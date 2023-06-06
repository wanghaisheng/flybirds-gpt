# flybirds-gpt
gpt empower about UI auomation testing. help gen scripts that fiybirds consume

没有openai账号的，可以试试这个共享链接，需要梯子

https://chat-shared1.zhile.io/


## 我的想法

假设我们的场景是测试登录功能是否完善，

1.最傻的是告诉他一句话，我想测试谷歌网站/某app的登录功能是否完善，完了它直接能出feature script

2.退而求其次，我想录制一个简单的登录操作，自动生成一个feature script

3.我把第一步的测试分解成一个个步骤，可以是纯自然语言形式，

a.访问网址，打开网页

b.检查网页是否成功加载

c 登录按钮是否加载

d 登录按钮是否可以点击

e 输入用户名和密码

f 点击登录

将这些分解步骤输入给gpt，它直接出feature script


## dsl 规则转换成prompts

https://github.com/wanghaisheng/flybirds-gpt/blob/main/DSL-rules.md

## 将自然语言转换成dsl

主要是替换其中选择器这种。

根据dsl规则转换prompts，我们可以输入下面的内容：
>进入页面根据选择器**button**检查内容是**登录**的元素是否渲染完成，改写成什么

但实际上通常我们会说
>进入页面检查登录按钮是否渲染完成，

如何把这句话利用prompt转成上面那句，这个规则该怎么表达。需要知道登录按钮的**选择器**是什么，登录按钮的**文本内容**是什么


对于进入url页面检查元素是否渲染完成来说，
第一步，我们需要获取元素的选择器表达式和元素的文本内容，可以使用：
```

If someone asks you to perform a task, your job is to come up with a series of playwright Python commands that will perform the task. 
There is no need  to include the descriptive text about the program in your answer, only the commands.
Note that the version of playwright is the latest.

Begin Your job:  
第一步：进入url,找到元素 ,无需给出代码，给出元素的选择器的名称是什么，选择器表达式是什么，以及该选择器的文本内容是什么即可
第二步：利用第一步中得到的选择器名称和选择器对应的文本内容，改写进入页面根据选择器button检查内容是登录的元素是否渲染完成这句话中对应部分：进入页面根据选择器[选择器名称]检查内容是[选择器对应的文本内容]的元素是否渲染完成，输出改写好的语句
第三歩：我们的转换规则如下：进入新的页面时根据选择器检查指定元素是否渲染完成，还可以设置超时时长，那么改写成：页面渲染完成出现元素[选择器{, path=false, multiSelector=false, timeout=10}]，对于选择器，不仅可以直接使用选择器表达式 ，同时可以设置选择器对应的内容是否为我们设定的内容，格式为 选择器=设定的内容，比如根据选择器text检查机票是否渲染完成，其中选择器是text，我们设定的内容是机票，可以改写成页面渲染完成出现元素[text=机票]，
```

这样子，这条规则的调教就完成了，接下来问他

```
那么进入baidu.com，检查登录是否渲染完成应该改写成什么，无需code代码，给出改写好的表达即可

```

```
第一步：
选择器的名称：按钮
选择器表达式：button
选择器的文本内容：登录

第二步：
进入页面根据选择器按钮检查内容是登录的元素是否渲染完成。

第三步：
页面渲染完成出现元素[button=登录]
````


这样，我们就完成了输入:

**进入baidu.com，检查登录是否渲染完成**,得到了flybirds scripts **页面渲染完成出现元素[button=登录]**





REF
https://github.com/mpetrovich/gherkin-scenario-builder

