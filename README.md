# nCov-page
疫情数据展示页模板，根据 serverless framework 构建。基于该项目[部署 Serverless 全栈 WEB 应用（Vue.js）](https://github.com/serverless/components/tree/master/templates/tencent-fullstack-vue-application)

&nbsp;

操作步骤：

1. [安装](#1-安装)
2. [部署](#2-部署)

&nbsp;

### 1. 安装

首先，通过如下命令安装 [Serverless Framework](https://www.github.com/serverless/serverless):

```console
$ npm i -g serverless
```

之后可以新建一个空的文件夹，使用 `create --template-url`，安装相关 template。

```console
$ serverless create --template-url https://github.com/tinafangkunding/nCov-page
```

使用`cd`命令，进入`\nCov-page` 文件夹，可以查看到如下目录结构：

```
|- api
|- dashboard
|- serverless.yml      # 使用项目中的 yml 文件
```

在`\nCov-page`目录下，运行如下命令分别安装目录下的 NPM 依赖：
```
$ npm run bootstrap
```

### 2. 部署

回到`nCov-page`目录下，直接通过 `serverless` 命令来部署应用:

```console
$ serverless
```

如果希望查看部署详情，可以通过调试模式的命令 `serverless --debug` 进行部署。

如您的账号未[登陆](https://cloud.tencent.com/login)或[注册](https://cloud.tencent.com/register)腾讯云，您可以直接通过微信扫描命令行中的二维码进行授权登陆和注册。

部署成功后，可以直接在浏览器中访问日志中返回的 dashboard url 地址，查看该全栈 Web app 的效果:

```
  dashboard: 
    url: http://9u9ywac-n56qlg-1251971143.cos-website.ap-guangzhou.myqcloud.com
    env: 
      apiUrl:   https://service-l77nemo2-1251971143.gz.apigw.tencentcs.com/release/
      apiUrlSZ: https://myapi.ihogu.com/public/?s=Whfy.city&city=%E6%B7%B1%E5%9C%B3
  api: 
    region:              ap-guangzhou
    functionName:        tencent-fullstack-vue-api
    apiGatewayServiceId: service-l77nemo2
    url:                 https://service-l77nemo2-1251971143.gz.apigw.tencentcs.com/release/

  21s › dashboard › done
```

&nbsp;

> 注:

1. 首次部署成功后，也可以通过以下命令，在本地运行服务，并与后端腾讯云服务进行通讯：

```console
$ cd dashboard && npm run start
```

2. 腾讯云 Component 已支持二维码一键登录，如您希望使用配置秘钥的方式登录，也可以参考如下步骤：
   在`nCov-page` 文件夹根目录创建 `.env` 文件

```console
$ touch .env # 腾讯云的配置信息
```

在 `.env` 文件中配置腾讯云的 SecretId 和 SecretKey 信息并保存
如果没有腾讯云账号，可以在此[注册新账号](https://cloud.tencent.com/register)。

如果已有腾讯云账号，可以在[API 密钥管理](https://console.cloud.tencent.com/cam/capi)中获取 `SecretId` 和`SecretKey`

```
# .env
TENCENT_SECRET_ID=123
TENCENT_SECRET_KEY=123
```
