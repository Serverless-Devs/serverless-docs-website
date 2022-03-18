---
title: 本地调用 local
description: '本地调用 local'
position: 1
category: '调用&调试'
---

# Local 命令

`local` 命令是在本地对函数调试的命令。

- [命令解析](#命令解析)
- [local invoke 命令](#local-invoke-命令)
  - [参数解析](#参数解析)
  - [操作案例](#操作案例)
- [local start 命令](#local-start-命令)
  - [参数解析](#参数解析-1)
  - [操作案例](#操作案例-1)

> ⚠️ 注意：该命令对 Docker 有所依赖，所以在使用该命令时，需要先进行 [Docker 安装](https://docs.docker.com/get-started/#download-and-install-docker) 。


## 命令解析

当执行命令`local -h`/`local --help`时，可以获取帮助文档。

在该命令中，包括了两个个子命令：

- [invoke：本地调试事件函数](#local-invoke-命令)
- [start：本地调试HTTP函数](#local-start-命令)

## local invoke 命令

`local invoke` 命令，是进行本地事件函数调试的命令。

> 💡 事件函数指的是非 HTTP 触发器的函数，包括不限于 OSS 触发器函数、CDN 触发器函数、Tablestore 触发器函数等。

当执行命令`local invoke -h`/`local invoke --help`时，可以获取帮助文档。

### 参数解析

| 参数全称      | 参数缩写 | Yaml模式下必填 | 参数含义                                                     |
| ------------- | -------- | -------------- | ------------------------------------------------------------ |
| event         | e        | 选填           |传入 `event` 函数的 `event` 事件数据，可以通过 `s cli fc-event` 指令快速获取事件数据示例，详细操作参考[这里](https://github.com/devsapp/fc/blob/main/docs/zh/command/invoke.md#注意事项)|
| event-file    | f        | 选填           |以文件形式传入 `event` 事件数据|
| event-stdin   | s        | 选填           |以标准输入形式传入 `event` 事件数据|
| mode          | m        | 选填           |调试模式选择，包括：<br> - `normal`: 默认模式，本地函数运行容器在函数执行完成后立刻退出<br>`server`: 本地函数运行容器一直存在，用户在其他终端发起的本地调用会复用该容器<br>`api`: 支持通过 sdk 调用本地函数|
| config        | c        | 选填           |指定断点调试时使用的 IDE，取值范围：`vscode, pycharm, intellij`|
| debug-port    | d        | 选填           |指定断点调试端口|
| debug-args    | -        | 选填           |断点调试时传入的参数|
| debugger-path | q        | 选填           |自定义断点调试器路径|
| tmp-dir       | -        | 选填           |自定义函数运行环境中 `/tmp` 路径的本机挂载路径，默认为 `./.s/tmp/invoke/serviceName/functionName`/|
| server-port   | -        | 选填           |自定义本地监听 `server` 的端口，默认是在 7000 到 8000 间的随机端口|
| debug         | -        | 选填           | 打开`debug`模式，将会输出更多日志信息                        |
| help          | h        | 选填           | 查看帮助信息                                                 |

### 操作案例

**有资源描述文件（Yaml）时**，可以直接执行`s local invoke `进行本地调试，完成的输出示例：

```
FC Invoke Start RequestId: 0ba8ac3f-abf8-46d4-b61f-8e0f9f265d6a
2021-11-11T05:45:58.027Z 0ba8ac3f-abf8-46d4-b61f-8e0f9f265d6a [INFO] hello world
FC Invoke End RequestId: 0ba8ac3f-abf8-46d4-b61f-8e0f9f265d6a
hello world

RequestId: 0ba8ac3f-abf8-46d4-b61f-8e0f9f265d6a 	 Billed Duration: 146 ms 	 Memory Size: 128 MB 	 Max Memory Used: 23 MB
```


## local start 命令

`local start` 命令，是进行本地 HTTP 函数调试的命令。

当执行命令`local start -h`/`local start --help`时，可以获取帮助文档。

### 参数解析

| 参数全称      | 参数缩写 | Yaml模式下必填 | 参数含义                                                     |
| ------------- | -------- | -------------- | ------------------------------------------------------------ |
| config        | c        | 选填           | 指定断点调试时使用的 IDE，可选：`vscode, pycharm, intellij` |
| debug-port    | d        | 选填           | 指定断点调试端口 |
| custom-domain | -        | 选填           | 以自定义域名作为 HTTP Server 的访问 url |
| debug-args    | -        | 选填           | 断点调试时传入的参数 |
| debugger-path | -        | 选填           | 自定义断点调试器路径 |
| tmp-dir       | -        | 选填           | 自定义函数运行环境中 `/tmp` 路径的本机挂载路径，默认为 `./.s/tmp/invoke/serviceName/functionName/` |
| server-port   | -        | 选填           | 自定义本地监听 HTTP Server 的端口，默认是在 7000 到 8000 间的随机端口 |
| debug         | -        | 选填           | 打开`debug`模式，将会输出更多日志信息                        |
| help          | h        | 选填           | 查看帮助信息                                                 |

### 操作案例

**有资源描述文件（Yaml）时**，可以直接执行`s local start `进行资源部署，部署完成的输出示例：

```text
 	url: http://localhost:7665/2016-08-15/proxy/fc-deploy-service/http-trigger-py36/
	methods: GET
	authType: anonymous

    Tips for more action:
        Start with customDomain method: [s local start auto]
        Debug with customDomain method: [s local start -d 3000 auto]
```

此时，可以根据命令行提示的`url`信息，在浏览器中查看 HTTP 函数本地调试的具体内容。

如果需要通过自定义域名的方式调试 HTTP 函数，则可以在调试时增加`--custom`参数，输出示例：

```
  url: http://localhost:7308/
	methods: GET
	authType: anonymous
```

> 关于自定义域名调试模式以及默认的调试模式区别：在使用函数计算的 HTTP 函数时，是有两个域名组成：
>
> - 系统域名地址，例如`http://localhost:7665/2016-08-15/proxy/fc-deploy-service/http-trigger-py36/`
> - 自定义域名地址，例如`http://abc.com`/
>
> 这两个地址在非 custom runtime 函数中是没有区别的，而对于 custom-runtime/custom-container 函数，这两个地址的核心区别是其`path`不同，例如以传统的 Web 框架为例：
>
> - 系统域名地址的基础路径匹配是：`/2016-08-15/proxy/fc-deploy-service/http-trigger-py36/`
> - 自定义域名地址的基础路径匹配可以是任何形式，包括`/`
>
> 由于路径的不同，所以在代码开发和处理的时候，都会有所不同，如果使用某个 Web 框架（例如 Express、Django 等），匹配的首页地址为`/`，那么使用系统域名地址则可能会出现`404`，这个时候较为推荐使用自定义域名，获得更原生的体验。所以为了满足开发者在系统域名与自定义域名不同模式下的调试需要，本组件支持`--custom-domain`参数进行自定义域名模式调试。
> 如果既要使用 custom-runtime/custom-container 函数，又要使用系统域名，还要不处理系统基础路径，那么可以在发给函数的 HTTP 请求中增加 header: `x-fc-invocation-target: 2016-08-15/proxy/$ServiceName/$functionName` 即可

### 注意事项

针对 s local start 本地调用交互设计：

- 如果不存在 customDomains 配置，一定使用系统域名路径：`/2016-08-15/proxy/serviceName/functionName/`
- 存在 customDomains 配置
  1. 指定 --custom-domain 参数, 使用指定域名配置的路径
  2. 未指定 --custom-domain
    2.1 如果 customDomains 仅有一个，直接使用此域名配置的路径
    2.2 如果存在多个则产生`交互`，选择配置的域名路径
  > 如果使用系统域名路径，使用 --custom-domain system 或者选择时候选择 system

## 调用时模拟 NAS 目录

当yaml中配置了nasConfig时，local 可以模拟 nas 的目录结构，例如：
`s.yaml` 配置如下
````yaml
services:
  helloworld:
    component:  fc
    props:
      region: cn-hangzhou
      service:
        name: hello-world-service
        description: 'hello world by serverless devs'
        vpcConfig: auto
        nasConfig:
          userId: 10003
          groupId: 10003
          mountPoints:
            - serverAddr: xxx.cn-hangzhou.nas.aliyuncs.com
              nasDir: /hello-world-service
              fcDir: /mnt/auto
      function:
        name: event-py3
        description: 'hello world by serverless devs'
        runtime: python3
        codeUri: ./code
        handler: index.handler
        memorySize: 128
        timeout: 60
````
`code/index.py` 内容如下
````
# -*- coding: utf-8 -*-
import logging
import os

def handler(event, context):
  logger = logging.getLogger()
  logger.info('============')
  os.system("ls /mnt/auto")
  logger.info('============')
  return 'hello world\n'
````

`s.yaml` 同目录级别 `.s/nas/auto-default/hello-world-service` 的目录下存在一个文件为 `test.ts` 的文件，目录结构及执行结果如下：
<img src="https://img.alicdn.com/imgextra/i4/O1CN01NqMcAX1h6vhheEDlz_!!6000000004229-2-tps-2494-1536.png"/>
