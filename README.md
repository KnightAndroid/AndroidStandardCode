* **什么叫规范？**

    对于某一工程作业或者行为进行定性的信息规定。主要是因为无法精准定量而形成的标准，所以，被称为规范。在平时日常开发中，编写代码如果不遵守编译器规定，编译器就会在编译的时候报错，这个规定就是这个语言的规则，有一种规定是一种人为约定成俗的，即使不按照规定也不会出错，而这种规定就叫做规范。
    
    假如大家都不按照规范来写代码，虽然运行不会出错，但是代码会很乱，到后面也很难维护。当我们养成一种不好的代码习惯后，这种习惯也许会陪伴自己的职业生涯，也许将来面试或者工作会让自己失去很多机会。
* **代码规范的好处**

    遵守代码规范可以说让自己赢在写代码之前上。**我自己规范代码就是一点：面向理解编程**。代码规范最直观的好处就是看起来整洁舒服，现在假如不按规范写几万行代码后，等过一段时间再看自己写的代码就会非常吃力，更不要说其他人看了，所以代码要尽可能得规范，个人觉得在怎么烂得代码注释要到位，把重点的方法写好注释，如：入参意义，方法功能等。按照软件工程的思想，注释要占整个文档的20%以上，因此注释要写的尽可能详细，格式也要规范。
    1. **降低成本维护成本提高合作效率**
       随着版本的迭代和代码行数的增加，开发过程中的代码质量直接影响维护和扩展成本，当有强制的统一代码规范后，每位开发者阅读他人代码就变得简单，使代码可读性大大提高，每个人看到任何一段代码都会非常熟悉，想要一个可以日后维护，扩展轻松的项目，那么制定一个开发规范是很有必要的。
    
    2. **可以减少Bug的处理**
        对输入和输出的参数进行规范(如禁用Map入参出参，非空以及必传校验)，规范的异常捕抓处理(如业务类异常，系统类异常)，规范的日志输出(如每个请求的唯一id，入参，当出现错误时会输出异常类型，出错行数，出错方法等)。这些规范都能避免类型空指针异常，转换异常等bug的出现，就算出现bug进行查找解决也变得更加简单。
        
    3. **有助于代码审查**
        代码审查并不是所有公司都有的开发流程，如果没有规范的代码进行审查会加重工作量和难度，代码规范能使开发统一，减少审查拿督，让代码审查有据可查，提高审查效率效果，也能促进代码审查工作的开展和实施。
    
    4. **开发过程规范化**
        通过在开发过程中采取一些规范开发来保证开发团队的代码质量，使开发过程更加规范，成就高质量代码，减少测试的投入，促进自身乃至团队的技能提高。
    5. **养成习惯**
        很多时候自己写的不规范代码，进行查找某个功能某个方法或者出现bug的时候进行调试的时候而乱了头绪。更何况其他人看自己代码了，像一些出名的开源框架如：Glide,okhttp写的开源库都是很规范的，但是不是规范就能代表很高水平，规范有利于来理解框架所用到的设计模式，提升自己的开发水平。想要自己达到高水平的程序员，先从小事做起，规范代码，规范自己。

### 目录
* [前言](#前言)
* [开发工具Android Studio规范](#开发工具AndroidStudio规范)

#### 前言
   * 代码规范原则
     
     * **代码简洁易懂，逻辑清晰**因为软件是需要人来维护的。这个人在未来很可能不是你。所以首先是为人编写程序，其次才是计算机。
         
         1. 不要过分追求技巧，降低程序的可读性。
         2. 简洁的代码可以让bug无处藏身。要写出明显没有bug的代码，而不是没有明显bug的代码。
     * **面向变化编程，而不是面向需求编程**本次迭代不能仅仅为了当前的需求，写出扩展性强，易修改的程序才是负责任的做法，对自己负责，对公司负责。
     * **先保证程序的正确性，防止过度工程**过度工程（over-engineering）：在正确可用的代码写出之前就过度地考虑扩展，重用的问题，使得工程过度复杂，`《编程的智慧》`里面有说到：
         1. 先把眼前的问题解决掉，解决好，再考虑将来的扩展问题。
         2. 先写出可用的代码，反复推敲，再考虑是否需要重用的问题
         3. 先写出可用，简单，明显没有bug的代码，再考虑测试的问题
         
   * 代码规范目标
   
       * **提升质量意识，降低问题发生和维护成本**
       * **统一标准，提升协作效率**
       * **追求卓越工匠精神，打磨精品代码**
       * **规范自己，榜样他人**
   对于有代码例子中，“说明”对代码进行了扩展和解释，“正例”意思是建议提倡这种编码方式；“反例”意思是错误的编码方式，不提倡甚至禁止这种编码习惯方式。
   
#### 开发工具Android Studio规范 
因为目前都是使用Android Studio来进行开发安卓开发，所以工具基于Android Studio来说明。

* 【强制】使用稳定的Android Studio版本进行开发，Android Studio会有四个版本分别是：
    * Stable Channel(稳定版)，我们一般使用这个版本进行开发
    * Beta Channel(预发布版本)，这个是预发布版本,在发布稳定版之前先发布这个版本，并获取问题反馈进行修复，Beta版本会将与一个新的稳定版本一起被更新
    * Dev Channel(开发版本)，金丝雀版本经过完整测试后会提到这个版本
    * Canary Channel(金丝雀版本)，大约周更，这是最早的发布的版本，这个版本会有下一个稳定版本最新的功能
    **建议：可以同时安装稳定版和金丝雀版本**。
    
   我们可以选择【Help】- 【Check for Updates...】进行查看对应版本更新
   ![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_checkupdates.png)
   
   点击【Configure updatea】进行跟新配置，查看对应不同的版本
   ![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_channel.png)
 
* 【推荐】使用统一版本的Android Stuido进行开发，如：4.1.1
* 【强制】使用统一的gradle构建工具版本，在项目根目录【gradle】-【gradle-wrapper.properties】进行设置
* 【强制】使用统一的gradle插件版本配置，在项目根目录【build.gradle】下进行设置
* 【强制】编码格式为UTF-8
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_filecode.png)
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_codesetting.png)
* 【强制】删除多余的import,手动清除可以点击菜单栏【Code】-【Optmize Imports】,可以设置自动清除
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_cancelimport.png)
* 【强制】禁止类文件中出现`import.*`,意思就是导入的类包必须是单路径引用，必须列出详细的import内容，可以设置下自动合并import的包名
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_changeimport.png)
kotlin设置**Use single name import**即可，Android Studio默认就是这个选项

* 【推荐】每行代码字符数不超过160个字符，在【Editor】-【Code Style】设置，Android Studio 默认就是这个字符数
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_codemax.png)

* 【强制】每个类必须带有版权信息，创建人信息，描述，对自己代码负责，可根据自己公司要求做出变化
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_filemessage.png)

* 【强制】必须安装[阿里巴巴代码](https://plugins.jetbrains.com/plugin/10046-alibaba-java-coding-guidelines)约束插件
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_alibabaplugins.png)
到这里开发工具就设置完毕。
## License

```text
Copyright 2021 Knight

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```


     


        
        