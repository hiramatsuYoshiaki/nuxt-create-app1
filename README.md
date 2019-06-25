# nuxt-app1

> My excellent Nuxt.js project

## Build Setup

``` bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, checkout [Nuxt.js docs](https://nuxtjs.org).

# GitHub Pages へデプロイするには？
 
Nuxt.js を使うと、例えば GitHub Pages のような静的ホスティングサービスで、ウェブアプリケーションをホストすることが可能です。 
 
GitHub Pages へデプロイするには、静的なウェブアプリケーションを生成する必要があります 
 
`
npm run generate
`
GitHub Pages のホスティングにデプロイするもの全てが入った dist フォルダが作成されます。プロジェクトリポジトリであれば gh-pages ブランチ、ユーザーや組織のサイトであれば master ブランチにデプロイしてください 。

1. nuxt.config.jsを編集する。
`
export default {
  router: {
    base: '/<repository-name>/'
  }
}
`
ローカルでアクセスするときは、
`
http://localhost:3000/リポジトリ名/
例
http://localhost:3000/nuxt-create-app1/
`
2. コマンドラインでデプロイする。push-dir package をインストールする。
`
npm install push-dir --save-dev
`
3. deploy コマンドを package.json に追加する。
ブランチは、プロジェクトリポジトリならば gh-pages ブランチ、ユーザーまたは組織サイトならば master ブランチを指定。
`
"scripts": {
  "dev": "nuxt",
  "build": "nuxt build",
  "start": "nuxt start",
  "generate": "nuxt generate",
  "deploy": "push-dir --dir=dist --branch=gh-pages --cleanup"
},
`
4. 静的なアプリケーションを生成
`
npm run generate
`
5. デプロイする。
`
npm run deploy
`