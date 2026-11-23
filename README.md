---
title : 'Hugo Template'
date : 2026-11-11T11:11:11
draft : false 
---
 
# Hugo Template
 [@seedunk](https://seedunk.github.io)
  
### 配置文件 
  - hugo.toml
  ``` 
    baseURL = "https://demo.seedunk.com/"  
    languageCode = "zh-CN" 
    title = "Demo"
    publishDir = "public"
    summaryLength = 70    
    [menus]
    [[menus.main]]
        name = 'Index'
        pageRef = '/'
        weight = 10
    
    [[menus.main]]
        name = 'Tags'
        pageRef = '/tags'
        weight = 30
    
    [module]
    proxy = "https://goproxy.cn,direct"
    
    [[module.imports]] 
    path = "github.com/seedunk/hugo-template/themes/seedunk"
    [[module.mounts]]
        source = "content"
        target = "content"
    [[module.mounts]]
        source = "layouts"
        target = "layouts"
    [[module.mounts]]
        source = "assets"
        target = "assets"
    [[module.mounts]]
        source = "static"
        target = "static"
    [[module.mounts]]
        source = "data"
        target = "data"
    [[module.mounts]]
        source = "i18n"
        target = "i18n"
    [[module.mounts]]
        source = "archetypes"
        target = "archetypes"
    [[module.mounts]]
        source = "assets"
        target = "content/assets"
    [[module.mounts]]
        source = "README.md"
        target = "content/_index.md"  
  ```

### 使用脚本
  ```
    # 初始化工程
    ~/bin/hugo mod init sample
    ~/bin/hugo mod tidy
    # 下载mod
    ~/bin/hugo mod get u
    # 构建
    ~/bin/hugo -s ~ server --poll 800ms --disableFastRender --disableLiveReload
  ```