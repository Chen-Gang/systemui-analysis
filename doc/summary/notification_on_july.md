# Notification功能需求与设计实现文档

内容：
* 项目简介
* 功能需求
* 项目进展
* 存在问题
* 设计实现


# 项目简介
　本项目属于Openthos开源项目的子项目，主要是基于Android SystemUI里面的Notification功能，x86 PC机器的用户实际应用场景，进行界面的深度定制和功能拓展。

# 功能需求
| 完成 	| 描述 	| 模块 	| 完成度 |
| ---- |-------    |:---------|:---------| 
| √ 	| 开始菜单常用软件 | 	界面 |	100% |
| √ 	| 开始菜单app 	| 界面 	| 100% |
| √ 	| 开始菜单电源 	| 界面 	| 95% |
| √ 	| 开始菜单app分类 	界面 	90% |
| √ 	| 状态栏时间 	| 界面 	100% |
| √ 	| 状态栏常用软件 	| 界面 	100% |
| x 	| 状态栏通知栏重置 	| 界面 | 0% |
| x 	| 状态栏输入法扩展 	| 界面 |	0% |
| √ 	| 状态栏WIFI扩展 	| 界面 	| 100% |
| √ 	| 状态栏声音扩展 	| 界面 	| 100% |
| √ 	| 开始菜单常用软件 	| 功能 	| 80% |
| √ 	| 开始菜单展示全部app 	| 功能 | 100% |
| √ 	| 开始菜单搜索 	| 功能 	|100% |
| √ 	| 开始菜单三种排序：使用频率，安装时间，| 名称排序 | 	功能 	100%|
| √ 	| 开始菜单左边常用软件鼠标右键取消 	|功能 |	0% |
| √ 	| 开始菜单右边app鼠标右键可运行可卸载 	| 功能 	0% |
| √ 	| 开始菜单电源：| 关机 | 重启 | 锁平 | 睡眠	| 功能 	90% |
| √ 	| 开始菜单我的电脑 | 设置 | 功能 | 100% |
| √ 	| 状态栏常用软件 | 功能| 100% |

# 项目进展

- 2016/03/21-2016/04/15
  * 刘畅
    * 熟悉Systemui/../starsbar/PhoneStarsbar.java中函数之间的调用关系
    * 在本地实现开始菜单页面原型。
    * 同 陈工 谢工 冯杰 讨论项目页面开发的切入口。

- 2016/04/16-2016/04/30
  * 刘畅
    * 在mutilwindows实现Systemui状态栏位置的重置。* 在本地实现开始菜单展示所有app的功能
  * 陈刚
    * 在陈工的带领下把追加的开始菜单模型及其功能第一次集成到mutilwindows中* 使其页面有了初步的可视效果。

- 2016/05/01-2016/05/15
  * 刘畅
    * 完善了开始菜单展示所有app的功能。
    * 添加我的电脑，设置， 电源（关机，重启，睡眠，锁定，搜索，app分类，常用软件的原型页面 。

- 2016/05/16-2016/05/31
  * 刘畅
    * 实现的function 有我的电脑，设置，电源中的关机，重启，和锁定。

# 存在问题
| 简述  | 类别  | 备注 |
| ---- |------- |:---------|
| 调用系统锁屏功能在同方笔记本T43u 和同方台式机精锐x700无效（待调研） | bug | https://dev.openthos.org/zentao/zentao/bug-view-182.html |
|  开始菜单点击电源弹出的dialog无法覆盖全屏(同多窗口有关待调研) | bug | https://dev.openthos.org/zentao/zentao/bug-view-194.html |
|  Systemui 状态栏中源WIFI逻辑比较复杂需要调研 	| bug | https://dev.openthos.org/zentao/zentao/bug-view-100.html
| Systemui与DocumentsUI 需要进行跨项目数据交互 并变更DocumentsUI数据库的内容 功能难度系数高比较耗时 | bug |	https://dev.openthos.org/zentao/zentao/bug-view-56.html |
| 重置Systemui通知栏 	| 功能 | 功能优先级未开始，需要底层人员协助|
| 扩展Systemui 输入法 	| 功能 |	功能优先级未开始|
| 扩展Systemui 电量 	| 功能 | 功能优先级未开始|

# 设计实现
