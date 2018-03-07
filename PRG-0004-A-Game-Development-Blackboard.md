# Game Development Blackboard

## 2018-03-07 星期三

### 腾讯专家答疑

* [腾讯专家答疑专场（汇总）](http://gad.qq.com/article/detail/38214)

### 网易游戏技术分享

* [网易游戏技术分享](https://blog.coderzh.com/2015/06/28/163GameOpenDay/)

### ECS 架构

* [《守望先锋》架构设计与网络同步 - GAD](http://gad.qq.com/article/detail/28682)
* [浅谈《守望先锋》中的 ECS 架构 - 云风的 BLOG](https://blog.codingnow.com/2017/06/overwatch_ecs.html)

### Unity 框架

* [Unity 游戏框架搭建系列 - GAD](http://gad.qq.com/u/profile/38901#)

### 寻路算法

* [深入理解游戏中的寻路算法](http://gad.qq.com/article/detail/33637)

### 行为树

#### Behavior Tree 行为树

* [基于行为树与状态机的游戏 AI - Unity3D 学习网](http://www.unity.5helpyou.com/3359.html)
* [Unity 行为树 Behavior Designer - CSDN](http://blog.csdn.net/yupu56/article/details/50151527)
* [采用行为树快速开发游戏 AI - 腾讯 GAD](http://gad.qq.com/article/detail/12729#)
* [使用行为树实现游戏 AI - CSDN](http://blog.csdn.net/wangxiong_zh/article/details/50994889)

#### 行为树插件

* [Behaviour Machine](http://www.behaviourmachine.com/)

#### BT-Framework 行为树框架

* [游戏 AI - 行为树 Part1：简介 - 知乎](https://zhuanlan.zhihu.com/indiegamepixel/19890016)
* [游戏 AI - 行为树 Part2：框架 - 知乎](https://zhuanlan.zhihu.com/p/19891875)
* [BT-Framework - GitHub](https://github.com/f15gdsy/BT-Framework)

![](media/15145212909492.jpg)

![](media/15145337019347.jpg)

## 2018-02-20 星期二

### Rigidbody Collision Detection Mode

![](media/15190986566276.jpg)

**Collision Detection**

> Used to prevent fast moving objects from passing through other objects without detecting collisions.

* **Discrete** - Use Discreet collision detection against all other colliders in the scene. Other colliders will use Discreet collision detection when testing for collision against it. Used for normal collisions (This is the default value).
* **Continuous** - Use Discrete collision detection against dynamic colliders (with a rigidbody) and continuous collision detection against static MeshColliders (without a rigidbody). Rigidbodies set to Continuous Dynamic will use continuous collision detection when testing for collision against this rigidbody. Other rigidbodies will use Discreet Collision detection. Used for objects which the Continuous Dynamic detection needs to collide with. (This has a big impact on physics performance, leave it set to Discrete, if you don’t have issues with collisions of fast objects)
* **Continuous Dynamic** - Use continuous collision detection against objects set to Continuous and Continuous Dynamic Collision. It will also use continuous collision detection against static MeshColliders (without a rigidbody). For all other colliders it uses discreet collision detection. Used for fast moving objects.

* [Rigidbody - Unity Manual](https://docs.unity3d.com/Manual/class-Rigidbody.html)
* [Collision Detection: Discrete vs. Continuous vs. Continuous Dynamic - Unity Forums](https://forum.unity.com/threads/collision-detection-discrete-vs-continuous-vs-continuous-dynamic.291818/)

### Rigidbody Interpolate

**Interpolate**	

> Try one of the options only if you are seeing jerkiness in your Rigidbody’s movement.

* **None** - No Interpolation is applied.
* **Interpolate** - Transform is smoothed based on the Transform of the previous frame.
* **Extrapolate** - Transform is smoothed based on the estimated Transform of the next frame.

* [Rigidbody - Unity Manual](https://docs.unity3d.com/Manual/class-Rigidbody.html)

## 2018-02-13 星期二

### Matrix4x4

* [Matrix4x4.MultiplyVector - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Matrix4x4.MultiplyVector.html)
* [Transform.localToWorldMatrix - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Transform-localToWorldMatrix.html)
* [transform的坐标变换注意事项 - iteye](http://superherosk123.iteye.com/blog/1900505)
* [World, View and Projection Transformation Matrices](http://www.codinglabs.net/article_world_view_projection_matrix.aspx)
* [Tutorial 3 : Matrices](http://www.opengl-tutorial.org/beginners-tutorials/tutorial-3-matrices/)

## 2018-02-03 星期六

### C# 的委托：delegate Action Func predicate

* [Action<T> 委托 - MSDN](https://msdn.microsoft.com/zh-cn/library/018hxwa8(v=vs.110).aspx)
* [Func<T, TRusult> 委托 - MSDN](https://msdn.microsoft.com/zh-cn/library/bb549151(v=vs.110).aspx)
* [C#委托的介绍(delegate、Action、Func、predicate) - cnblogs](http://www.cnblogs.com/akwwl/p/3232679.html)
* [C#之Action和Func的用法 - cnblogs](https://www.cnblogs.com/LipeiNet/p/4694225.html)

* delegate 是最常用的一种委托，至少0个参数，至多32个参数，可以无返回值，也可以指定返回值类型。
* Action 是无返回值的泛型委托。
* Func 是有返回值的泛型委托。
* predicate 是返回 bool 型的泛型委托。

### struct & class

* [C# 中 Struct 与 Class 的区别，以及两者的适用场合 - cnblogs](http://www.cnblogs.com/waitrabbit/archive/2008/05/18/1202064.html)

* class 是引用类型，struct 是值类型
* class 有面向对象的扩展优势，struct 有性能优势
* 将用于底层数据存储的类型设计为 struct，而将用于定义应用程序行为的类型设计为 class；如果对类型将来的应用情况不确定，应将其设计为 class

## 2018-01-27 星期六

### Transform.parent & Transform.SetParent

**Transform.parent**

> The parent of the transform.
> Changing the parent will modify the parent-relative position, scale and rotation but keep the world space position, rotation and scale the same.

**Transform.SetParent**

> Set the parent of the transform.
> This method is the same as the parent property except that it is possible to make the Transform keep its local orientation rather than its global orientation. This is managed by setting the worldPositionStays parameter to false. When SetParent is called with only the single Transform argument the worldPositionStays argument is set to true.

## 2018-01-17 星期三

### 技能系统设计

* [从技能设计复杂度及定位谈被动技能 - GameRes](http://bbs.gameres.com/thread_328718_1_1.html)

* [如何设计一个易扩展的游戏技能系统？- 知乎](https://www.zhihu.com/question/29545727)

**技能系统核心功能有两个，一个是定义表现流程，一个是处理逻辑效果。**
所谓表现流程就是角色在什么时候播放什么动画、特效、音效，什么时候判定伤害，什么时候发射抛射物。
所谓逻辑效果就是技能给目标造成多少伤害，附加什么buff/debuff效果。在我设计的技能系统中，核心基础是lua脚本，通过lua脚本处理复杂的技能逻辑。

基础内容有这么几个部分：

* **Actor**，这个是角色本身，它不属于技能系统，但是它要给技能系统开放足够的接口，比如播放动画、播放声音、控制位移、造成伤害、添加buff等等
* **Skill**，这个就是技能本身，它在合适的时机调用脚本中的相应函数，脚本中可以在OnCreate  OnHit  OnDeath  OnHeroDeath  OnSoldierDeath等事件中写相应代码。由于是脚本，所以代码非常灵活，而由于限定了只处理技能相关功能，所以代码也不会很复杂，有经验的策划绝对搞的定。
* **Buff**，这个是技能效果的核心。它可以是有时限的，也可以是被动无时限的。在它对应的脚本中，定义了这个Buff会影响哪些角色属性（如血量、暴击、攻击力等等）或者角色状态（如眩晕、隐身、沉默等等），同样，buff脚本也支持事件机制，在脚本的相应事件处理其逻辑功能，可以实现非常丰富的效果。
* **Modifier**，这个是一个技能修改器。技能修改器可以修改技能的流程和效果（比如技能伤害增加、火球击中人会爆炸等等），具体可以参考风暴英雄中的技能天赋系统。技能修改器并没有脚本与之对应，一个技能如果支持某个修改器，需要在脚本中处理相应功能。

* [Buff 机制及其实际运用 - GameRes](http://bbs.gameres.com/forum.php?mod=viewthread&tid=215027)

Buff 是一种回调机制，在必要的时候进行逻辑回调。
Buff 回调点：

1. BuffOccur
2. BuffOnTick
3. BuffRemoved
4. BuffBeHurt
5. BuffOnHit
6. BuffBeforeKilled
7. BuffAfterKilled

* [通用型buff机制在实战中的运用 - GameRes](http://bbs.gameres.com/thread_454153.html)

1、Buff 在同一款游戏中并非只能有一套
2、Buff 机制并非只能在 ARPG 中使用
3、现实生活中也有 Buff 机制的落脚点

* [游戏 BUFF 设计 - cnblogs](http://www.cnblogs.com/damowang/p/5799967.html)

总体上来说，BUFF/DEBUFF都属于“临时的技能效果”，因此它们可以沿用绝大部分的技能逻辑对角色进行程序处理。

设计一个BUFF/DEBUFF机制，需要考虑这么几个要点：

内部运算：
1、是否包含技能效果？（提高/降低 攻击 命中 闪避 移动速度  群体伤害 替换技能ID 等 ）
2、是否包含阶段效果？（BUFF分为多个阶段，不同的阶段有不同的效果，比如影之哀伤）
3、是否包含计时器？（持续时长计算、叠加时长计算 总之所有关于持续性时间的问题 都丢这里）
4、是否包含计数器？（用来计算阶段、剩余生效次数、比如影之哀伤 LOL电刀）
5、是否具备分类规则？（魔法效果 诅咒效果 中毒效果 用于进行归类 方便程序进行的 驱散筛选判断）
6、是否可以被驱散？ （魔法效果只能用祛除魔法解除 中毒效果只能用解药祛除）
7、是否具备优先级？（附加优先级，低等级BUFF会被高等级BUFF替换，低等级BUFF无法附加给高等级怪）
8、是否保留母体信息？（比如传染性的DEBUFF，感染者传播一次，母体会获得额外巴拉巴拉。。。多个项）
9、是否共享同步规则？（比如多个角色共享一个BUFF状态，一个人的BUFF被祛除则其他人也被祛除）
10、以上功能可以进行再补充，没有需求则可以逐个剔除。

外部表现：
1、是否显示BUFF图标？（传奇里道士的BUFF是不显示图标的）
2、是否不同阶段表现不同的图标？
3、是否显示计时器？
4、是否显示计数器？
5、是否显示BUFF文字说明？（对BUFF类型、效果的描述）
6、是否改变角色外形？（DNF里的冰冻、WOW里的变形）
7、以上表现功能可以进行再补充，同上。

* [策划公式的 DSL 设计 - 云风的 BLOG](https://blog.codingnow.com/2012/01/dev_note_8.html)
* [AOE机制的DSL及其实际运用 - GameRes](http://bbs.gameres.com/forum.php?mod=viewthread&tid=225054)

* [不要用海量表项压垮“技能流程” - GameRes](http://bbs.gameres.com/thread_229210_1_1.html)

技能，说穿了只是一个流程，而不该是一个实体。

* [游戏开发笔记（九）——技能系统 - CSDN](http://blog.csdn.net/mooke/article/details/9771545)

对于技能系统这个比较大的主题，通常要先拆小了来分析。也许不太恰当，但姑且先分为动作表现、技能逻辑和伤害判定这三块吧。

### 判断动画是否播放结束

* [Unity Animator 怎么判断一个动画播放结束 - cnblog](http://www.cnblogs.com/mimime/p/6599798.html)
* [AnimatorStateInfo.normalizedTime - Unity Scripting API](https://docs.unity3d.com/ScriptReference/AnimatorStateInfo-normalizedTime.html)

**三种方法：**

* FBX -> Animations -> Clips -> Events -> Add Event
* Animator -> Exit Time
* AnimatorStateInfo.normalizedTime

## 2018-01-16 星期二

### Rotating an object in relation to its velocity

Rigidbody 的转向跟随其速度方向的实现采用这种方法：
* [Rotating gameobject to velocity - Unity Answers](https://answers.unity.com/questions/293282/rotating-gameobject-to-velocity.html)

* [Rotating an object in relation to its velocity - StackExchange](https://gamedev.stackexchange.com/questions/99244/unity-3d-rotating-an-object-in-relation-to-its-velocity)
* [How to rotate object in unity3d using Rigidbody](http://www.cuelogic.com/blog/how-to-rotate-object-in-unity3d-using-rigidbody/)
* [Rotating an object in relation to its velocity](https://gamedev.stackexchange.com/questions/99244/unity-3d-rotating-an-object-in-relation-to-its-velocity)
* [发射弓箭轨迹的实现](http://www.cnblogs.com/jqg-aliang/p/4806002.html)

### 物体移动方式

* [物体移动方式总结 - CSDN](http://blog.csdn.net/MyArrow/article/details/45846567)

## 2018-01-13 星期六

### Collider or Trigger?

**Collider 和 Trigger 的区别？OnCollisionEnter 和 OnTriggerEnter 的区别？**

* [Collider.OnCollisionEnter - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Collider.OnCollisionEnter.html)

> OnCollisionEnter is called when this collider/rigidbody has begun touching another rigidbody/collider.
> In contrast to OnTriggerEnter, OnCollisionEnter is passed the Collision class and not a Collider. The Collision class contains information about contact points, impact velocity etc. If you don't use collisionInfo in the function, leave out the collisionInfo parameter as this avoids unneccessary calculations. Notes: Collision events are only sent if one of the colliders also has a non-kinematic rigidbody attached. Collision events will be sent to disabled MonoBehaviours, to allow enabling Behaviours in response to collisions.

* [Collider.OnTriggerEnter - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Collider.OnTriggerEnter.html)

> OnTriggerEnter is called when the Collider other enters the trigger.
> This message is sent to the trigger Collider and the Rigidbody (if any) that the trigger Collider belongs to, and to the Rigidbody (or the Collider if there is no Rigidbody) that touches the trigger. Notes: Trigger events are only sent if one of the Colliders also has a Rigidbody attached. Trigger events will be sent to disabled MonoBehaviours, to allow enabling Behaviours in response to collisions. OnTriggerEnter occurs on the FixedUpdate after a collision. The Colliders involved are not guaranteed to be at the point of initial contact.
> Note: OnTriggerEnter is not technically part of Collision. It is a MonoBehaviour function.

### readonly

* [readonly - C# Reference](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/readonly)

> The `readonly` keyword is a modifier that you can use on fields. When a field declaration includes a `readonly` modifier, assignments to the fields introduced by the declaration can only occur as part of the declaration or in a constructor in the same class.

* [What are the benefits to marking a field as `readonly` in C#? - stack overflow](https://stackoverflow.com/questions/277010/what-are-the-benefits-to-marking-a-field-as-readonly-in-c)

> The `readonly` keyword is used to declare a member variable a constant, but allows the value to be calculated at runtime. This differs from a constant declared with the `const` modifier, which must have its value set at compile time. Using `readonly` you can set the value of the field either in the declaration, or in the constructor of the object that the field is a member of.
> Also use it if you don't want to have to recompile external DLLs that reference the constant (since it gets replaced at compile time).

## 2018-01-11 星期四

### 坐标系转化

* [坐标系转化](https://li-kang.gitbooks.io/unity-concise-course/content/Summary/coordinate.html)

### 弧度与角度

* [Radian - 维基百科](https://en.wikipedia.org/wiki/Radian)
* [Why convert degrees to radians?](https://answers.unity.com/questions/989535/why-convert-degrees-to-radians.html)

![](media/15156578153800.gif)

### float 值是否相等判定

* [Mathf.Approximately - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Mathf.Approximately.html)

## 2018-01-04 星期四

### 雾效

* [Unity 雾效的开启](http://blog.csdn.net/Rhett_Yuan/article/details/54425236)
* [Unity 体积雾 Shader](http://www.ceeger.com/forum/read.php?tid=3132)
* [ShadowGun 系列之二——雾和体积光](http://blog.csdn.net/candycat1992/article/details/42061701)

### Sublime Text 文本不换行显示

* [Sublime 小技巧：文本自动换行显示？- 简书](https://www.jianshu.com/p/c75d21d2e967)

```
"word_wrap": "false"
```

### 自定义宏

* [常用宏的介绍与如何自定义宏](http://www.u3d8.com/?p=818)
* [C#怎么进行宏定义？](http://bbs.csdn.net/topics/390638754)

## 2017-12-27 星期三

### 物理引擎碰撞检测 & 网络编程算法

* 《实时碰撞检测算法技术》
* 《Algorithms and Networking for Computer Games》
* [CS4344: Networked and Mobile Games](https://www.comp.nus.edu.sg/~ooiwt/cs4344/archives/0708s1/)

## 2017-12-24 星期日

### NGUI 自适应屏幕

* [NGUI研究院之自适应屏幕](http://www.xuanyusong.com/archives/2536)

## 2017-12-23 星期六

### Inspector 中的脚本勾选框

* 当脚本中存在 Start/Update/FixedUpdate/LateUpdate/OnGUI 等 MonoBehaviour 方法时，该勾选框会显示，反之不会显示，即使存在 Awake 方法也不会显示。

* [为什么Inspector视图中脚本前面的勾选框没了](http://www.xuanyusong.com/archives/3130)

### Animator.CrossFade

* [Animator.CrossFade - Unity Scripting API](https://docs.unity3d.com/ScriptReference/Animator.CrossFade.html)
* [记一次Animator状态快速切换问题的解决 - cnblogs](http://www.cnblogs.com/hont/p/5196485.html)
* [Unity中使用Animation提高Animator的性能](http://georgejin.me/2016/09/09/Unity%E4%B8%AD%E4%BD%BF%E7%94%A8Animation%E6%8F%90%E9%AB%98Animator%E7%9A%84%E6%80%A7%E8%83%BD/)

## 2017-12-06 星期三

### 游戏程序团队分工

一种游戏程序团队可能的分工


## 2017-12-04 星期一

### 逻辑帧与渲染帧

* [游戏主循环 - cnblog](http://www.cnblogs.com/kekec/p/3670389.html)

### 性能优化

* [深入浅出聊优化：从Draw Calls到GC](http://www.cnblogs.com/murongxiaopifu/p/4284988.html)
* [再议 Unity 优化 - 知乎](https://zhuanlan.zhihu.com/p/26763624)

* [Unity性能优化大合集，All In One !（更新至8.18）](https://blog.uwa4d.com/archives/allinone.html)

* [性能优化，永无止境---CPU篇](https://blog.uwa4d.com/archives/optimzation_cpu.html)
* [性能优化，进无止境-内存篇（上）](https://blog.uwa4d.com/archives/optimzation_memory_1.html)
* [性能优化，进无止境-内存篇（下）](https://blog.uwa4d.com/archives/optimzation_memory_2.html)

* [Unity中的优化技术 - CSDN 博客](http://blog.csdn.net/candycat1992/article/details/42127811)

## 2017-12-02 星期六

### Audio

* Audio Reverb Zones 音频混响区的概念和用法没弄明白？（直接看 Unity Manual 吧）

## 2017-12-01 星期五

### 游戏程序员之路 
* [游戏程序员养成计划 - cnblog](http://www.cnblogs.com/clayman/archive/2009/05/17/1459001.html)

### Shader

* [Unity3D Shader入门指南（一）](https://onevcat.com/2013/07/shader-tutorial-1/)
* [Unity3D Shader入门指南（二）](https://onevcat.com/2013/08/shader-tutorial-2/)[Shader Part 1 - UnityGems](https://unitygem.wordpress.com/shader-part-1/)
* [Surface Shader examples - Unity Manual](https://docs.unity3d.com/Manual/SL-SurfaceShaderExamples.html)
* [Materials, Shaders & Textures - Unity Manual](https://docs.unity3d.com/Manual/Shaders.html)
* [初探Surface Shader背后的机制 - CSDN](http://blog.csdn.net/candycat1992/article/details/39994049)
* [如何系统的学习 Unity 3D 中的 shader 编写（nvidia cg 编程）？- 知乎](https://www.zhihu.com/question/21451211)

## 2017-11-22 星期三

### iOS 项目编译错误

编译 iOS 项目时报以下错误，可能与 Unity IAP 的 bug 有关，删除项目中的 link.xml 即可编译成功，其他设置无须改动。

```
Failed running /Applications/Unity/Unity.app/Contents/il2cpp/build/UnityLinker.exe --api=NET_2_0_Subset
```

* [Unity2017.2 : build error : UnityLinker.exe did not run properly!](https://forum.unity.com/threads/unity2017-2-build-error-unitylinker-exe-did-not-run-properly.485006/)
* [ios build error on macos "UnityLinker.exe did not run properly!"](https://forum.unity.com/threads/ios-build-error-on-macos-unitylinker-exe-did-not-run-properly.486265/)
* [iOS build error after update to 2017.1.0f3](https://answers.unity.com/questions/1394481/ios-build-error-after-update-to-201710f3.html)

## 2017-11-19 星期日

### UGUI RectTransform

* [RectTransform 详解 - 简书](http://www.jianshu.com/p/dbefa746e50d)
* [How to calculate sizeDelta in RectTransform?](https://stackoverflow.com/questions/44471568/how-to-calculate-sizedelta-in-recttransform)
* [RectTransform.sizeDelta](https://docs.unity3d.com/ScriptReference/RectTransform-sizeDelta.html)

* 将 Android SDK 的 tools 降级为 tools_r25.2.5-windows.zip 即可。
* 同时 JDK 使用 1.8 版本，而不是 1.7 或 1.9。

### 编译 Android 失败

* [Unable to list target platforms. Please make sure the android sdk path is correct. See the Console for more details.](https://answers.unity.com/questions/1323731/unable-to-list-target-platforms-please-make-sure-t.html)
* [Build apk 失败](https://ukyoappdev.blogspot.jp/2017/05/unityandroid-sdk-toolsbuild-apkafter.html)
* [Unable to list target platforms](http://www.jianshu.com/p/fe4c334ee9fe)

### idea 编译项目错误

* [编译报错，javacTask:源发行版1.8需要目标发行版1.8](http://download.oracle.com/otn-pub/java/jdk/8u152-b16/aa0333dd3019491ca4f6ddbe78cdb6d0/jdk-8u152-windows-x64.exe?AuthParam=1511150650_dfc5d83b121b76d58e82c4b2679486dc)

## 2017-11-17 星期五

### Unity 配置文件读取

```csharp

// 读取配置
NetworkConfig networkConfig = Resources.Load<NetworkConfig>("NetworkConfig");
Debug.Log(networkConfig.Host + ":" + networkConfig.Port);
```

## 2017-10-31 星期二

### DDL for game database

```
CREATE TABLE `user` (
  `id` varchar(32) NOT NULL,
  `pw` varchar(32) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8

CREATE TABLE `player` (
  `id` varchar(32) NOT NULL,
  `data` blob,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8
```

## 2017-09-28 星期四

### 帧同步技术问答

* [【腾讯专家答疑专场】帧同步技术解答精选](http://gad.qq.com/article/detail/33704?sessionUserType=BFT.PARAMS.237718.TASKID&ADUIN=494074276&ADSESSION=1506562461&ADTAG=CLIENT.QQ.5527_.0&ADPUBNO=26632)

* 《实时碰撞检测算法技术》

我们真做了一个通用框架来帮助开发同学检测和分析不一致性，原理上大致如下：
1.定义个逻辑帧状态的切片（FrameStateSnapshot），帧切片里面是游戏对象的状态以及本帧发生的事件。
2.每个逻辑帧跑完，生成本帧的切片
3.将帧切片序列化成一个二进制串
4.可选：将二进制串生成MD5
5.可选：将MD5码和帧序号发送给服务器，服务器可以通过这个MD5码判定每个客户端的帧切片是不是一致
6.将帧切片的二进制串保存到本地文件（也可以带MD5）
7.打完一场之后，生成了一个状态录制文件
比较各个客户端所录制的这些数据，可以知道哪帧不一致，这个帧里面哪个数据不一致了。

## 2017-09-19 星期二

### ASCII 码表

* [ASCII - 百度百科](https://baike.baidu.com/item/ASCII)

### Frame Sync

* [帧同步的初步探究](https://musoucrow.github.io/2017/08/26/frame_sync/)

## 2017-09-15 星期五

### C# decompile
* [推荐.Net、C# 逆向反编译四大工具利器](http://blog.csdn.net/kongwei521/article/details/54927689)

## 2017-09-12 星期二

### MVC & MVVM & Unity 项目架构

* [PureMVC](http://puremvc.org/)

* [StrangeIoC](https://strangeioc.github.io/strangeioc/index.html)

![](media/15052143407916.png)

* [Unity应用架构设计(1)—— MVVM 模式的设计和实施(Part 1)](http://www.cnblogs.com/OceanEyes/p/unity3d_framework_designing_get_started_with_mvvm_part1.html)

* [浅谈Unity开发中的分层设计](https://zhuanlan.zhihu.com/p/28401100)

## 2017-09-11 星期一

### Splatoon

* [Splatoon GamePlay](https://www.youtube.com/watch?v=-7DVixaWbWo)

### Client-Server Game Architecture

* [Fast-Paced Multiplayer](http://www.gabrielgambetta.com/)
* [Doom3](https://github.com/TTimo/doom3.gpl)

## 2017-09-09 星期六

### uFrame

* [uFrame](https://www.assetstore.unity3d.com/cn/#!/content/14381)

## 2017-09-07 星期四

### Unity 图文插件

TextMesh
Drawcall

## 2017-09-06 星期三

### Bombermaaan

* [Bombermaaan game project on sourceforge.net](http://bombermaaan.sourceforge.net/)
* [Bombermaaan - GitHub](https://github.com/bjaraujo/Bombermaaan)

### UML

* [UML 类图中各种关系总结](http://www.open-open.com/lib/view/open1328059700311.html)

## 2017-09-04 星期一

### Unity Trick

**在 Scene 视图中快速无缝拼接贴图或者物体：**

* 转中一个 GameObject
* 按下住 `V` 键（Vertex 顶点的意思），鼠标移动到就近顶点会自动选中
* 拖动被选中顶点（保持 `V` 键按下），将其拖动到要拼接的顶点处
* Unity 会自动将这两个顶点无缝拼接在一起
* 这个小技巧在做「滚动背景」时很有效

* [为游戏开发者总结的20个最好的 Unity 建议和技巧](http://imgtec.eetrend.com/forum/10259)
* [Unity 小技巧介绍](http://imgtec.eetrend.com/blog/7818)

**让粒子系统跟随 GameObject 旋转：**

* [How can I rotate a particle effect?](http://answers.unity3d.com/questions/762742/how-can-i-rotate-a-particle-effect.html)

```csharp
thrust_flare.particleSystem.startRotation = gameObject.transform.rotation.eulerAngles.y * Mathf.Deg2Rad;
```

**Unity 平台依赖编译：**

* [Platform dependent compilation](https://docs.unity3d.com/Manual/PlatformDependentCompilation.html)

## 2017-08-31 星期四

### mysql

* [mysql 安装](http://www.runoob.com/mysql/mysql-install.html)

**Windows 上安装Mysql**

Windows上安装Mysql相对来说会较为简单，你只需要在 MySQL 下载中下载windows版本的mysql安装包，并解压安装包。
双击 setup.exe 文件，接下来你只需要安装默认的配置点击"next"即可，默认情况下安装信息会在C:\mysql目录中。
接下来你可以通过"开始" =》在搜索框中输入 " cmd" 命令 =》 在命令提示符上切换到 C:\mysql\bin 目录，并输入一下命令：

```
mysqld.exe --console
```

如果安装成功以上命令将输出一些mysql启动及InnoDB信息。

**TCP/IP port：3306**

![](media/15041662488290.png)

## 2017-08-30 星期三

### Socket.Receive

Socket 客户端的接收字节流的方法，可以自动读取流中所有的可用数据（一个长度不确定的消息包的所有字节），前提是用于接收的字节数组 byte[] 大小够大（或者 ByteBuffer）：

* [C# API](https://docs.microsoft.com/en-us/dotnet/api/system.net.sockets.socket.receive?view=netframework-4.7#System_Net_Sockets_Socket_Receive_System_Byte___)

```csharp
// Socket.​Receive
public int Receive (byte[] buffer);
// Returns: The number of bytes received.
```

* [Java API](https://docs.oracle.com/javase/7/docs/api/java/io/InputStream.html)

```java
// java.io.InputStream
public int read(byte[] b) throws IOException
// Returns: the total number of bytes read into the buffer, or -1 if there is no more data because the end of the stream has been reached.
```

## 2017-08-24 星期四

### Using VS with Unity - Trouble Shooting 

* [Unity keeps opening new instances of Microsoft Visual Studio](http://answers.unity3d.com/questions/1078859/unity-keeps-opening-new-instances-of-microsoft-vis.html)

## 2017-08-18 星期五

### Lua Editor

Lua 编辑器：ZeroBrane Studio

## 2017-08-17 星期四

### 热更新

* **热更新的原理和过程：**
	⁃	其实做热更的步骤不麻烦，因为Unity的c#类部分热更不了，那我们需要热更的就只有Lua代码部分了，当我们写完游戏测试OK了，就可以上线运营，并且在Web服务器上面部署最新的版本资源文件，我们就可以将Lua的代码编码后上传到Web服务器上面去，当游戏客户端启动的时候，它会启动解包流程、解包的资源一般都是当时做包时候的资源，到后面我们修改以后，它内部的资源可能已经不是最新的了，但是大部分可能是新的，只有少部分需要更新，那紧接着就启动更新流程，从Web服务器上面的资源配置列表里面，通过MD5/CRC比较查询到最新的资源，下载更新本地的文件，达到更新最新版的目的，游戏顺利启动。

接下来便要尝试代码热更新，让程序下载服务器上的lua文件，然后运行它。在说明热更新之前，需要先看看Unity3D热更新的一般方法。如下图所示，Unity3D的热更新会涉及3个目录。

![](media/15030289649578.jpg)

**﻿热更新的过程：**

**游戏资源目录**：里面包含Unity3D工程中StreamingAssets文件夹下的文件。安装游戏之后，这些文件将会被一字不差地复制到目标机器上的特定文件夹里，不同平台的文件夹不同，如下所示（上图以windows平台为例）

Mac OS或Windows：Application.dataPath + "/StreamingAssets";

IOS： Application.dataPath + "/Raw";

Android：jar:file://" + Application.dataPath + "!/assets/";

**数据目录**：由于“游戏资源目录”在Android和IOS上是只读的，不能把网上的下载的资源放到里面，所以需要建立一个“数据目录”，该目录可读可写。第一次开启游戏后，程序将“游戏资源目录”的内容复制到“数据目录中”（步骤1，这个步骤只会执行一次，下次再打开游戏就不复制了）。游戏过程中的资源加载，都是从“数据目录”中获取、解包（步骤3）。不同平台下，“数据目录”的地址也不同，LuaFramework的定义如下：

Android或IOS：Application.persistentDataPath + "/LuaFramework"    

Mac OS或Windows：c:/LuaFramework/

调试模式下：Application.dataPath + "/StreamingAssets/"

注：”LuaFramework”和”StreamingAssets”由配置决定，这里取默认值

**网络资源地址**：存放游戏资源的网址，游戏开启后，程序会从网络资源地址下载一些更新的文件到数据目录。

这些目录包含着不同版本的资源文件，以及用于版本控制的files.txt。Files.txt的内容如下图所示，里面存放着资源文件的名称和md5码。程序会先下载“网络资源地址”上的files.txt，然后与“数据目录”中文件的md5码做比较，更新有变化的文件（步骤2）。

![](media/15030290098812.jpg)
files.txt

LuaFramework的热更新代码定义在Assets\LuaFramework\Scripts\Manager\GameManager.cs，真正用到项目时可能还需少许改动。

## 2017-08-15 星期二

### pbc

在 macOS 中编译 pbc

https://github.com/cloudwu/pbc/issues/97

## 2017-08-10 星期四

* [炸弹小分队](http://www.iqiyi.com/w_19ru4qh3uh.html)

* [zlib](http://www.zlib.net/)

## 2017-08-07 星期一

### 网络游戏编程资料

http://www.gad.qq.com/article/detail/28052

-------




