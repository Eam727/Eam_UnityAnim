##**Unity中的动画**

###**1.普通Animation动画**

Animation界面：

![](https://i.imgur.com/dTLSwHa.png)

备注：

录制模式的红点，开启后为开启关键帧录制模式：
这个模式下，改变当前物体的属性(如场景里拖拽改变位置属性)，会直接在当前帧的动画数据中记录该属性值，作为动画中当前帧的物体状态；而未开启该模式这不会自动记录在动画里。

底部的Dopesheet为关键帧，Curves为动画曲线(可以调整动画加速度)。

![](https://i.imgur.com/Wt5zIXb.gif)


----------


###**2.UGUI的按钮动画**

Button的Animation切换模式

![](https://i.imgur.com/nuRYv9z.png)

用于按钮的点击或者选择动画。

选择Animation后，选择自动生成动画(Unity2017),然后会自动生成AnimatorController和四个状态的动画。可设置正常、悬浮、按下、禁用(Button设置为Interactable为false)四种状态的按钮的动画，然后进入对应事件时切换播放动画。

![](https://i.imgur.com/Ln55osB.gif)


----------


###**3.2D精灵动画**

2D游戏中动画一般使用图片帧动画，如下面一张图切成3份，不停切换形成动画。

![](https://i.imgur.com/HTIfrrp.png)

1/ 图片导入到Unity设置为2D精灵，在SpriteEditor里切图，切成3个精灵。

![](https://i.imgur.com/C41KePq.png)

![](https://i.imgur.com/j5idaXy.png)

2/ 然后选择这几个精灵直接拖拽到Hierarchy面板中，直接生成动画。

可以看到：场景里创建了一个物体，挂了SpriteRenderer组件用于渲染这个2D图，挂了Animator组件用于播放动画。(会使SpriteRenderer里的Sprite不停切换形成动画)

3/ 可以选择物体，打开Animation界面，编辑动画，修改Samples值来改变每秒帧数来改变动画速度。

4/ 我们也可以不拖拽，创建一个Animation选择物体的SpriteRenderer属性进行帧修改就行了。

![](https://i.imgur.com/paB7Zk7.gif)


----------

###**4.骨骼动画 Mecanim动画系统**

**1/ 导入模式**

模型动画导入模式有三种(操作源文件-Rig)：

- Lagacy :旧版本Animation系统,使用后直接使用Animation组件播放动画
- Generic：Mecanim系统，动物骨骼动画(动物/怪物/带披风触角尾巴任务)，动画不可复用;选择后文件下生生成Avatar
- Humanoid：Mecanim系统，人形骨骼动画，动画可以复用；选择后文件下生生成Avatar

**2/ 切割动画**

美术可能把所有动作做在了一个动画上，需要在源文件-Animation切页里裁剪。

![](https://i.imgur.com/6laMkoN.png)

切割完成会在文件下得到动画片段。