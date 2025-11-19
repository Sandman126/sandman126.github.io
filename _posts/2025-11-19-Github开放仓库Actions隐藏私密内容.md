---
title: Github开放仓库Actions隐藏私密内容
description: GitHub Actions 里根本没有 git-crypt 密钥 → 拉下来的 `_config.yml` 是一坨加密乱码 → Jekyll 构建直接炸掉，报错一大堆。
category:
  - 网络
  - Github
tags:
  - github
  - jekyll
  - action
  - crypt
  - 加密
pin: false
math: false
mermaid: false
image: assets/img/bannel.jpg
---

你遇到的问题非常典型，也几乎是所有用 **git-crypt 加密 Jekyll/Hexo/Quarto 等静态站点配置文件** 的人都会踩的坑：

**GitHub Actions 里根本没有 git-crypt 密钥 → 拉下来的 `_config.yml` 是一坨加密乱码 → Jekyll 构建直接炸掉，报错一大堆。**



#### **不要加密 `_config.yml`，改用 GitHub Actions 的 Encrypted Secrets + 环境变量注入**

理由：  
- `_config.yml` 本身几乎不放真正需要隐藏的内容（URL、标题、主题这些本来就是公开的）  
- 真正需要隐藏的（API key、Token、Analytics ID、Disqus shortname 等）完全可以用 `secrets` 注入  
- 彻底避免 git-crypt 在 CI 环境解密失败的各种坑

**具体操作步骤（3 分钟搞定）**

1. **把敏感内容从 `_config.yml` 里全部删掉/注释掉**  
   改成这样（以 Jekyll 为例）：

   ```yaml
   # _config.yml（明文提交，公开仓库也安全）
   title: 我的博客
   url: https://yourname.github.io

   # 下面这些用 GitHub Secrets 注入，不写死
   google_analytics:  # 会自动填入
   disqus:
     shortname:       # 会自动填入
   baidu_analytics:   # 会自动填入

   # 私密 API 密钥（比如私人图床、评论系统 webhook 等）
   private_api_key:   # 会自动填入
   ```

2. **去 GitHub 仓库 → Settings → Secrets and variables → Actions → New repository secret**  
   添加下面这些（名字随便起，但后面要对应）：

   | Secret 名称             | 值（填你真实的）            |
   |-------------------------|-----------------------------|
   | GOOGLE_ANALYTICS        | UA-123456-7                 |
   | DISQUS_SHORTNAME        | your-disqus-shortname       |
   | BAIDU_ANALYTICS         | 2c123f0a5axxxxxxxxxxxxxxxx  |
   | PRIVATE_API_KEY         | sk-xxxxxxxxxxxxxxxxxxxx    |

3. **修改 GitHub Actions 工作流（.github/workflows/ci.yml）**  
   示例（适用于 Jekyll）：

   ```yaml
   name: Build and Deploy
   on: [push, workflow_dispatch]
   jobs:
     build:
       runs-on: ubuntu-latest
       steps:
       - uses: actions/checkout@v4

       # 关键一步：在构建前注入 secrets 到 _config.yml
       - name: Inject secrets into _config.yml
         run: |
           sed -i "s|google_analytics:.*|google_analytics: ${{ secrets.GOOGLE_ANALYTICS }}|" _config.yml
           sed -i "s|shortname:.*|shortname: ${{ secrets.DISQUS_SHORTNAME }}|" _config.yml
           sed -i "s|baidu_analytics:.*|baidu_analytics: ${{ secrets.BAIDU_ANALYTICS }}|" _config.yml
           sed -i "s|private_api_key:.*|private_api_key: ${{ secrets.PRIVATE_API_KEY }}|" _config.yml

       - name: Build with Jekyll
         uses: actions/jekyll-build-pages@v1
         with:
           source: ./
           destination: ./_site

       - name: Upload Pages artifact–

         uses: actions/upload-pages-artifact@v3
   ```

这样就完美解决了：  
- 公开仓库里 `_config.yml` 永远是明文（Actions 能正常构建）  
- 所有私密内容通过 GitHub 官方加密通道注入，100% 安全  
- 完全不需要 git-crypt，也不用在 CI 里折腾 GPG 私钥


