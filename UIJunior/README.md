UI初级整理
===
> 整理的相关方法基于Xcode7.2.1版本中的文档。

<!-- /MarkdownTOC -->

- [01 iPhone 开发入门](#01-iphone-开发入门)
	- [一. 项目文件释义](#一-项目文件释义)
	- [二. 基本设置](#二-基本设置)
	- [三. 常用基本操作](#三-常用基本操作)
	- [四. 应用程序的生命周期](#四-应用程序的生命周期)
- [02 窗口与视图](#02-窗口与视图)
	- [一. 窗口与视图：](#一-窗口与视图：)
	- [二. 窗口的创建](#二-窗口的创建)
	- [三. 视图的创建](#三-视图的创建)
	- [四. 视图的层次结构](#四-视图的层次结构)
	- [五. UIView的常用方法](#五-uiview的常用方法)
	- [六. 查找子视图](#六-查找子视图)
	- [七. UIView的常用属性](#七-uiview的常用属性)
	- [八. 坐标系统变换\(实现视图的简单变换\)](#八-坐标系统变换实现视图的简单变换)
	- [九. UIView属性的动画](#九-uiview属性的动画)
	- [十. 配置动画参数](#十-配置动画参数)
- [03 常用UI控件](#03-常用ui控件)
	- [一. UILabel文本标签](#一-uilabel文本标签)
	- [二. UIControl](#二-uicontrol)
	- [三. UIButton按钮](#三-uibutton按钮)
	- [四. UITextField文本输入](#四-uitextfield文本输入)
	- [五. UIImageView图像视图](#五-uiimageview图像视图)
	- [六. UISlider滑块](#六-uislider滑块)
	- [七. UIActivityIndicatorView](#七-uiactivityindicatorview)
	- [八. UIPageControl分页控件](#八-uipagecontrol分页控件)
	- [九. UIAlertView提示框](#九-uialertview提示框)
	- [十. UIActionSheet功能菜单](#十-uiactionsheet功能菜单)
- [04 视图控制器](#04-视图控制器)
	- [一. UIViewController介绍](#一-uiviewcontroller介绍)
	- [二. UIViewController的创建](#二-uiviewcontroller的创建)
	- [三.  视图的加载](#三--视图的加载)
	- [四. 设置模拟器支持方向旋转](#四-设置模拟器支持方向旋转)
	- [五. 模态视图](#五-模态视图)
	- [六. 小问题](#六-小问题)
- [05 导航控制器](#05-导航控制器)
	- [一. 导航控制器\(UINavigationController\)的基本概念](#一-导航控制器uinavigationcontroller的基本概念)
	- [二. 实现导航控制器](#二-实现导航控制器)
	- [三. 常用方法](#三-常用方法)
	- [四. 导航栏的基本概念](#四-导航栏的基本概念)
- [06 标签控制器](#06-标签控制器)
	- [一. 标签控制器基本概念](#一-标签控制器基本概念)
	- [二. 标签控制器的创建](#二-标签控制器的创建)
	- [三. 代理方法](#三-代理方法)
	- [四. UITabBar视图的组成](#四-uitabbar视图的组成)
	- [五. 定制UITabbar](#五-定制uitabbar)
	- [六. UITabbar的设置](#六-uitabbar的设置)
- [07 表视图](#07-表视图)
	- [一. 表视图的基本概念](#一-表视图的基本概念)
	- [二. 表视图的简单创建](#二-表视图的简单创建)
	- [三. 表视图调用顺序—委托方法](#三-表视图调用顺序—委托方法)
	- [四. 表视图的构成](#四-表视图的构成)
	- [五. 数据源方法和委托方法](#五-数据源方法和委托方法)
	- [六. 单元格复用](#六-单元格复用)
	- [七. 单元格UITableViewCell常用属性](#七-单元格uitableviewcell常用属性)
	- [八. 单元格高度自适应核心代码](#八-单元格高度自适应核心代码)
- [08 表视图控制器](#08-表视图控制器)
	- [一. 基本概念](#一-基本概念)
	- [二. 单元格类型](#二-单元格类型)
	- [三. 自定义单元格](#三-自定义单元格)
	- [四. 表视图的编辑模式](#四-表视图的编辑模式)
	- [五. 多选模式](#五-多选模式)
	- [六. 过滤表格内容](#六-过滤表格内容)
- [09 滑动视图](#09-滑动视图)
	- [一. 基本概念](#一-基本概念-1)
	- [二. 创建](#二-创建)
	- [三. 常用属性](#三-常用属性)
	- [四. 常用代理方法](#四-常用代理方法)

<!-- /MarkdownTOC -->

## 01 iPhone 开发入门
#### 一. 项目文件释义
- Supporting Files
	- plist 文件: 应用程序相关设置（属性）的文件
	- strings文件: 设置应用程序本地化的文件
	- main.m: 程序的入口
	- pch文件: 程序的预处理文件

- Frameworks
	- 存放框架位置

- Products
	- 应用程序执行文件

#### 二. 基本设置
- 设置应用程序的图片
	- Icon.png
	- Icon@2x.png

- 设置启动页面
	- Default.png
	- Default@2x.png
	- Default-568h@2x.png

#### 三. 常用基本操作

Function | Order
--- | ---
Home键 | Command + Shift + H
旋转设备 | Command + 方向键
锁定屏幕 | Command + L
屏幕快照 |  Command + S
通话时状态栏呼出 | Command + Y

#### 四. 应用程序的生命周期

```objectivec
// UIApplication对象实例化, 程序启动时首先调用的方法
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    return YES;
}
```

```objectivec
// 当应用程序进入非活动状态时执行, 在此期间, 应用程序不接受消息或事件、比如电话来了、锁屏等
- (void)applicationWillResignActive:(UIApplication *)application {

}
```

```objectivec
// 当应用程序进入活跃状态时执行, 刚好与上一方法功能相反
- (void)applicationDidBecomeActive:(UIApplication *)application {

}
```

```objectivec
// 如果程序支持后台, 则程序进入后台调用此方法
- (void)applicationDidEnterBackground:(UIApplication *)application {

}
```

```objectivec
// 程序在后台进入前台时, 与上面的方法相反
- (void)applicationWillEnterForeground:(UIApplication *)application {

}
```

```objectivec
// 当程序将要被退出时调用, 通常用来保存数据和退出前的清理工作
- (void)applicationWillTerminate:(UIApplication *)application {
  
}
```

## 02 窗口与视图
#### 一. 窗口与视图：
> iOS中，使用窗口与视图在屏幕上显示应用程序的内容。窗口本身不具有任何可见内容，仅用于提供应用程序视图的一个容器。视图定义所需要的内容来填充部分窗口。

#### 二. 窗口的创建
1. 手动创建

```objectivec
	// 创建窗口
	self.window = [[UIWindow alloc] initWithFrame:[UIScreen mainScreen].bounds];
	// 设置窗口背景颜色为白色
	self.window.backgroundColor = [UIColor whiteColor];
	// 使窗口可见
	[self.window makeKeyAndVisible];
```

2. 通过xib文件创建、加载mainWindow.xib文件加载进行实例化

#### 三. 视图的创建
1. 手动创建

```objectivec
	// 设定边框大小
	CGRect viewRect = CGRectMake(0, 0, 100, 100); 
	// 创建视图的同时设定边框
	UIView *myView = [[UIView alloc] initWithFrame:viewRect];
```

2. 通过xib文件创建视图对象

```objectivec
	// 创建数据包
	NSBundle *bundle = [NSBundle mainBundle];
	// 导入数据包
	NSArray *array = [bundle loadNibNamed:@"myView" owner:self options:nil];
	// 将最底部的窗口取出
	UIView *myView = [array objectAtIndex:0];
 
	// P.S. 一般多整合成一句代码
	[[NSBundle mainBundle]loadNibNamed:@"myView" owner:self options:nil];
```

#### 四. 视图的层次结构
> - UIView的层次结构可以理解为“视图树”。
> - 一个视图就是一个容器，当一个视图包含其它视图的时候, 两个视图之间建立父子关系。被包含的称为“子视图”包含的视图称为“父视图”或“超视图”。
> - 子视图隐藏父视图内容，设置透明属性可以看到父视图的内容。
> - 一个视图可以嵌入多个subView，但是只能有一个superView。

#### 五. UIView的常用方法
基本的添加和删除:

```objectivec
// 把视图从父视图中移除
- (void)removeFromSuperview;
// 视图插入到指定索引
- (void)insertSubview:(UIView *)view atIndex:(NSInteger)index;
// 把两个索引对应的视图调换位置
- (void)exchangeSubviewAtIndex:(NSInteger)index1 withSubviewAtIndex:(NSInteger)index2;

// 添加子视图
- (void)addSubview:(UIView *)view;
// 插入到指定视图之下
- (void)insertSubview:(UIView *)view belowSubview:(UIView *)siblingSubview;
// 插入到指定视图之上
- (void)insertSubview:(UIView *)view aboveSubview:(UIView *)siblingSubview;

// 把视图移动到最顶层
- (void)bringSubviewToFront:(UIView *)view;
// 把视图移动到最底层
- (void)sendSubviewToBack:(UIView *)view;
```

#### 六. 查找子视图
> UIView类中有一个tag属性，通过tag值可以标示视图对象
 
```objectivec
    UIView *myView = [[UIView alloc] initWithFrame:CGRectMake(0, 0, 100, 100)];
    myView.tag = 100;
    [self.view addSubview:myView];
    
    // 通过tag值获得view
    // 此时的findView就是上方建立的myView
	UIView *findView = [self.view viewWithTag:100];   
```

#### 七. UIView的常用属性

Property | 释义
--- | ---
alpha | 透明度
backgroundColor | 背景颜色
subViews | 子视图集合
hidden | 是否隐藏，该属性的隐藏代表直接隐藏
tag | 标签值
superView | 父视图
multipleTouchEnabled | 是否支持多点触摸
userInteractionEnabled | 是否响应触摸事件

#### 八. 坐标系统变换(实现视图的简单变换)
> 使用CGAffineTransformMake来创建的变换，会覆盖前一次的变换。  
> 因为该变换只在原有基础上进行变换，故将一次次覆盖。

```objectivec
// 对视图进行变焦旋转参数:当前视图的变换状态, 旋转角度(弧度)
— CGAffineTransformRotate(CGAffineTransform t, CGFloat angle);

// 对视图进行缩放变换参数:当前视图的变换状态, x、y方向上放大的比例
— CGAffineTransformScale(CGAffineTransform t, CGFloat sx, CGFloat sy);

// 对视图进行平移变换参数:当前视图的变换状态, x、y方向上要移动的距离
— CGAffineTransformTranslate(CGAffineTransform t, CGFloat tx, CGFloat ty);
```

```objectivec
//  1. 获取视图当前的变换状态
    CGAffineTransform transform = view.transform;
//  2. 旋转变换
    transform = CGAffineTransformRotate(transform, M_PI_4);
//  3. 平移
    transform = CGAffineTransformTranslate(transform, 50, 200);
//  4. 缩放
    transform = CGAffineTransformScale(transform, 0.2, 2.0);
//  5. 将变换应用到视图上
    view.transform = transform;
```

#### 九. UIView属性的动画
> 通过改变UIView的属性来显示动画，比如frame尺寸位置、center中心点、alpha透明度、backgroundColor背景颜色、contentStretch视图拉伸。

```objectivec
//  默认执行方法 -animationWillStart:(NSString *)animationID context:(void *)context;
+ (void)setAnimationWillStartSelector:(nullable SEL)selector;

//  默认执行方法 -animationDidStop:(NSString *)animationID finished:(NSNumber *)finished context:(void *)context;
//  参数:动画块中的动画标识符;如果动画顺利, 没有被其它动画取消或停止, 则返回YES;传递额外信息
+ (void)setAnimationDidStopSelector:(nullable SEL)selector;
```

#### 十. 配置动画参数

```objectivec
//  开始动画
+ (void)beginAnimations:(NSString *)animationID context:(void *)context;
//  提交动画
+ (void)commitAnimations;

//  设置动画持续的秒数; 默认为0.2秒
+ (void)setAnimationDuration:(NSTimeInterval)duration;
//  设置动画实际发生的与commitAnimations方法返回的时间点之间的间隔
+ (void)setAnimationDelay:(NSTimeInterval)delay;
//  设置动画在commitAnimations方法返回之后的日期; 默认为当前
+ (void)setAnimationStartDate:(NSDate *)startDate;
//  设置动画过程的相对速度; 默认为全程同速
+ (void)setAnimationCurve:(UIViewAnimationCurve)curve;
//  设置动画的重复次数; 默认为0次, 即仅执行一次
+ (void)setAnimationRepeatCount:(float)repeatCount;
//  指定动画到达目标值是否自动反向播放; 默认为不自动反向, 只有在动画重复次数不为0次的时候有效
+ (void)setAnimationRepeatAutoreverses:(BOOL)repeatAutoreverses;
//  可以让部分动画块中发生的某些变化不产生动画效果, 可通过该方法禁止
+ (void)setAnimationsEnabled:(BOOL)enabled;
```

## 03 常用UI控件

![UIWidget](/UIJunior/Image/UIWidget.png)

#### 一. UILabel文本标签
> UILabel主要用来显示简短的文本。

Property | 释义
--- | ---
textColor | 文本颜色
text | 文本值
font | 文本字体
textAlignment | 文本显示位置：靠左、居中、靠右默认左对齐
numberOfLines | 文本行数

#### 二. UIControl
> UIControl是所有具有事件处理控件的父类。
>> 控件主要响应3种事件：基于触摸的事件、基于值的事件、基于编辑的事件。  
>> 常用事件：UIControlEventTouchUpInside 按钮的点击事件、UIControlEventValueChanged 进度条拖动。

![UIControl](/UIJunior/Image/UIControl.png)

#### 三. UIButton按钮
1. 常用方法

```objectivec
//  设置指定状态对应的标题文本; 默认无文本, 单行
- (void)setTitle:(nullable NSString *)title forState:(UIControlState)state;
//  设置指定状态对应的标题颜色; 默认白色
- (void)setTitleColor:(nullable UIColor *)color forState:(UIControlState)state;
//  设置指定状态对应的标题阴影颜色; 默认为50%的黑色
- (void)setTitleShadowColor:(nullable UIColor *)color forState:(UIControlState)state;
//  设置标题图片; 默认为空, 如果要添加不同状态下的图片, 它们的大小需要一样
- (void)setImage:(nullable UIImage *)image forState:(UIControlState)state;
//  设置背景图片; 默认为空
- (void)setBackgroundImage:(nullable UIImage *)image forState:(UIControlState)state;
```

2. 状态

Button State | 释义
--- | ---
UIControlStateNormal | 普通状态
UIControlStateHighlighted | 高亮状态
UIControlStateDisabled | 禁用状态
UIControlStateSelected | 选中状态
UIControlStateApplication | 程序使用时的状态
UIControlStateReserved | 系统保留状态

3. UIButton类型

![UIButton](/UIJunior/Image/UIButton.png)

#### 四. UITextField文本输入
> 文本输入框，用于输入少量文字。

Property | 释义
--- | ---
autocapitalizationType | 自动大写类型，可禁止
keyboardType | 键盘类型
boardStyle | 输入框显示样式
returnKeyType | 键盘上的return键的显示样式
clearButtonMode | 清除按钮模式
placeholder | 输入框为空显示的提示文字
secureTextEntry | 是否提供文本隐藏特性(密码输入框)
textAlignment | 输入框中的文本对齐方式
textColor | 输入框中的文本颜色
font | 输入框的文本字体
text | 输入框中的文本

2. 委托方法

```objectivec
//  将要开始输入时调用的方法, 可以返回NO来禁止编辑
- (BOOL)textFieldShouldBeginEditing:(UITextField *)textField;
//  将要输入结束时调用的方法, 可以返回YES来结束文本编辑, 并隐藏键盘
- (BOOL)textFieldShouldEndEditing:(UITextField *)textField;
//  清除文字按钮点击事件
- (BOOL)textFieldShouldClear:(UITextField *)textField;
//  return按钮的点击事件
- (BOOL)textFieldShouldReturn:(UITextField *)textField;
```

#### 五. UIImageView图像视图
> UIImageView用来显示图像视图，也可以以动画的形式显示一组图片

Property | 释义
--- | ---
image | 图片对象
userInteractionEnabled | 是否响应触摸事件，默认NO
highlightedImage | 高亮显示的图片
highlighted | 是否高亮
animationImages | 图片数组，用于动画播放
animationDuration | 播放动画图片的间隔时间

常用方法：

```objectivec
//  开始播放图片动画
- (void)startAnimating;
//  停止播放图片动画
- (void)stopAnimating;
```

#### 六. UISlider滑块
> UISlider是一个可以滑动的控件。

Property | 释义
--- | ---
value | 滑块的值
minimumValue | 滑块最小值
maximumValue | 滑块最大值

#### 七. UIActivityIndicatorView
> 类似风火轮，常用于加载等待。

Property | 释义
--- | ---
activityIndicatorStyle | 显示样式

2. 常用方法

```objectivec
//  开始风火轮转动动画
- (void)startAnimating;
//  停止风火轮转动动画
- (void)stopAnimating;
```

#### 八. UIPageControl分页控件
> UIPageControl用于标记当前页码。

Property | 释义
--- | ---
numberOfPages | 总页数
currentPage | 当前页数

#### 九. UIAlertView提示框
> iOS8 之后被UIAlertViewController代替，但还没有完全不可用。

1. 初始化方法

- UIAlertView

```objectivec
/**
 *  提醒框的init方法, 已被弃用, 使用UIAlertController
 *
 *  @param title             提醒标题
 *  @param message           提醒内容
 *  @param delegate          签订代理对象
 *  @param cancelButtonTitle 取消按钮文字
 *  @param otherButtonTitles 其他按钮文字
 *
 *  @return 一个初始化完毕的提示框
 */
- (instancetype)initWithTitle:(nullable NSString *)title message:(nullable NSString *)message delegate:(nullable id /*<UIAlertViewDelegate>*/)delegate cancelButtonTitle:(nullable NSString *)cancelButtonTitle otherButtonTitles:(nullable NSString *)otherButtonTitles, ...;
```

- UIAlertController

```objectivec
/**
 *  由于原有的UIAlertView被弃用, 使用提醒框控制器来代替
 *
 *  @param title          提醒标题
 *  @param message        提醒内容
 *  @param preferredStyle 提醒样式(功能菜单 / 提示框)
 *
 *  @return 一个初始化完毕的提示控制器
 */
+ (instancetype)alertControllerWithTitle:(nullable NSString *)title message:(nullable NSString *)message preferredStyle:(UIAlertControllerStyle)preferredStyle;
```

2. 常用方法

- UIAlertView

```objectivec
//  初始化创建后show即可
- (void)show; 
```

- UIAlertController

```objectivec
/**
 *  初始化功能按钮
 *
 *  @param title   按钮文字
 *  @param style   功能样式
 *  @param handler 实现功能的代码块
 *
 *  @return 一个初始化完毕的提示框样式按钮
 */
+ (instancetype)actionWithTitle:(nullable NSString *)title style:(UIAlertActionStyle)style handler:(void (^ __nullable)(UIAlertAction *action))handler;

/**
 *  为提示框控制器添加功能
 *
 *  @param action 初始化完毕的功能按钮
 */
- (void)addAction:(UIAlertAction *)action;

//  添加功能完毕后, 只需要以模态视图弹出即可
```

#### 十. UIActionSheet功能菜单
> 在iOS8之后和提示框一样被弃用，集成于UIAlertController中

1. 初始化方法

- UIActionSheet

```objectivec
/**
 *  初始化功能菜单
 *
 *  @param title                  功能菜单标题
 *  @param delegate               签订代理对象
 *  @param cancelButtonTitle      取消按钮文字(位于底部)
 *  @param destructiveButtonTitle 销毁按钮文字(默认红底样式)
 *  @param otherButtonTitles      其他按钮文字
 *
 *  @return 一个初始化完毕的功能菜单
 */
- (instancetype)initWithTitle:(nullable NSString *)title delegate:(nullable id<UIActionSheetDelegate>)delegate cancelButtonTitle:(nullable NSString *)cancelButtonTitle destructiveButtonTitle:(nullable NSString *)destructiveButtonTitle otherButtonTitles:(nullable NSString *)otherButtonTitles, ...;
```

2.常用方法

- UIActionSheet

```objectivec
- (void)showInView:(UIView *)view;//初始化创建后在一个视图上显示出上拉菜单即可
```

- UIAlertController
> 同提示框中的示例，更改提示框控制器的选择样式即可，其它方法实现不变。

## 04 视图控制器
#### 一. UIViewController介绍
- 视图控制器用来管理视图的加载、卸载、横屏竖屏显示等操作
	- 每一个界面都应该由一个控制器来管理显示
	- UIViewController是所有视图控制器的父类
	- iOS内置多种视图控制器类，如导航控制器UINavigationController、标签栏控制器UITabBarController、表视图控制器UITableViewController等
	- 每个视图控制器管理和控制一系列的视图，但是你永远不会直接把UIView添加到UIWindow上，而是添加UIViewController

![UIViewController](/UIJunior/Image/UIViewController.png)

#### 二. UIViewController的创建

```objectivec
RootViewController *rootCtrl = [[RootViewController alloc] init];
[self.window setRootViewController:rootCtrl];
```

1. 通过代码创建视图

```objectivec
- (void)loadView {
// 创建每个根控制器的视图
UIView *rootView = [[UIView alloc]initWithFrame:[UIScreen mainScreen].applicationFrame];
self.view = rootView;
self.view.backgroundColor = [UIColor redColor];

// 初始化其它视图
// ......
}
```

2. 通过xib创建视图

#### 三.  视图的加载
> 1. 去访问View属性。
> 2. 如果存在view，则直接加载。相反，如果不存在，则UIViewController调用loadView方法。
> 3. loadView方法执行如下操作：如果你重载了该方法，则必须创建view给UIViewController的view的属性。

![UIView](/UIJunior/Image/UIView.png)

![UIVIew2](/UIJunior/Image/UIView2.png)

#### 四. 设置模拟器支持方向旋转
1. 直接设置
> 1. plist文件中的Supported interface orientaion设置
> 2. 对工程文件的Deployment Info直接取消勾选不需要的设置

Position | 释义
--- | ---
Portrait | Home键在底部
UpsideDown | Home键在顶部
Landscape Left | Home键在左侧
Landscape Right | Home键在右侧


2. 代码设置
- 可以在代码中覆写该方法来实现方向旋转，有以下枚举值已经设定完毕

Position | 释义
--- | ---
UIInterfaceOrientationMaskPortrait | 普通竖屏
UIInterfaceOrientationMaskLandscapeLeft | 左横屏
UIInterfaceOrientationMaskLandscapeRight | 右横屏
UIInterfaceOrientationMaskPortraitUpsideDown | 反向竖屏
UIInterfaceOrientationMaskLandscape | 支持横屏
UIInterfaceOrientationMaskAll | 支持所有方向
UIInterfaceOrientationMaskAllButUpsideDown | 支持除反向竖屏外的所有方向

```objectivec
- (NSUInteger)supportedInterfaceOrientations {
//  支持左横屏和竖屏方向
return (UIInterfaceOrientationMaskPortrait｜UIInterfaceOrientationMaskLandscapeLeft);
}
```

#### 五. 模态视图
1. 概念
> 通过视图控制器的presentModalViewController:方法弹出的视图都为模态视图

```objectivec
//  模态视图出现的场景一般都是临时弹出的窗口
ModalViewController *mc = [[ModalViewController alloc]init];
//  设置视图弹出时的动画效果
mc.modalTransitionStyle = UIModalTransitionStyleFlipHorizontal'
[self presentModalViewController:mc animated:YES];
```

2. 常用方法

```objectivec
/**
 *  弹出模态视图
 *
 *  @param viewControllerToPresent 将要弹出的视图控制器
 *  @param flag                    是否添加动画(可设置动画类型)
 *  @param completion              弹出后还需完成何种功能
 */
- (void)presentViewController:(UIViewController *)viewControllerToPresent animated: (BOOL)flag completion:(void (^ __nullable)(void))completion;

/**
 *  收回模态视图
 *
 *  @param flag       是否添加动画(可设置动画类型)
 *  @param completion 在模态视图收回后是否需要完成何种功能
 */
- (void)dismissViewControllerAnimated: (BOOL)flag completion: (void (^ __nullable)(void))completion;

//  如果要实现两个视图之间的数值传递，可以通过block块、协议等方法(参见OC整理)
```

3. 视图出现

![ShowModalView](/UIJunior/Image/ShowModalView.png)

4. 视图消失

![DismissModalView](/UIJunior/Image/DismissModalView.png)

5. 理解调用顺序

```objectivec
//  创建载入根视图
- (void)loadView;
//  视图载入完成
- (void)viewDidLoad;
//  视图将出现在屏幕之前
- (void)viewWillAppear:(BOOL)animated;
//  视图已在屏幕上渲染完成
- (void)viewDidAppear:(BOOL)animated;
//  视图将被从屏幕上移除之前执行
- (void)viewWillDisappear:(BOOL)animated;
//  视图已经从屏幕上移除
- (void)viewDidDisappear:(BOOL)animated;
```

#### 六. 小问题
1. 视图控制器是view吗？视图控制器与视图的关系？
- 答：视图控制器不是view，每一个视图控制器都有一个view，视图控制器是个大管家，管理这个视图的加载、卸载、横屏显示。

2. 视图控制器的loadView什么时候调用？会调用多次吗？
- 答：loadView被调用满足两个条件：1.此控制器的view访问器方法被调用 2.view为nil时，正常情况下loadView只会被调用一次，因为loadView第一次调用之后，view就不再为空了。

3. UIViewController的loadView中如何加载视图的？
- 答：loadView中首先判断是否有可用的xib文件可以加载，如果有则加载xib文件来创建此控制器的view，如果没有，则使用代码创建此控制器的view。

4. 如果使用xib创建控制器的视图，是怎样的加载流程？
- 答：先判断是否有指定xib文件名，如果没有，则使用控制器的类名作为xib文件名去加载xib，如果指定了，则使用指定的xib文件名去加载。

5. viewDidAppear方法何时调用，会调用多次吗？viewDidDisappear呢？
- 答：当前控制器的view被添加到父视图上去时，则会调用此控制器的viewDidAppear方法，因为控制器的view可以被多次添加到父视图上，因此viewDidDisappear可以被调用多次。当控制器视图从父视图上移除时，则此控制器的viewDidDisappear调用。

## 05 导航控制器
#### 一. 导航控制器(UINavigationController)的基本概念
> 基本概念:
- 导航控制器本身不显示视图内容，而是管理子控制器的视图显示
- 基本结构:导航栏(Navigation bar)、子控制器的视图(Custom content)、导航工具栏(Navigation toolbar)默认隐藏，较少使用
- 导航栏高度64px，工具栏高度49px

#### 二. 实现导航控制器
- 创建导航控制器

```objectivec
//  创建子控制器
RootViewController *rootVC = [[RootViewController alloc]init];
//  创建导航控制器，并将rootVC作为第一个管理的子控制器
UINavigationController *navigation = [[UINavigationController alloc]initWithRootViewController:rootVC];
```

- 导航到下一个子控制器
```objectivec
//  创建第二个子控制器
SecondViewController *secondVC = [[SecondViewController alloc]init];
//  导航到第二个控制器
[self.navigationController pushViewController:secondVC animated:YES];
```

#### 三. 常用方法

```objectivec
//  初始化一个根视图控制器，在栈的最底层
- (instancetype)initWithRootViewController:(UIViewController *)rootViewController;
//  压入到一个新的视图控制器中，在栈中最顶层，可以选择是否需要动画 
- (void)pushViewController:(UIViewController *)viewController animated:(BOOL)animated; 

//  弹出到上一个控制器，可以选择是否需要动画效果
- (UIViewController *)popViewControllerAnimated:(BOOL)animated; 
//  弹出到指定的视图控制器中，可以选择是否需要动画效果
- (NSArray<__kindof UIViewController *> *)popToViewController:(UIViewController *)viewController animated:(BOOL)animated; 
//  回到根视图控制器，可以选择是否需要动画效果
- (NSArray<__kindof UIViewController *> *)popToRootViewControllerAnimated:(BOOL)animated; 

```

#### 四. 导航栏的基本概念
1.  - 一个导航控制器包含一个导航栏(UINavigationBar)
	- 一个子控制器对应一个导航项(UINavigationItem)

![UINavigation](/UIJunior/Image/UINavigation.png)

2. 设置导航栏标题

```objectivec
// 使用内置标题: 
self.title = @"标题";

// 自定义标题:
UILabel *titleLabel = [[UILabel alloc]initWithFrame:CGRectMake(0, 0, 100, 44)];
titleLabel.backgroundColor = [UIColor redColor];
titleLabel.text = @"标题";
self.navigationItem.titleView = titleLabel;
```

3. 导航栏按钮

```objectivec
// 初始化一个带图片的UIBarButtonItem实例(一般不用)
- (instancetype)initWithImage:(nullable UIImage *)image style:(UIBarButtonItemStyle)style target:(nullable id)target action:(nullable SEL)action;

// 初始化一个只带标题的UIBarButtonItem实例
- (instancetype)initWithTitle:(nullable NSString *)title style:(UIBarButtonItemStyle)style target:(nullable id)target action:(nullable SEL)action;

// 初始化一个系统自带的UIBarButtonItem实例
- (instancetype)initWithBarButtonSystemItem:(UIBarButtonSystemItem)systemItem target:(nullable id)target action:(nullable SEL)action;

// 初始化自定义的一个视图
- (instancetype)initWithCustomView:(UIView *)customView;
```

4.导航栏的一些基本设置

```objectivec
	// 设置风格:设置导航栏风格为黑色，实际字体为白色
	self.navigationController.navigationBar.barStyle = UIBarStyleBlack;
	// 设置导航栏为透明
	self.navigationController.navigationBar.translucent = YES;

	// 设置导航栏的颜色
    self.navigationController.navigationBar.tintColor = [UIColor redColor];

// 设置背景图片
- (void)setBackgroundImage:(nullable UIImage *)backgroundImage forBarPosition:(UIBarPosition)barPosition barMetrics:(UIBarMetrics)barMetrics;

	// 设置prompt属性(用的较少)
	// 作用为用于提示用户。比如正在请求网络数据的时候，提示用户数据正在加载。
	// 待加载完成以后可设置为nil，取消显示
	self.navigationItem.prompt = @"加载";
	self.navigationItem.prompt = nil;
```

![UINavigationBar](/UIJunior/Image/UINavigationBar.png)

5. 代理方法

```objectivec
// 视图控制器将要显示时调用
- (void)navigationController:(UINavigationController *)navigationController willShowViewController:(UIViewController *)viewController animated:(BOOL)animated;
// 视图控制器已经显示时调用
- (void)navigationController:(UINavigationController *)navigationController didShowViewController:(UIViewController *)viewController animated:(BOOL)animated;
```

## 06 标签控制器
#### 一. 标签控制器基本概念
> UITabBarController同UINavigationController一样是用来管理视图控制器的。  
> 标签控制器是管理固定的几个视图控制器，子控制器是并列的，可以任意切换显示

#### 二. 标签控制器的创建

```objectivec
    // 系统自带的标签控制器样式的初始化方法。如果创建的子控制器超过五个以上，则默认会在"更多"里。
    UIViewController *viewCtr1 = [[UIViewController alloc]init];
    viewCtr1.title = @"主页";
   
    UIViewController *viewCtr2 = [[UIViewController alloc] init];
    viewCtr2.title = @"消息";
    
    UIViewController *viewCtr3 = [[UIViewController alloc] init];
    viewCtr3.title = @"搜索";
    
    UIViewController *viewCtr4 = [[UIViewController alloc] init];
    viewCtr4.title = @"设置";
    
    // 将所有子控制器放入数组
    NSArray *viewCtrs = [NSArray arrayWithObjects:viewCtr1, viewCtr2, viewCtr3, viewCtr4, nil];
    
    UITabBarController *tabBar = [[UITabBarController alloc] init];
    // 将标签控制器创建出来后，把子控制器数组交由标签控制器管理
    tabBar.viewControllers = viewCtrs;
    // 将根控制器的权限给标签控制器
    self.window.rootViewController = tabBar;
```

#### 三. 代理方法

```objectivec
// 视图将要切换时调用,viewController为将要显示的控制器
- (BOOL)tabBarController:(UITabBarController *)tabBarController shouldSelectViewController:(UIViewController *)viewController;

// 视图已经切换后调用，viewController为将要显示的控制器
- (void)tabBarController:(UITabBarController *)tabBarController didSelectViewController:(UIViewController *)viewController;
```

#### 四. UITabBar视图的组成

![UITabBar](/UIJunior/Image/UITabBar.png)

#### 五. 定制UITabbar
- 项目中最常用的结构图

![CustomTabBar](/UIJunior/Image/CustomTabBar.png)

![CustomTabBarController](/UIJunior/Image/CustomTabBarController.png)

1. 采用系统自带的tabBar类型

```objectivec
    // 自定义title、图片
    UITabBarItem *tabItem = [[UITabBarItem alloc] initWithTitle:@"收藏夹" image:[UIImage imageNamed:@"top"] tag:100];

    // 自定义title，样式用系统自带的图标
    UITabBarItem *tabItem2 = [[UITabBarItem alloc] initWithTabBarSystemItem:UITabBarSystemItemFavorites tag:101];
   
    // 将UITabBarItem绑定对应的子控制器
    HomeViewController *homeViewController = [[HomeViewController alloc] init];
    // 此时的HomeViewController是继承于UITabBarController
    homeViewController.tabBarItem = tabItem;
```

2. 自定义tabBar
> 如果要自定义tabBar视图，执行以下4个步骤
>> 1. 首先，隐藏系统的tabBar视图(如果想自己重新做，建议删除tabBar视图，自行添加视图和按钮等)
>> 2. 自定义一个tabBar视图(高度49个像素)
>> 3. 将用户自定义的图片添加到背景图片
>> 4. 定义一个选中时的图片，用户选中时，实现简单的移动动画效果

- 代码实现

```objectivec
    // 创建子控制器
    FirstViewController *firstViewController = [[FirstViewController alloc] init];
    
    // 创建导航控制器
    UINavigationController *navigaitonController = [[UINavigationController alloc] initWithRootViewController:firstViewController];
    
    // 将导航控制器交给标签控制器管理
    NSArray *viewControllers = [NSArray arrayWithObjects:navigaitonController, nil];
    UITabBarController *tabBarController = [[UITabBarController alloc] init];
    tabBarController.viewControllers = viewControllers;
    
    self.window.rootViewController = tabBarController;
```

#### 六. UITabbar的设置

```objectivec
    // 创建出标签控制器
    UITabBarController *tabBarController = [[UITabBarController alloc] init];
    
    // 设置tabBar的背景图片
    tabBarController.tabBar.backgroundImage = [UIImage imageNamed:@"图片名"];
    // 设置标签控制器的背景颜色
    tabBarController.tabBar.backgroundColor = [UIColor redColor];
    // 设置选中item的字体颜色
    tabBarController.tabBar.tintColor = [UIColor blackColor];
    // 设置选中item时的背景图片
    tabBarController.tabBar.selectionIndicatorImage = [UIImage imageNamed:@"图片名"];
    
    // 设置badgeValue属性显示红色图标标记,该属性值的类型为字符串类型
    self.tabBarItem.badgeValue = @"New";
```

## 07 表视图
#### 一. 表视图的基本概念
1. 最常见的表视图例子如通讯录，设置等等。
2. 表视图的风格分两种:UITableViewStylePlain(平铺)，UITableViewStyleGrouped(分组)。

![UITableView](/UIJunior/Image/UITableView.png)

3. 表视图的索引路径(NSIndexPath)

key | 释义
--- | ---
IndexPath | 代表cell的位置
Section | 组索引
Row | 在组中的行索引

#### 二. 表视图的简单创建
1. 表视图的创建

```objectivec
	UITableView *tableView = [[UITableView alloc]initWithFrame:CGRectMake(0, 0, self.view.frame.size.width,self.view.frame.size.height) style:UITableViewStylePlain];
    
    // 设置代理对象、数据源对象
    tableView.delegate = self;
    tableView.dataSource = self;
    
    [self.view addSubview:tableView];
```

2. 实现协议方法

```objectivec
// 以下两个数据源方法必须强制实现
- (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section {
	// 返回每组中单元格的数量，一般以数组的形式表示其行数[array count]
    return 20;  
}

- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath {
    static NSString *identify = @"myCell";
    // 检测、查询是否有闲置单元格
    UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:identify];
    if (cell == nil) {
        cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault reuseIdentifier:identify];
    }
    // 返回每行的单元格对象
    return cell;
}
```

#### 三. 表视图调用顺序—委托方法
> 创建和配置表视图的顺序
>> 1. 创建表视图实例，初始化风格和大小
>> 2. 设置数据源方法和委托方法
>> 3. 开始调用数据源方法(事件循环没有结束)
>> 4. 调用顺序如图示

![UITableViewDelegateAndDataSource](/UIJunior/Image/UITableViewDelegateAndDataSource.png)

#### 四. 表视图的构成
1. 主要由头视图、单元格、尾视图三部分组成。

2. 常用属性

```objectivec
// 设置表视图分割线风格
@property (nonatomic) UITableViewCellSelectionStyle   selectionStyle;
// 设置表视图分割线颜色、默认标准灰色
@property (nonatomic, strong, nullable) UIColor *separatorColor

// 设置表视图的头部视图
@property (nonatomic, strong, nullable) UIView *tableHeaderView;
// 设置表视图的尾部视图
@property (nonatomic, strong, nullable) UIView *tableFooterView;

// 设置表视图单元格的行高
@property (nonatomic) CGFloat rowHeight;             
// 设置表视图的组的头部行高
@property (nonatomic) CGFloat sectionHeaderHeight;
// 设置表视图的组的尾部行高
@property (nonatomic) CGFloat sectionFooterHeight;

// 设置表视图背景
@property (nonatomic, strong, nullable) UIView *backgroundView 

// 刷新表视图单元格中数据
- (void)reloadData;
```

3. 常用方法

```objectivec
// 指定一个NSIndexPath，返回一个cell实例，如果cell没有显示，返回nil
- (nullable __kindof UITableViewCell *)cellForRowAtIndexPath:(NSIndexPath *)indexPath;

// 根据显示的cell，返回一组cell实例的数组，如果没有显示，返回nil
@property (nonatomic, readonly) NSArray<__kindof UITableViewCell *> *visibleCells;

// 根据显示的cell，返回一组NSIndexPath实例的数组，如果没有显示，返回nil
@property (nonatomic, readonly, nullable) NSArray<NSIndexPath *> *indexPathsForVisibleRows;

// 滑动到指定位置，可以配置动画
- (void)scrollToRowAtIndexPath:(NSIndexPath *)indexPath atScrollPosition:(UITableViewScrollPosition)scrollPosition animated:(BOOL)animated;
```

#### 五. 数据源方法和委托方法
- 表视图继承自UIScrollView，这样的继承关系使得表视图可以实现上、下滚动
- 数据源方法(UITableViewDatasource)：实例化表视图时，必须要实现它的数据源方法，以此来完成表中数据的配置
- 委托方法(UITbaleViewDelegate)：表视图的委托方法(代理方法)，一般是处理表视图基本样式(如单元格的高度)以及捕捉选中单元格事件

1. 数据源方法:

```objectivec
@required
// 配置section中含有行数
- (NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section;
// 创建单元格实例
- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath;

@optional
// 配置表视图section个数, 默认为1
- (NSInteger)numberOfSectionsInTableView:(UITableView *)tableView;
// section中的头部视图的标题
- (nullable NSString *)tableView:(UITableView *)tableView titleForHeaderInSection:(NSInteger)section;
// section中的尾部视图的标题
- (nullable NSString *)tableView:(UITableView *)tableView titleForFooterInSection:(NSInteger)section;
```

2. 委托方法

```objectivec
// 当单元格被选中时调用
- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)indexPath;

// 配置行高
- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath;
// 设置section的头部视图的高度
- (CGFloat)tableView:(UITableView *)tableView heightForHeaderInSection:(NSInteger)section;
// 设置section的尾部视图的高度
- (CGFloat)tableView:(UITableView *)tableView heightForFooterInSection:(NSInteger)section;

// 自定义section的头部视图、需要指定高度
- (nullable UIView *)tableView:(UITableView *)tableView viewForHeaderInSection:(NSInteger)section;
// 自定义section的尾部视图、需要指定高度
- (nullable UIView *)tableView:(UITableView *)tableView viewForFooterInSection:(NSInteger)section;
```

#### 六. 单元格复用

```objectivec
    // 单元格标识符
    static NSString *identifier = @"cell";
    // 查询池子中是否有闲置的单元格
    UITableViewCell *cell = [tableView dequeueReusableCellWithIdentifier:identifier];
    if (cell == nil) {
        cell = [[UITableViewCell alloc] initWithStyle:UITableViewCellStyleDefault reuseIdentifier:identifier];
    }
    return cell;
```

#### 七. 单元格UITableViewCell常用属性

```objectivec
// 背景视图
@property (nonatomic, strong, nullable) UIView *backgroundView;
// 选中后的背景视图
@property (nonatomic, strong, nullable) UIView *selectedBackgroundView;

// 选中后的显示样式
@property (nonatomic) UITableViewCellSelectionStyle   selectionStyle;
// 是否高亮(选中)
@property (nonatomic, getter=isHighlighted) BOOL      highlighted; 

// 辅助图标
@property (nonatomic) UITableViewCellAccessoryType    accessoryType;
// 自定义辅助图标
@property (nonatomic, strong, nullable) UIView       *accessoryView;
```

#### 八. 单元格高度自适应核心代码

```objectivec
- (CGFloat)tableView:(UITableView *)tableView heightForRowAtIndexPath:(NSIndexPath *)indexPath{
    NSString *text = [_data objectAtIndex:indexPath.row];
    CGSize size = [text sizeWithFont:[UIFont systemFontOfSize:14] constrainedToSize:CGSizeMake(300, 1000)];
    return size.height + 20;
}
```

## 08 表视图控制器
#### 一. 基本概念
- UITableViewController继承UIViewController，默认实现了常用的数据源方法和代理方法
- 如果覆写了loadView方法，注意确保父类的loadView方法，因为父类的loadView需要初始化UITableView

```objectivec
// 通过属性，访问和设置表视图
@property (nonatomic, strong, null_resettable) UITableView *tableView;
// 默认YES，当视图出现时，是否取消选中状态
@property (nonatomic) BOOL clearsSelectionOnViewWillAppear;
```
 
#### 二. 单元格类型
1 .第一种:UITableViewCellStyleDefault(默认样式、左图右标题)

```objectivec
    if (cell == nil) {
        cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault
                                     reuseIdentifier:identify];
        cell.imageView.image = [UIImage imageNamed:@"cell"];
        cell.textLabel.text = text;
    }
```

2. 第二种:UITableViewCellStyleSubtitle(左图，右上标题、右下小标题)

```objectivec
	// 属性设置多了一个detailText的设置，即子标题
	cell.detailTextLabel.text = detailText; 
```

3. 第三种:UITableViewCellStyleValue1(无图，左标题黑体，右小标题字体蓝色)
4. 第四种:UITableViewCellStyleValue2(无图，左标题蓝色字体，右小标题字体黑色)
#### 三. 自定义单元格
1. 第一种方式：向contentView添加子视图

```objectivec
    if (cell == nil) {
        cell = [[UITableViewCell alloc]initWithStyle:UITableViewCellStyleDefault
                                     reuseIdentifier:identify];
        
        CGRect labelFrame = CGRectMake(10, 5, 200, 20);
        UILabel *titleLabel = [[UILabel alloc]initWithFrame:labelFrame];
        titleLabel.tag = 100;
        titleLabel.font = [UIFont systemFontOfSize:14];
        titleLabel.backgroundColor = [UIColor clearColor];
        [cell.contentView addSubview:titleLabel];
        
        // 添加其它子视图
        // .....
    }
    
    UILabel *titleLabel = (UILabel *)[cell.contentView viewWithTag:100];
    titleLabel.text = @"label内容";
```

2. 第二种方式：xib定义单元格

```objectivec
    if (cell == nil) {
        NSBundle *bundle = [NSBundle mainBundle];
        
        // 加载xib
        NSArray *array = [bundle loadNibNamed:@"newCell" owner:self options:nil];
        cell = [array objectAtIndex:0];
    }
    
    UILabel *titleLabel = (UILabel *)[cell.contentView viewWithTag:100];
    titleLabel.text = @"label内容";
```

3.第三种方式：子类化

```objectivec
@property (nonatomic, strong) UILabel *titleLabel;
@property (nonatomic, strong) UILabel *commentLabel;
@property (nonatomic, strong) UILabel *timeLabel;

- (void)_initViews{
    _titleLabel = [[UILabel alloc] initWithFrame:CGRectZero];
    _titleLabel.font = [UIFont systemFontOfSize:14];
    _titleLabel.backgroundColor = [UIColor clearColor];
    [self.contentview addSubview:_titleLabel];
}

- (void)layoutSubViews{
    [super layoutSubViews];
    _titleLabel.frame = CGRectMake(10, 5, 200, 20);
    _commentLabel.frame = CGRectMake(10, 30, 100, 10);
    _timeLabel.frame = CGRectMake(260, 30, 50, 10);
    
    _titleLabel.text = news.title;
    _commentLabel.text = [NSString stringWithFormat:@"%i条评论", news.commentCount];
    _timeLabel.text = [NSString stringWithFormat:"%i小时前", news.timeVal];
}
```

#### 四. 表视图的编辑模式
- 其编辑模式有三种：添加，删除，移动

1. 编辑常用方法

```objectivec
// 插入一行cell，指定一个实现的动画效果
- (void)insertRowsAtIndexPaths:(NSArray<NSIndexPath *> *)indexPaths withRowAnimation:(UITableViewRowAnimation)animation;
// 删除一行cell，指定一个实现的动画效果
- (void)deleteRowsAtIndexPaths:(NSArray<NSIndexPath *> *)indexPaths withRowAnimation:(UITableViewRowAnimation)animation;
// 移动cell的位置，指定一个实现的动画效果
- (void)moveRowAtIndexPath:(NSIndexPath *)indexPath toIndexPath:(NSIndexPath *)newIndexPath
```

2. 数据源方法

```objectivec
// 定义可编辑的单元格
- (BOOL)tableView:(UITableView *)tableView canEditRowAtIndexPath:(NSIndexPath *)indexPath;
// 定义编辑模式下、按钮的显示样式，有新增、删除
- (UITableViewCellEditingStyle)tableView:(UITableView *)tableView editingStyleForRowAtIndexPath:(NSIndexPath *)indexPath;
// 新增、删除按钮事件
- (void)tableView:(UITableView *)tableView commitEditingStyle:(UITableViewCellEditingStyle)editingStyle forRowAtIndexPath:(NSIndexPath *)indexPath;
```

- 核心代码:新增、删除按钮事件

```objectivec
- (void)tableView:(UITableView *)tableView commitEditingStyle:(UITableViewCellEditingStyle)editingStyle forRowAtIndexPath:(NSIndexPath *)indexPath{
    // 删除
    if (editingStyle == UITableViewCellEditingStyleDelete) {
        [_data removeObjectAtIndex:indexPath.row];
        [tableView deleteRowsAtIndexPaths:[NSArray arrayWithObject:indexPath]
                         withRowAnimation:UITableViewRowAnimationFade];
    }
    // 新增
    else if (editingStyle == UITableViewCellEditingStyleInsert){
        NSString *obj = [NSString stringWithFormat:@"我是新添加的"];
        [_data insertObject:obj atIndex:indexPath.row];
        [tableView insertRowsAtIndexPaths:[NSArray arrayWithObject:indexPath]
                         withRowAnimation:UITableViewRowAnimationFade];
    }
}
```

3. 编辑模式数据源方法

```objectivec
// 实现此方法，单元格即可移动
- (void)tableView:(UITableView *)tableView moveRowAtIndexPath:(NSIndexPath *)sourceIndexPath toIndexPath:(NSIndexPath *)destinationIndexPath;
// 指定可移动的单元格
- (BOOL)tableView:(UITableView *)tableView canMoveRowAtIndexPath:(NSIndexPath *)indexPath;
```

4. 表视图的编辑模式流程图

![UITableViewController](/UIJunior/Image/UITableViewController.png)

#### 五. 多选模式
- 在iOS5.0后，表视图增加多选功能

```objectivec
// 在编辑模式下 支持多选
self.tableView.allowsMultipleSelectionDuringEditing = YES;
// 选中后的cell索引集合
NSArray *indexPaths = self.tableView.indexPathsForSelectedRows;
```

#### 六. 过滤表格内容

```objectivec
- (void)textChange:(UITextField *)textField{
    NSString *text = textField.text;
    if ([text length] == 0) {
        self.filterData = _data;
        [self.tableView reloadData];
        return;
    }
    // 过滤条件
    NSString *p = [NSString stringWithFormat:@"SELF LIKE[c] '%@*'", text];
    NSPredicate *predicate = [NSPredicate predicateWithFormat:p];
    self.filterData = [_data filteredArrayUsingPredicate:predicate];
    [self.tableView reloadData];
}
```

## 09 滑动视图
#### 一. 基本概念
> 1. UIScrollView是一个视图，可以选择滑动，用于显示更多的内容
> 2. ScrollView通过手势、可以放大或缩小显示的内容
> 3. 其包含两个子类，其中一个就是UITableView

#### 二. 创建

```objectivec
    // 创建一个UIScrollView实例
    CGRect frame = CGRectMake(0, 0, 200, 200);
    UIScrollView *scrollView = [[UIScrollView alloc] initWithFrame:frame];
    
    // 添加子视图
    frame = CGRectMake(0, 0, 500, 500);
    UIImageView *myImageView = [[UIImageView alloc] initWithFrame:frame];
    [scrollView addSubview:myImageView];
    
    // 设置内容尺寸
    scrollView.contentSize = CGSizeMake(500, 500);
```

#### 三. 常用属性

```objectivec
//滚动时是否显示水平滚动条
@property(nonatomic)  BOOL    showsHorizontalScrollIndicator;
//滚动时是否显示垂直滚动条
@property(nonatomic)  BOOL    showsVerticalScrollIndicator;   

//滚动开始、末尾位置、是否加反弹效果
@property(nonatomic)  BOOL    bounces;
//缩放、放大最大是否加反弹效果
@property(nonatomic)  BOOL    bouncesZoom;

//滚动条的样式，基本只是设置颜色。总共三个颜色：默认、黑、白
@property(nonatomic)  UIScrollViewIndicatorStyle    indicatorStyle;
//滚动的偏移量
@property(nonatomic)  CGPoint    contentOffset
//滚动内容的尺寸
@property(nonatomic)  CGSize    contentSize

//当正在缩放的时候值是YES，否则NO
@property(nonatomic, readonly, getter = isZooming)  BOOL    zooming;
//一个浮点数，表示能放最大的倍数
@property(nonatomic)  CGFloat    maximumZoomScale;
//一个浮点数，表示能缩最小的倍数
@property(nonatomic)  CGFloat    minimumZoomScale;

//是否分页滑动
@property(nonatomic, readonly, getter = isPagingEnabled)  BOOL    pagingEnabled;
//是否开启滚动
@property(nonatomic, readonly, getter = isScrollEnabled)  BOOL    scrollEnabled;
```

#### 四. 常用代理方法

```objectivec
// 滑动时，实时调用
- (void)scrollViewDidScroll:(UIScrollView *)scrollView;

// 开始拖动
- (void)scrollViewWillBeginDragging:(UIScrollView *)scrollView;
// 结束拖动，手指离开屏幕，decelerate:是否为减速状态
- (void)scrollViewDidEndDragging:(UIScrollView *)scrollView willDecelerate:(BOOL)decelerate;
// scrollView开始减速(以下两个方法注意与以上两个方法加以区别)
- (void)scrollViewWillBeginDecelerating:(UIScrollView *)scrollView;
// scrollView减速停止
- (void)scrollViewDidEndDecelerating:(UIScrollView *)scrollView;      

// 返回一个放大或者缩小的子视图
- (nullable UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView;
// 开始放大或者缩小
- (void)scrollViewWillBeginZooming:(UIScrollView *)scrollView withView:(nullable UIView *)view; 
// 缩放结束
- (void)scrollViewDidEndZooming:(UIScrollView *)scrollView withView:(nullable UIView *)view atScale:(CGFloat)scale;

// 缩放或放大、实时调用
- (void)scrollViewDidZoom:(UIScrollView *)scrollView 
```

- 示例代码

```objectivec
- (void)viewSetting {
    //放大最大尺寸为2倍
    scrollView.maximumZoomScale = 2;
    //缩小最小尺寸为0.5倍
    scrollView.minimumZoomScale = 0.5;
    
    //向UIScrollView上添加子视图
    CGRect imageFrame = CGRectMake(0, 0, 320, 420);
    UIImageView *imageView = [[UIImageView alloc] initWithFrame:imageFrame];
    imageView.tag = 101;
    imageView.userInteractionEnabled = YES;
    imageView.image = [UIImage imageNamed:@"0.jpg"];
    [_scroolView addSubview:imageView];
}

- (UIView *)viewForZoomingInScrollView:(UIScrollView *)scrollView{
    return [scrollView viewWithTag:101];
}
```
