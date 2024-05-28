# 更新情况
#### 2024-05-17 更新
1. 原生本机Wifi，蓝牙支持
2. 更新到opencore 1.0.0
3. 支持最新 macOS 14.5版本
4. EFI文件归类，不同系统根据分类使用
5. 支持Apple DRM（支持无损格式，杜比）

#### 2023-4-30 更新
1. 加入大小核心调度，能够正确识别大核，线程，小核，不会启动应用直接全部占用
   系统优先使用大核，其次小核，再线程
1. 直接调用的主板自带因特尔网卡，支持Wi-Fi 6，不需要额外购买网卡
2. 如果是免驱显卡可以去掉 6650xt的acpi，如果是仿冒其他驱动，第一插槽的显卡地址为：pc00/peg1
3. 有线网卡速率2.5G
4. 去除usb端口限制
5. 已屏蔽核显，核显无法驱动，屏蔽后可以节能
6. 睡眠唤醒正常使用
7. 大小核补丁加入后，性能比未加入的要高很多
8. 声音，麦克风正常使用

##### 已知问题：
~~1. 自带蓝牙目前没有驱动~~已解决
2，不能随航（需要该功能可以买免驱动网卡，14已不支持直接免驱）

# EFI文件说明
macOS 12 - 13 版本： macOS-Ventura 目录
macOS 14.1 - 14.3.1版本：macOS-Sonoma-14.3.1up 目录
macOS 14.4 - up 版本：macOS-Sonoma-14.4 目录

#### 说明
由于macOS14.4有相关变更，不能直接无痛升级
需要将 Misc - Security - SecurityBootMode : Disabled

无线网卡驱动也需要重新部署（目前制作的EFI已经可以直接使用）

# macOS关于
<table>
    <tr>
        <td>
            <img src="images/info.jpg" border=0 style="margin-top:0px;">
            EFI：macOS-Ventura/EFI
            <br/>
            升级：小版本直接升级，大版本升级到14.3.1最高
            <br/>
            ⚠️需要将无线网卡升级到14.0版本
        </td>
        <td>
            <img src="images/macOS-14.3.png" border=0 style="margin-top:0px;">
            EFI：macOS-Sonoma-14.3.1up/EFI
            <br/>
            升级：14.0 - 14.3.1 之间任意版本使用，蓝牙以及无线已经更新到14.0版本
            <br/>
            ⚠️升级14.4以及以上版本需配置EFI：·Misc - Security - SecurityBootMode : Disabled·
            <br/>
            ⚠️需要将无线网卡升级到14.4版本
        </td>
        <td>
            <img src="images/macOS-14.5.png" border=0 style="margin-top:0px;">
            EFI：macOS-Sonoma-14.4/EFI
            <br/>
            14.4-目前最新版本14.5之间版本可以任意升级，已经更新了蓝牙和无线网卡驱动到最新版本，并且已经处理好SecurityBootMode，更新nvmefix支持到14.5
        </td>
    </tr>
</table>

##### ⚠️应当避免使用的macOS版本
1. macOS 14.4.1 ： [包含 Java 代码的某些应用程序会意外退出｜影响icoud｜生产力不推荐]

##### 🔝推荐的系统版本：
1. Ventura 13.5.1
2. Sonoma 14.3.1
3. Sonoma 14.5

##### ⏩如何在线升级：
1. 小版本升级：可以直接在系统设置 直接更新
2. 大版本升级 推荐：使用 pkg 对应版本的升级包升级
3. 大版本升级：下载对应 dmg 系统包，打开以后有一个安装进行升级

#### 🆓相关资源：
##### 1.macOSpkg升级包
* macOS Sonoma 14.5 (23F79) - 推荐版本
* 
    链接: https://pan.baidu.com/s/1DQ9vFTQPSUv7Xg-wMDT6hg?pwd=4qxa 

    提取码: 4qxa 

    SHA256SUM：包内

* macOS Sonoma 14.3.1 (23D60)
* 
    链接: https://pan.baidu.com/s/1_bTx8A4GdBfaLCLUEh4YzA?pwd=bt4j

    提取码: bt4j 

    SHA256SUM：包内

##### 2.macOSdmg安装包
* macOS Venture 13.5.1 22G90 With opencore 1.9.4 and WinPE

    链接: https://pan.baidu.com/s/1rq-Q5e3-my8gZUX3oZS_Ng?pwd=rv49 

    提取码: rv49 

# 主板型号
TX GAMING B760M，EFI支持 ddr4/ddr5版本

关键字：`华硕天选B760M黑苹果`，`TX B760m Hackintosh`，`TX GAMING B760M WIFI hackintosh`；

<img src="images/tx-b760m.jpg" width=70%>

## opencore : 1.0.0v2 144无线蓝牙网卡版本
![oc-1.0.0](images/oc14.5.png)
## opencore : 0.9.9 版本
![oc-0.9.9](images/oc099.png)
## 支持系统：
1. macOS Sonoma 14
2. macOS Ventura 13
3. macOS Monterey 12

# 使用教程：
通过 [OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools/releases) 工具 打开 菜单 PI 后，生成三码信息导入使用
![三码设置](images/smi.png)
## bios设置
 
| Bios选项名         | 选项     | 必需 |
|--------------------|----------|------|
| VT-d               | Enabled  |      |
| XHCI-Hand-Off      | Enabled  |      |
| Above 4G Decoding  | Enabled  |      |
| Fast Boot          | Disabled |      |
| CSM                | Disabled |      |
| Secure Boot        | Disabled |      |
| Resize Bar Support | Enabled  |      |


## 其他

1. 主板自带网卡驱动信息
因 Sonoma 14 以后，免驱动苹果网卡无法使用，且只支持Wi-Fi5，使用Wi-Fi 6 自带网卡速率更快
![Wi-Fi](images/Wi-Fi.png)
内置无线网卡可以跑满 2400Mbps传输速率
![Wi-Fi-2](images/Wi-Fi-2.png)

2. ACPI信息
如果你是免驱动显卡，可以去掉 SSDT-RX6650XT-TXB760-PC00-PEG1.aml 文件
如果你是仿冒显卡，不同型号，可以使用hackintosh工具中的pcie找到显卡路径
![acpi](images/acpi.png)
3. cpu核心能够正确识别成 16核心 24个线程
![cpu-core](images/cpu-core.png)
大小核处理器均能识别到正确的大小核并且调度
![cpu-core](images/p+e.png)
4. 将 音乐 - 设置 - 播放，流播放：设置成无损
出现无损标志：支持Apple DRM
<img src="images/apple-drm.png" >

5. 日常使用占用
双屏4k，播放影音以及日常办公使用
<img src="images/used.png" >

