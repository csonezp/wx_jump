# 100行以内实现自动玩微信跳一跳游戏

- 建议以master分支上的版本为准，100行版本比较投机，不是很严谨
- 100行版本请见分支‘100’

## HOW

- 目前只对android进行了适配，源码中的数据均为1080x1920下，可能需要微调参数
- 连接手机后开启USB调试模式，电脑需要安装adb
- 打开微信-跳一跳小游戏，点击开始游戏
- 运行wx_jump_py27.py即可

效果如图

 ![image](https://github.com/williamfzc/wx_jump/raw/master/demo.jpg)

## 思路

- 用adb获取手机截图并拉取到项目中
- 对图片进行二值化
- 根据棋子的RGB值获取当前位置
- 按行遍历这张图片，从300行后开始（避免干扰），如果检测到两行数据有差异，说明该位置为菱形顶端
- 获得菱形顶端之后可以计算出目的点的位置
- 两点间距求出距离，换算成adb点按时长，让手机执行

## TODO

- 新定位算法对特殊图形仍有计算误差
- 整型计算感觉会有不小误差

## BUG

- 有任何问题请联系我或直接留言