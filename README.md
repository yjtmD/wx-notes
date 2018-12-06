### 基于GitBook的博客搭建

*  ###### 通过NPM安装gitbook
```
npm install gitbook-cli -g
```
*  ###### 初始化项目(新建文件)
```
gitbook init
```
*  ###### 启动服务(http://localhost:4000/)
```
gitbook serve
```
*  ###### 根目录下新建`book.json`
```
{
  "title": "前端笔记",
  "author": "yjtmD",
  "description": "前端笔记积累",
  "language": "zh-hans",
  "gitbook": ">=3.0.0",
  "styles": {
    "website": "./styles/website.css"
  },
  "structure": {
    "readme": "README.md"
  },
  "links": {
  },
  "plugins": [
    "-search",
    "search-pro",
    "github"
  ],
  "pluginsConfig": {
    "search-pro": {
      "cutWordLib": "nodejieba"
    },
    "github": {
      "url": "https://github.com/yjtmD/wx-notes"
    }
  }
}
```
*  ###### 安装插件
```
gitbook install
```
*  ###### 关联git仓库
*  ###### 全局安装`gh-pages`工具
```
npm install gh-pages -g
```
*  ###### _book部署到分支
```
gh-pages -d _book
```
*  ###### 关联域名，添加`CNNAME`文件
