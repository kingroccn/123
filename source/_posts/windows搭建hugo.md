title: windows搭建hugo
author: 云溪酋长
tags:
  - hugo
  - windows
  - github
  - travis
categories:
  - 技巧
date: 2018-06-07 16:13:00
---
# Step 1: Install Hugo

# Step 2: Create a New Site 
`hugo new site quickstart`

# Step 3: Add a Theme 
See themes.gohugo.io for a list of themes to consider. This quickstart uses the beautiful Ananke theme.
```
cd quickstart;\
git init;\
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke;\
```
Edit your config.toml configuration file
and add the Ananke theme.

```echo 'theme = "ananke"' >> config.toml``` 

# Step 4: Add Some Content 

`hugo new posts/my-first-post.md`  

# Step 5: hugo server
```
hugo server -D
```
# Step 6: Travis CI的配置
* 生成GH_TOKEN[(官方教程链接)](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/)
![](https://raw.githubusercontent.com/MaxdSre/maxdsre.github.io/image/blog-image/2018-04-10-go_travisci_github_page/2018-04-11_00-13-54-github-access-token.png)
* 将生成的token添加到Travis的环境变量
![](https://raw.githubusercontent.com/MaxdSre/maxdsre.github.io/image/blog-image/2018-04-10-go_travisci_github_page/2018-04-11_00-11-05-travisci-system-var-setting.png)
* 创建.travis.yml 文件  

# Step 7: Travis CI生成
![](/20180604131101852/20180604022059157.png)