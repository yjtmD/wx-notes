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
```json
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
    "github",
    "donate",
    "anchor-navigation-ex",
    "expandable-menu",
    "splitter",
    "include-codeblock",
    "theme-comscore"
  ],
  "pluginsConfig": {
    "search-pro": {
      "cutWordLib": "nodejieba"
    },
    "github": {
      "url": "https://github.com/yjtmD/wx-notes"
    },
    "donate": {
      "wechat": "http://www.wxylx.top/images/wechat.jpg",
      "alipay": "http://www.wxylx.top/images/alipay.jpg",
      "title": "",
      "button": "打赏",
      "alipayText": "支付宝捐赠",
      "wechatText": "微信捐赠"
    },
    "anchor-navigation-ex": {
      "isRewritePageTitle": false,
      "tocLevel1Icon": "fa fa-hand-o-right",
      "tocLevel2Icon": "fa fa-hand-o-right",
      "tocLevel3Icon": "fa fa-hand-o-right"
    },
    "include-codeblock": {
      "template": "ace",
      "unindent": true,
      "edit": true
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
