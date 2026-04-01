# ScreenSpot-Pro

数据集构成：一张图片对应一段json格式的指令描述

工业软件：cad,solidworks,inventor,vivado
![total](./resource/GUI/total.png)
![cad](./resource/GUI/cad.png)

![word](./resource/GUI/word.png)
![json](./resource/GUI/json.png)

前两张图在数据集里是一张完整的图片，实际点击按钮占整个图片很小很小的一部分，比较难看清我就把两块屏幕分开了。
第一张图左上角红框不是数据集中自带的的，是我下载下来之后用程序结合数据集的图片还有json中的bbox标的像素点位置标注的，程序标注的时候我用的是完整的图片

整个数据集的采集过程是实际工程师工作环境，使用双屏工作，右边word文档是工作时看的任务说明，左边是实际使用软件界面，截图是论文团队自己开发的一款后台静默截图工具，工程师按下快捷键，图片就会以一种半透明的形式覆盖在屏幕上，然后工程师再框住自己当前操作的地方，输入指令描述当前操作，然后bbox里的四个数就是第一张图框框的左上角和右下角的横纵坐标，然后就是ui type字段，只要操作的ui有文本信息就是text,否则就是icon类。

IndusGCC

![INDUS01png](./resource/GUI/INDUS_01.png)

![INDUS02png](./resource/GUI/INDUS_02.png)

mouse-event

|     |     |     |     |     |
| --- | --- | --- | --- | --- |
| frame | x   | y   | button | event |
| 134 | 45  | 203 | Button.left | Pressed |
| 142 | 45  | 203 | Button.left | Released |
| 334 | 44  | 288 | Button.left | Pressed |
| 340 | 44  | 288 | Button.left | Released |
| 545 | 787 | 314 | Button.left | Pressed |
| 551 | 787 | 314 | Button.left | Released |
| 729 | 619 | 596 | Button.left | Pressed |
| 735 | 619 | 596 | Button.left | Released |
| 985 | 1111 | 209 | Button.left | Pressed |
| 991 | 1111 | 209 | Button.left | Released |
| 1104 | 613 | 878 | Button.left | Pressed |
| 1108 | 613 | 878 | Button.left | Released |

#

# VideoCAD

数据集构成：视频画面 + 最终结果图 + 关键帧的操作

采集过程：以公开的 DeepCAD 数据集为基础，筛选出一部分CAD 模型作为数据生成的原始标准。然后将每个 CAD 模型的建模工序、几何参数，转换为软件可直接执行的鼠标、键盘操作指令。通过自动化脚本执行操作指令，同步录制操作全过程的界面视频，录制的时候还要记录每一步操作的时间、类型与参数。最后对比生成的CAD模型和原始样本，剔除不合格样本，将合格的视频、操作标注、目标模型图整理为标准化数据，最终得到有效样本，形成完整数据集。
