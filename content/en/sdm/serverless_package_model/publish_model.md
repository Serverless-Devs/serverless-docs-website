---
title: Pacakge Post
description: 'Pacakge release'
position: 6
category: 'Development Kit Models'
---
- [Release app](https://github.com/orgs/Serverless-Devs/discussions/439)
- [Application Model Specification](https://github.com/Serverless-Devs/Serverless-Devs/blob/publish_docs/spec/en/0.0.2/serverless_package_model/package_model.md#application-model-specification)
- [Parameters specification] (#Parameters specification)
  - [default data type](#default data type)
    - [string](#string)
    - [boolean](#boolean)
    - [password](#password)
  - [custom UI](#custom UI)
    - [oss x-bucket](#x-bucket)
    - [role authorization x-role](#x-role)
    - [nas network disk x-nas](#x-nas)

# Parameters specification
## default data type
### string
The full description is
````
region:
  title: Territory
  type: string
  default: cn-hangzhou
  description: The region where the app is created
  enum:
    - cn-beijing
    - cn-hangzhou
    - cn-shanghai
    - cn-qingdao
    - cn-zhangjiakou
    - cn-huhehaote
    - cn-shenzhen
    - cn-chengdu
    - cn-hongkong
    -ap-southeast-1
    -ap-southeast-2
    -ap-southeast-3
    -ap-southeast-5
    -ap-northeast-1
    - eu-central-1
    - eu-west-1
    - us-west-1
    - us-east-1
    - ap-south-1
````
> enum represents the enumeration value, the user does not need to enter it manually, just select it directly

- The expression in cli is:
![](https://img.alicdn.com/imgextra/i4/O1CN01kOr5UI29BKmNNuZLe_!!6000000008029-2-tps-1304-334.png)

- The expression on the webpage is as
![](https://img.alicdn.com/imgextra/i4/O1CN01A49qaI23UfoB84sU2_!!6000000007259-2-tps-1968-644.png)

### boolean

The full description is

````
internetAccess:
  type: boolean
  title: allow public network access
  description: Whether the function in the configuration service can access the Internet
  default: true
````

- The expression in cli is:
  ![](https://img.alicdn.com/imgextra/i1/O1CN01UyPuY51wjbPTe8Jg7_!!6000000006344-2-tps-1062-212.png)

- The expression on the webpage is as
  ![](https://img.alicdn.com/imgextra/i4/O1CN01pMntUJ1MHpDpOLFTa_!!6000000001410-2-tps-1670-472.png)

###password

The full description is

````
password:
  type: password
  title: Application Admin Password
  description: application administrator password
  default: 123456
````

- The expression in cli is:
  ![](https://img.alicdn.com/imgextra/i3/O1CN01TZvXPN1Ne664nVWoS_!!6000000001594-2-tps-1058-256.png)

- The expression on the webpage is as
  TODO:

## custom UI
The main user of the custom UI is on the web side, and the user can operate it conveniently. Usually starts with `x-`
#### x-bucket
Used for oss bucket selection
````
bucketName:
  title: OSS bucket name
  type: string
  default: ""
  description: OSS bucket name (note the same region as the function)
  x-bucket:
    dependency:
      - region # depends on other input fields region
````
![](https://img.alicdn.com/imgextra/i3/O1CN01qmCC5P1adGNimqJuM_!!6000000003352-2-tps-1946-700.png)

##### Field Description
| Field Name | Type | Description |
| --- | --- | --- |
| dependency | list<`string`> | dependency fields |

#### x-role
for character selection
````
triggerRoleArn:
  title: Trigger RAM Role ARN
  type: string
  default: ''
  pattern: '^acs:ram::[0-9]*:role/.*$'
  description: OSS uses this role to send event notifications to call functions
  required: true
  x-role:
    name: aliyunosseventnotificationrole # role name
    service: OSS # service account
    authorities:
      -AliyunFCInvocationAccess
````
![](https://img.alicdn.com/imgextra/i1/O1CN01LQCH9a1XiLw3aa09O_!!6000000002957-2-tps-2032-770.png)

##### Field Description
| Field Name | Type | Description |
| --- | --- | --- |
| name | `string` | system role name |
| service | `string` | Service account, currently supported system accounts: OSS, FC, LOG |
| authorities | list<`string`> | system policies |

#### x-nas

Choice of NAS mount points, VPCs, switches, security groups

````
mountPointsServerAddr:
  title: NAS mount point address
  type: string
  default: ""
  description: NAS mount point address, you can log in to <a href="https://nasnext.console.aliyun.com" target="_blank">NAS console</a> to view
  x-nas:
    denpendency:
      - region
````
##### Field Description

| Field Name | Type | Description |
| ---------- | -------------- | -------- |
| dependency | list<`string`> | dependency fields |


> Note that x-nas is used with the 'vpcId', 'vswitchId', 'securityGroupId' fields

````
vpcId:
  title: VPC Id
  type: string
  default: ""
  description: VPC ID where the NAS mount point is located, such as vpc-bp1lynmabizqdgt4308dt
vswitchId:
  title: Switch Id
  type: string
  default: ""
  description: VSW ID of the virtual switch where the NAS mount point is located, the switch should preferably be in the availability zone supported by FC
securityGroupId:
  title: Security Group Id
  type: string
  default: ""
  description: Log in to <a href="https://ecs.console.aliyun.com/#/securityGroup/region/cn-hangzhou" target="_blank">security group</a> to view, usually empty security created by default group (note the same region as above), for example sg-bp1cd2w08t3dy7nhrvtx
````

![](https://img.alicdn.com/imgextra/i1/O1CN01eov5OU1op5DsbN82b_!!6000000005273-2-tps-2016-750.png)