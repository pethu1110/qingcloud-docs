---
title: "步骤二：开启外网访问（可选）"
description: 本小节主要介绍如何快速配置 MySQL Plus 集群访问白名单。 
keywords: mysql plus 白名单,公网访问,外网访问
weight: 20
collapsible: false
draft: false
---

本小节主要介绍如何开启 MySQL Plus 外网访问，包括申请外网访问和配置 IP 白名单。

## 背景介绍

在 APPCenter 管理控制台，MySQL Plus 集群默认不提供外网地址。若需允许外网访问集群，需申请外网访问，并配置允许外网访问的 IP 白名单。

- **外网**又叫公网。开启外网访问后，外网地址可能会降低集群的安全性，请谨慎使用。
   
   - 为加强外网访问安全，外网访问安全组由系统维护，无需另行配置管理。
   
   - 外网地址使用的公网 IP，目前免费使用，您

- **IP 白名单**指允许外网访问 MySQL Plus 集群的 IP 清单，建议您定期维护白名单，提高集群外网访问安全。需要设置 IP 白名单的场景如下：
   
   - 若需允许外部服务器正常访问集群，需要将外部 IP 地址添加至 IP白名单。
  
   - 若需允许不同 VPC 网络服务器访问集群，可选择集群切换 VPC 网络或将服务器 IP 地址添加到 IP 白名单。

## 前提条件

- 已获取 QingCloud 管理控制台登录账号和密码，且已获取集群操作权限。
- 已创建 MySQL Plus 集群，且集群状态为**活跃**。
- 已获取允许访问的主机 IP 清单。

## 操作步骤

1. 在集群管理页面，点击目标集群 ID，进入集群详情页面。

2. [申请外网访问](#申请外网访问)
   
3. [配置 IP 白名单](#配置-ip-白名单)

4. 获取外网连接信息。
   
   在**连接信息**模块，即可查看已配置的外网访问地址和 IP 白名单。
   
   <img src="../../_images/check_access_info.png" alt="查看连接信息" style="zoom:50%;" />
  
### 申请外网访问
   
1. 在左侧**连接信息**模块，点击**申请外网地址**。

   <img src="../../_images/external_access.png" alt="申请外网访问" style="zoom:50%;" />

2. 在弹出的外网申请须知窗口，确认申请须知和免责声明信息后，勾选**已阅读申请须知和免责声明，并同意申请外网地址**。
   
    <img src="../../_images/external_access_notice.png" alt="外网访问免责声明" style="zoom:50%;" />

3. 点击**免费申请**，跳转到申请外网地址窗口。

    <img src="../../_images/set_external_access.png" alt="配置外网域名和端口" style="zoom:50%;" /> 

4. 配置外网域名和端口。

    **外网域名**: 不支持为空；长度8～64个字符；以小写字母开头，可包含小写字母（a～z）、大写字母（A～Z）、数字（0～9）、特殊字符（_-)。
    
    **外网端口**: 默认值为3306；不支持为空；不支持大小写字母和特殊字符；端口范围1000～65534。

5. 点击**提交**，返回集群详情页面。

   <img src=".../../_images/enable_external_access.png" alt="开启外网访问" style="zoom:50%;" />

### 配置 IP 白名单

1. 在**连接信息**模块，点击**设置 IP 白名单**。
   
    <img src="../../_images/set_whitelist0.png" alt="配置 IP 白名单" style="zoom:50%;" />

2. 弹出外网访问白名单配置窗口，根据白名单配置要求，输入允许访问的外网服务器 IP。
    
    可输入 IP 地址、IP 段和 IP 地址范围；多个 IP 之间换行分隔。

     - IP 白名单不支持为空，不支持重复 IP 地址。

     - IP 白名单添加0.0.0.0/0，表示任何外网 IP 地址均可连接数据库，请谨慎使用。

     - IP 白名单添加127.0.0.1，表示任何 IP 地址均无法连接数据库。
   
3. 点击**提交**，返回集群详情页面，即可使用外网地址访问数据库。

   <img src="../../_images/check_access_info.png" alt="连接信息" style="zoom:50%;" />

## 后续管理

 - [修改外网地址](../../manual/mgt_connect/mgt_external_network)
  
 - [修改 IP 白名单](../../manual/mgt_connect/mgt_whitelist)
