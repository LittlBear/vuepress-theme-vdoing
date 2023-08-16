##### 一、安装基础环境

升级make、gcc、glibc，安装node.js(版本≥8)、npm@9.8.1、git



```sh
# 配置国内镜像
npm confifig set registry https://registry.npm.taobao.org

# npm升级到9.8.1
npm install -g npm@9.8.1

# clone the project
git clone https://github.com/xugaoyi/vuepress-theme-vdoing.git

# enter the project directory
cd vuepress-theme-vdoing

# install dependency 注意：如安装不成功请关闭淘宝源。
npm install # or yarn install

# develop
npm run dev # or yarn dev


```

###### git异常处理

###### `Peer's Certificate issuer is not recognized`异常

在CentOS7操作系统中搭建了内部使用的gitlab平台，当使用`git clone`下载代码时会提示以下异常：

```sh
fatal: unable to access 'https://*****/xx.git/': Peer's Certificate issuer is not recognized.
```

导致该问题的原因是系统证书问题，因为系统会对SSL证书进行验证，操作系统判断这个操作可能会造成不好的影响，并进行了阻止，停止了下载操作。

因为该gitlab仓库是我们信任的，我们只需要设置跳过SSL证书验证就可以，执行以下命令：

```sh
git config --global http.sslVerify false
```

[转自编程技术分享]: https://hellogitlab.com/CM/git/git_exceptions.html#peer-s-certificate-issuer-is-not-recognized%E5%BC%82%E5%B8%B8	"git异常处理"

