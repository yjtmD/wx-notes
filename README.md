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
  "output.name": "site",
  "gitbook": "3.2.3",
  "root": ".",
  "styles": {
    "website": "styles/website.css"
  },
  "links": {
  },
  "plugins": [
    "-lunr",
    "-search",
    "-highlight",
    "search-plus",
    "simple-page-toc",
    "prism",
    "prism-themes",
    "github",
    "donate",
    "anchor-navigation-ex",
    "expandable-menu",
    "splitter",
    "include-codeblock",
    "tbfed-pagefooter"
  ],
  "pluginsConfig": {
    "simple-page-toc": {
      "maxDepth": 3,
      "skipFirstH1": true
    },
    "prism": {
      "css": [
        "prism-themes/themes/prism-base16-ateliersulphurpool.light.css"
      ]
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
    },
    "tbfed-pagefooter": {
      "modify_label": "该文件修订时间：",
      "modify_format": "YYYY-MM-DD HH:mm:ss"
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
