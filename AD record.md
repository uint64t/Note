# AD record

## AD19 官方设计指南

* 可以设置单一'\\'符号代表负信号
  * Preference -> Schematic -> Graphical Editing -> Options
* 建议设置光标类型为 Large Curcor 90
  * Preference -> Schematic -> Graphical Editing -> Cursors
* 在区域内排列器件
  * 快捷键 I+L
* F5 打开网络颜色开关
* 布线的环路最小原则
  * 信号线与其环路构成的环面积要尽可能小，环路越小，对外辐射越小，接收外界的干扰也越小
* 选择框可视区域外的器件
  * Edit -> Select -> Outside Area, or shotcut E+S+O
* From-To Editor in PCB panel(what is this)
* Mark 点
  * Mark 点的优选形状为直径 1mm(+/-0.2mm) 的实心圆，开窗。
  * Mark 点不该有 Paste 开窗，Mark 点的空旷区域（Solder Layer）的直径应是 Mark 点直径的三倍
* 布线状况下按 Shift+W 可选择推荐线宽

## Others

### BOM

PartType = Comment

BOM 生成的数据排列方式会与窗口排列的方式完全一样, 而使用 BOM Template 的话, 可以选择性取数据, 因此可以利用一些参数进行排序, 后直接将数据输出. 并且使用 Template 的好处是可以提前进行单元格规划

在 BOM Template 中可使用的参数

https://www.altium.com/documentation/altium-designer/including-design-data-in-the-excel-bom-ad?version=18.1