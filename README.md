![RAN](https://user-images.githubusercontent.com/694940/29736531-6ab509e8-8a02-11e7-8e61-66e5ea4e29b8.png)

### serverless-ran

Fork by [ran](https://github.com/Sly777/ran), and integrated with [Serverless Framework](https://github.com/serverless/serverless).

## Features

- **_Integrated with Serverless Framework_**

- **_Hot-Reload Ready for Dev_**

- **_Next Generation JavaScript (ES6)_**

- **_Offline Ready (Experimental!)_**

- **_Next Generation CSS (CSS-in-JS)_**

- **_Create New Page in a Second (with CLI)_**

- **_SEO-Ready_**

- **_Performance-first_**

- **_Production Deployment Ready for Now, Digital Ocean, Heroku, and AWS_**

- **_Prettier and ESLint integrated_**

## How to use

- Firstly, clone the repo with this command.

```bash
git clone --depth=1 https://github.com/yugasun/serverless-ran.git serverless-ran
cd serverless-ran
yarn
```

- If you are not using Yarn, just run `npm install` instead of `yarn`
- After everything is finished, run `yarn dev` (or `npm run dev`)

And that's all!

## Deploy to Tencent Cloud

This project using serverless component [tencnet-nextjs](https://github.com/serverless-components/tencent-nextjs) to deploy.

### Install Serverless

Install the Serverless Framework globally:

```bash
$ npm install -g serverless
```

### Create .env file (optional)

In project root, create the following simple boilerplate:

```bash
$ touch .env           # your Tencent api keys
```

Add the access keys of a [Tencent CAM Role](https://console.cloud.tencent.com/cam/capi) with `AdministratorAccess` in the `.env` file, using this format:

```
# .env
TENCENT_SECRET_ID=XXX
TENCENT_SECRET_KEY=XXX
```

If you don't have a Tencent Cloud account, you could [sign up](https://intl.cloud.tencent.com/register) first

### Configure serverless.yml

```yml
# serverless.yml
NextjsFunc:
  component: '@serverless/tencent-nextjs'
  inputs:
    functionName: nextjs-function
    region: ap-guangzhou
    code: ./
    functionConf:
      timeout: 30
      memorySize: 128
    environment:
      variables:
        RUN_ENV: test
    apigatewayConf:
      protocols:
        - http
        - https
      environment: release
```

- [More Options](https://github.com/serverless-components/tencent-nextjs/blob/master/docs/configure.md)

### Run Deploy

```bash
$ sls --debug
```

> Notice: `sls` is short for `serverless` command.

### Remove

```bash
$ sls remove --debug
```

#### Clean Setup (without example pages & components)

```bash
git clone --depth=1 https://github.com/yugasun/serverless-ran.git RAN
cd RAN
yarn && yarn setup:clean
```

## Example

[Click here](https://service-74whi6qw-1251556596.gz.apigw.tencentcs.com/release/) to see example project to understand how RAN! works on production. I used [graph.cool](https://graph.cool/) service for GraphQL and [now](https://zeit.co/now) for hosting in the example.

## Commands

Best feature of RAN! is **CL commands**. You can just run one command to create page with route! [Click here](docs/Commands.md) to see details how It works on RAN!.

![YAY](https://media.giphy.com/media/l0Iy6nmyS5p7hIAso/giphy.gif)
![YAYY](https://media.giphy.com/media/26vIfscbQhVK7ML5u/giphy.gif)

## Documentation

[Click here](https://www.rantoolkit.com/) to see all details of RAN!

## FAQ

[Click here](docs/FAQ.md) for FAQ of RAN! If it doesn't solve your problem, feel free to open an issue on GitHub!

## License

Copyright (c) 2020 Yuga Sun
