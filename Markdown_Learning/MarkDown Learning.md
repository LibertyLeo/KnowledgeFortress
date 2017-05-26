MarkDown 学习笔记
===
本文整理于2016年5月，默认测试工具为有道云协作上的MarkDown。    
注意文章中加粗部分的文字可在`GitHub`中使用，若有额外注释，以注释为准。    
P.S. `目录`的使用在简书中无效，此处仅保留展示效果。    
如需查看目录效果，请访问GitHub上的[MarkDown_Learning](https://github.com/LibertyLeo/KnowledgeFortress/blob/master/Markdown_Learning/MarkDown%20Learning.md)

本文参考自:[果冻虾仁](https://github.com/guodongxiaren/README)  

## 目录
* [分割线](#分割线)
* [换行](#换行)
* [标题](#标题)
* [文本](#文本)
    * 普通文本
    * 单行文本
    * 多行文本
    * 文字高亮
    * [代码高亮](#代码高亮)
    * 斜、粗体、删除线
* [块引用](#块引用)
* [列表](#列表)
    * 无序列表
    * 有序列表
    * 复选框列表
* [图片](#图片)
    * 网络图片
    * GitHub图片
* [链接](#链接)
    * 文字超链接
        * 外部网页链接
        * Git仓库链接
    * 图片网页链接
    * [锚点](#锚点)
* [表格](#表格)
    * 对齐方式
* [表情Emoji](#表情Emoji)

### 分割线
常用的分割线主要分以下几种形式:

`***`
***

`---`
---

`___`
___

### 换行
1. 在MarkDown语句中，直接键入回车只能用于区分上下格式，如果需要进行换行操作，在上一行文本末尾添加两个Tab或者空格，下一行文本就进行换行操作。
2. 如果觉得效果可以稍微差一些，可以键入一个空行，即键入两个回车后开始编辑文字。

### 标题
标题的大小仅仅用`#`表示即可，标题大小根据`#`个数。

# 一级标题
## 二级标题
#### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题

### 文本

#### 普通文本
这是一行普通文字。

#### 单行文本
使用方法：在任意一行开头键入1个Tab符或者4个空格。

    这里的文本只限于单行显示, 如果文字数量超出浏览器页面大小, 默认增加滑动条进行显示。

#### 多行文本
使用方法1：连续几行的文本开头键入1个Tab符或者4个空格。

    早上好
    中午好
    下午好
    
使用方法2: 使用一对各三个的反引号。

    `
    文字
    文字
    文字
    `

方法2示例效果:    
该方法同样可以用于[代码高亮](#代码高亮)

```plain
Good Morning
Good Afternoon
Good Night
```

### 文字高亮
采用一对反引号，可以使行内部分文字高亮，使用方法如下: 

    `Linux` `网络编程` `原创`

显示效果常用作文章标签:`Linux` `网络编程` `原创`    
有道云协作上的高亮效果，采取一对双等号进行标示：`==文字==`    
GitHub上不支持这一效果，无非是粗体或者引用样式。  

有道云上显示效果:==高亮文字==    
GitHub上显示效果: **高亮文字** or `高亮文字`

#### 代码高亮
采用一对三个反引号来包含代码，头部的三反引号后跟上编程语言名。    
格式如下：

    ```编程语言名  
    代码内容  
    ```
    
示例效果：

```Java
public static void main(String[]args){} //Java
```

```c
int main(int argc, char *argv[]) //C
```

```Bash
echo "hello GitHub" #Bash
```

```javascript
document.getElementById("myH1").innerHTML="Welcome to my Homepage"; //javascipt
```

```cpp
string &operator+(const string& A,const string& B) //cpp
```

### 斜、粗体、删除线
语法 | 效果
--- | ---
`*斜体1*` | *斜体1*
`_斜体2_` | _斜体2_
`**粗体1**` | **粗体1**
`__粗体2__` | __粗体2__
`***斜粗体1***` | ***斜粗体1***
`___斜粗体2___` | ___斜粗体1___
`~~删除线~~` | ~~删除线~~
`***~~斜粗体删除线~~***` | ***~~斜粗体删除线~~***
`___~~斜粗体删除线~~___` | ___~~斜粗体删除线~~___
`~~***斜粗体删除线***~~` | ~~***斜粗体删除线***~~

### 块引用
#### 块引用常用语文字注解，概念引用：
常使用`>`符号来创建引用效果，以下为示例效果    
实际上术语“little endian”（小端）和“big endian”（大端）出自Jonathan Swift的《格利佛游记》一书，其中交战的两个派别无法就应该从哪一端打开一个半熟的鸡蛋达成一致。-- 摘自《深入理解计算系统》P27
> **“端”（endian）的起源**  
以下是Jonathan Swift在1726年关于大小端之争历史的描述：  
“……下面我要告诉你的是，Lilliput和Blefuscu这两大强国在过去36个月里一直在苦战。战争开始是由于以下的原因：我们大家都认为，吃鸡蛋前，原始的方法是打破鸡蛋较大的一端，可是当今的皇帝的祖父小时候吃鸡蛋，一次按古法打鸡蛋时碰巧将一个手指弄破了，因此他的父亲，当时的皇帝，就下了一道敕令，命令全体臣民吃鸡蛋时打破较小的一端，违令者重罚。”

### 多级结构
> 交互界面
>> 视图控制器
>>> 父视图
>>>> 子视图

### 列表
#### 无序列表
常采用`-`来创建列表效果

- 姓名
- 年龄
- 籍贯

#### 多级无序列表
使用时只需要依次在该行的`-`前增加Tab符即可，无序列表默认到三级为止。

- 编程语言
    - 脚本语言
        - Python


#### 有序列表
一般情况下的有序列表格式为"数字.空格", 即"1. "

面向对象的三个基本特征:
1. 封装
2. 继承
3. 多态

#### 有序列表自动排序
即在首次使用时采取"1. ", 之后可以使用"任意数字. "    
**在Git上还可采用`*`来代替, 有道云平台不支持该语法**    

面向对象的七大原则

1. 开闭原则
1. 里氏转换原则
1. 依赖倒转原则 

#### 多级有序列表
1. 此乃一级有序列表
    1. 此乃二级有序列表, 数字显示为罗马数字
        1. 此乃三级有序列表, 数字显示为英文字母
            1. 此乃四级有序列表, 数字依然为英文字母

#### 复选框列表
复选框列表主要分两种形式：    
`- [x] 文字` 与 `- [ ] 文字`    
前者显示勾选效果，后者显示未勾选效果。

- [x] 需求分析
- [ ] 交付
 
### 图片
#### 网络图片
图片的基本格式为`![alt](URL Title)`  
`alt`：表示图片显示失败时的替换文本。    
`URL`：图片的网络地址, 如果引用当前仓库中的图片, 使用相对路径。    
`title`：表示鼠标悬停在图片时的显示文本（悬停文字需以""框选起来）。

#### GitHub图片
**如果使用其他GitHub仓库中的图片需注意格式为:`仓库地址/raw/分支名/图片路径/`，示例如下：** 
`https://github.com/LibertyLeo/MarkDown_Learning/raw/master/Markdown_Learning/Image/Lamp.gif`

**注意示例2的语法, 即在文章末尾绑定了该占位符"Lamp"的值:**
 `[Lamp]:https://github.com/LibertyLeo/MarkDown_Learning/raw/master/Markdown_Learning/Image/Lamp.gif`  
更多"占位符"的便捷方法, 参见[链接](#链接)

No. | 语法 | 显示效果
--- | :---: | ---
1 | `![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")` | ![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo") 
2 | `![][Lamp]` | ![][Lamp]

### 链接
#### 外部网页链接
第一种样式为常规语法。    
第二张样式为特殊语法：相当于指定一个占位符的存在（位于表格第二行 ），之后再进行值绑定（位于表格第三行），值绑定的操作一般可以放在文章的末端，可集中归纳在一起。

No. | 语法 | 效果
:---: | --- | :---:
1 | `[我的博客](http://blog.csdn.net/libertyleo "悬停显示")` | [我的博客](http://blog.csdn.net/libertyleo "悬停显示")
2 | `[My ZhiHu][zhihu]` | [My ZhiHu][zhihu]
2 | `[zhihu]:https://www.zhihu.com/people/LibertyLeo"`| 

#### Git仓库链接
语法 | 效果
--- | ---
`[ReadMe](/README.md)` | [ReadMe](/README.md)
`[CSDN](/Markdown_Learning/Image/csdn.png)` | [CSDN](/Markdown_Learning/Image/csdn.png)

#### 图片网页链接
图片网页链接即显示图片, 点击图片跳转链接网址。    
普通链接[ ]显示的为链接显示的文本, 而图片链接[ ]显示的为链接显示的图片。    
混合语法固然可以, 但使用起来不方便, 可采用"占位符"来简化操作。

No. | 语法 | 效果
--- | --- | ---
1 | `[![weibo_logo]](http://weibo.com/zijianlei)` | [![weibo_logo]](http://weibo.com/zijianlei)
2 | `[![](/Markdown_Learning/Image/zhihu.png "我的知乎")][zhihu]` | [![](/Markdown_Learning/Image/zhihu.png "我的知乎")][zhihu]
3 | `[![csdn_logo]][csdn]` | [![csdn_logo]][csdn]

图片和链接本身均支持"占位符"形式，所以图片链接也可以采取简便用法，如示例3。    
此时鼠标悬停时显示的文字是图片的titie，而非链接本身的title。

### 锚点
锚点: 常用于网页制作中的超链接, 起到一个定位的作用。

语法 | 效果
--- | ---
`[回到顶部](#readme)` | [回到顶部](#readme)

### 表格
表格格式如下，一般分为两种，`-`需使用三个及以上:    
(有道云中仅仅使用一个`-`及以上即可)

```plain
表头1 | 表头2
--- | ---
表格内容 | 表格内容
表格内容 | 表格内容
```

```plain
| 表头1 | 表头2 |
| --- | --- |
| 表格内容 | 表格内容 |
| 表格内容 | 表格内容 |
```

表头1 | 表头2
--- | ---
表格内容 | 表格内容
表格内容 | 表格内容

| 表头1 | 表头2 |
| --- | --- |
| 表格内容 | 表格内容 |
| 表格内容 | 表格内容 |

#### 对齐方式
表格默认表头均居中显示，余下表格内容默认左对齐。

```
左对齐 | 居中 | 右对齐  
:--- | :---:| ---:  
内容1 | 内容2 | 内容3  
```

左对齐 | 居中 | 右对齐
:--- | :---: | ---:
one word | More words than others | more words
test | example | case
left | center | right

### 表情Emoji
**Emoji表情支持GitHub的MarkDown**，输入不同的符号`:blush:`，显示效果:blush:    
更多符号可以参见本仓库中的[Emoji.md](./emoji.md)

[csdn]:http://blog.csdn.net/libertyleo "我的博客"
[zhihu]:https://www.zhihu.com/people/LibertyLeo "LibertyLeo's zhihu"
[weibo]:http://weibo.com/zijianlei
[baidu_logo]:http://www.baidu.com/img/bdlogo.gif "百度logo"
[weibo_logo]:/Markdown_Learning/Image/weibo.png "点击图片进入我的微博"
[csdn_logo]:/Markdown_Learning/Image/csdn.png "我的csdn博客"
[Lamp]:https://github.com/LibertyLeo/KnowledgeFortress/raw/master/Markdown_Learning/Image/Lamp.gif
