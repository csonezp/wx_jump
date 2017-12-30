# 100行以内实现自动玩微信跳一跳游戏

## HOW

- 目前只对android进行了适配，源码中的数据均为1080x1920下
- 连接手机后开启USB调试模式，电脑需要安装adb

## 思路

- 用adb获取手机截图并拉取到项目中
- 对图片进行二值化
- 根据棋子的RGB值获取当前位置
- 按行遍历这张图片，从300行后开始（避免干扰），如果检测到两行数据有差异，说明该位置为菱形顶端
- 获得菱形顶端之后可以计算出目的点的位置
- 两点间距求出距离，换算成adb点按时长，让手机执行

## TODO

- 对各参数进行进一步的微调

## BUG

- 有任何问题请联系我或直接留言
- QQ 178894043