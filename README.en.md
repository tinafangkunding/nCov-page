# nCov-page

Use Serverless Components to deploy a nCov page with 3 steps. Check how many people get sick in your city. The project based on [Serverless full-stack template Vue.js + Express.js）](https://github.com/serverless/components/tree/master/templates/tencent-fullstack-vue-application)

&nbsp;

1. [Install](#1-install)
2. [Create](#2-create)
3. [Deploy](#3-deploy)

[简体中文](./README.md) | English

&nbsp;

### 1. Install

Install the [Serverless Framework](https://www.github.com/serverless/serverless):

```console
$ npm i -g serverless
```

### 2. Create

Next, use the create --template-url command to install the template.

```console
$ serverless create --template-url https://github.com/tinafangkunding/nCov-page
```

Use `cd` command and get into `\nCov-page` folder, and the directory should look something like this:

```
|- api
|- dashboard
|- serverless.yml      # 使用项目中的 yml 文件
```

Run bootstrap script to install the NPM dependencies:
```
$ npm run bootstrap
```

### 3. Deploy

Deploy via the serverless command:
```
$ serverless
```
Use the --debug flag if you'd like to learn what's happening behind the scenes:
```
$ serverless --debug
```

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

### 5. Account (optional)

If you cannot Login/Signup with Wechat QR code, just create a `.env` file

```console
$ touch .env # your Tencent API Keys
```

Add the access keys of a [Tencent CAM Role](https://console.cloud.tencent.com/cam/capi) with `AdministratorAccess` in the `.env` file, using this format:

```
# .env
TENCENT_SECRET_ID=123
TENCENT_SECRET_KEY=123
```

- If you don't have a Tencent Cloud account, you could [sign up](https://intl.cloud.tencent.com/register) first.
