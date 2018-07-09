# AT device #

## 1. 简介 ##

AT device 软件包是由 RT-Thread AT 组件针对不同 AT 设备的移植文件和示例代码组成，目前支持的 AT 设备有：ESP32、ESP8266、M26等，其中 ESP8266 和 M26 设备完成对 `AT socket` 功能的移植，及设备通过 AT 命令实现标准 socket 编程接口，完成 socket 通讯的功能，具体功能介绍可参考 [RT-Thread AT 用户手册](https://git.rt-thread.com/packages/rt_at/blob/master/README.md)。

### 1.1. 文件结构 ###

| 名称 | 说明 |
| ---- | ---- |
| at_socket_esp8266.c  |  ESP8266 模块针对 AT 组件的移植文件，实现 AT socket |
| at_socket_m26.c | M26 模块针对 AT 组件的移植文件，实现 AT socket |
| at_client_sample.c | ESP8266 模块 AT Client 功能示例文件 |

### 1.2 许可证 ###


### 1.3 依赖 ###

- RT_Thread 3.0+
- RT_Thread AT 组件
- RT_Thread SAL 组件

## 2. 获取方式 ##

AT device 软件包是对 AT 组件库和 AT socket 功能的移植，需开启 AT 组件库和 AT socket 功能来获取 AT device 软件包。

先要开启 AT 组件库和 AT socket 功能， 具体路径如下所示：

    RT-Thread Components  --->
        Network stack  --->
             Socket abstraction layer  --->
                protocol family type  --->
                  [ ] Support lwIP stack
                  [*] Support AT Commands stack

开启 AT socket 功能之后，默认开启 AT device 软件包， 具体路径如下所示：

    Privated Packages of RealThread  --->
        -*- AT DEVICE: RT-Thread AT component porting or samples for different device             
              AT socket device modules (Not selected, please select)  --->    
              Version (latest)  --->

- `AT socket device modules`: AT 设备选择，目前支持 ESP8266、M26 等设备；
- `Version`: 下载软件包版本；

## 3. 注意事项  ##

- AT device 软件包默认设备类型为未选择，使用时需要指定使用设备型号；
- AT device 软件包目前处于 `beta` 测试阶段, 推荐在 menuconfig 选项中选择 `latest` 版本；