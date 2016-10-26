# 基于Android的NFC开发
NFC:近距离无线通信技术，分为主动模式和被动模式。
三种工作模式：
* 读写模式：由手机(NFC设备)作为发起者，以TAG作为目标者。
* P2P，2个NFC设备连接，实现数据的传递
* 卡模拟，类似IC卡，用于支付等

## NFC协议基础
### 技术标准和规范
* ISO 14443 (A/B)技术标准。A/B的编码方案和初始化方法不同，国内大部分的卡都是type-A的。type-B更开放一些。
* NFCIP-1 标准规范 
* MIFARE 标准规范
* Felica 由sony开发的一种标准规范

### TAG
TAG指的是复合NFC标准的标签或者卡片
#### NFC Forum定义的四种tag类型
* type-1 96bytes,106kb/s TOPAZ,ISO 14443
* type-2 512bytes,106kb/s MIFARE UL NXP
* type-3 Felica sony,读写模式是在生产的时候就确定了，不可更改
* type-4 ISO 14443,读写模式是在生产的时候就确定了，不可更改
 国内用的多的是type-2

#### NXP特定的tag类型
Mifare TAG:ISO 14443，可读可重写，可配置为只读

### NDEF协议
NFC Data Exchange Format,NFC数据交换格式，是一种二进制的消息封装格式。
一个NDEF信息包括若干个Record,每个Record有Header和Payload（内容）。具体可看[NFCForum-TS-NDEF_1.0](https://github.com/AeroYoung/NFC/NFCForum-TS-NDEF_1.0.pdf)的3.2

### RTD协议
NFC Record TyPE Definition
* RTD_TEXT 文本信息
* RTD_URL 网络地址
* RTD_SMART_POSTER 综合URL,标签等信息.Record里可以包含Record

