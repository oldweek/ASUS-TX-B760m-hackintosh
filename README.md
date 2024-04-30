<img src="images/info.jpg" width=35%>

# 主板型号
TX GAMING B760M，EFI支持 ddr4/ddr5版本
<img src="images/tx-b760m.jpg" width=70%>

## opencore : 0.9.9 版本
![oc-0.9.9](images/oc099.png)

## 支持系统：
1. macOS Sonoma 14
2. macOS Ventura 13
3. macOS Monterey 12

## 更新 2023.4.30：
1. 加入大小核心调度，能够正确识别大核，线程，小核，不会启动应用直接全部占用
   系统优先使用大核，其次小核，再线程
2. 直接调用的主板自带因特尔网卡，支持Wi-Fi 6，不需要额外购买网卡
3. 如果是免驱显卡可以去掉 6650xt的acpi，如果是仿冒其他驱动，第一插槽的显卡地址为：pc00/peg1
4. 有线网卡速率2.5G
5. 去除usb端口限制
6. 已屏蔽核显，核显无法驱动，屏蔽后可以节能

## 已知问题：
1. 自带蓝牙目前没有驱动

除该问题外，其他已经正常使用

## bios设置
  VT-d ：Enabled		
  XHCI-Hand-Off ：Enabled
  Above 4G Decoding ： Enabled		
  Fast Boot	： Disabled
  CSM	： Disabled		
  Secure Boot ： Disabled
  Resize Bar Support	： Enabled

## 加载 kext 信息
![加载的kext信息](images/kext.png)


## 使用教程：
通过 [OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools/releases) 工具 打开 菜单 PI 后，生成三码信息导入使用
![三码设置](images/smi.png)