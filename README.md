主板型号
TX GAMING B760M，EFI支持 ddr4/ddr5版本

opencore : 0.9.9 版本

支持系统：
1，macOS Sonoma 14
2，macOS Ventura 13
3，macOS Monterey 12

特性：
1，加入大小核心调度，能够正确识别大核，线程，小核，不会启动应用直接全部占用
   系统优先使用大核，其次小核，再线程
2，直接调用的主板自带因特尔网卡，支持Wi-Fi 6，不需要额外购买网卡
3，如果是免驱显卡可以去掉 6650xt的acpi，如果是仿冒其他驱动，第一插槽的显卡地址为：pc00/peg1

已知问题：
1，自带蓝牙目前没有驱动

bios设置
  VT-d ：Enabled		
  XHCI-Hand-Off ：Enabled
  Above 4G Decoding ： Enabled		
  Fast Boot	： Disabled
  CSM	： Disabled		
  Secure Boot ： Disabled
  Resize Bar Support	： Enabled

加载 kext 信息
<img width="1192" alt="image" src="../ASUS-TX-B760m-hackintosh/assets/24860745/dd45d559-0f43-4e26-9c61-1a94020a852a">

使用教程：
  通过 OCAuxiliaryTools 工具 打开 菜单 PI 后，生成三码信息导入使用
