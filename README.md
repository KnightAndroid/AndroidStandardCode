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
* [基本规范](#基本规范)
* [开发工具Android Studio规范](#开发工具AndroidStudio规范)
* [APP包命名规范](#APP包命名规范)
* [分包命名规范](#分包命名规范)
* [模块命名规范](#模块命名规范)
* [类命名规范](#类命名规范)
* [接口规范](#接口规范)
* [变量命名](#变量命名)

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
   
#### 基本规范
* 删除无用变量，代码，无用的引入，禁用s1,s2,s3,y1这种命名
* 代码尽量不要出现中文，注释除外，代码中通过`strings.xml`来引用显示中文
* 布局文件中的字体大小，`margin`和`padding`的值也要放在`dimens.xml`中
* 在一个`View.OnClickListener`中处理所有的点击事件逻辑，集中方便管理
* `strings.xml`中使用`%1d`实现字符串的通配
* TextView字体大小单位用sp，距离用dp
* xml中用`layout_marginStart/End`来代替`layout_marginLeft/Right`，`padding`同理
* 数据类型转换一定要加校验
* 禁止在四大组件(Activity，Service，BroadcastReceiver，ContentProvider)中主线程做耗时操作
* 注册反注册要成对出现(Eventbus,广播)
* 资源对象不再使用时要及时关闭(Cursor,文件流,Bitmap,视频)，当确保不在使用这些资源时，必须关闭，否在会引起泄漏(Cursor.close(),BufferefReader.close()，Bitmap.recycle())。**注意：在 2.3.3 及以下需要调用 recycle()函数，在 2.3.3 以上 GC 会自动管理**
    ```
    if (Build.VERSION.SDK_INT <= 10) {
        bitmap.recycle();
    }
    bitmap = null;
    ```
* 禁止在非UI线程(一般指主线程)进行view的相关操作
* 不要通过Intent在基础组件传递大数据(binder transaction 缓存为1MB)
* 操作本地数据库放在子线程中去，多线程写入数据库时，需要使用事务，以免出现同步问题
* 使用png或者jpg图片时，一定要自己先使用压缩工具(tinypng)去进行压缩处理
* 不要把敏感信息打印到log中，线上一定关闭所有log输出
* 用`equals`方法时，用`xxxx.equals(object)`，不用`object.equals(xxxx)`，因为object对象有可能为空，导致空指针异常
* 一个类不被继承时，要用final来修饰
* 看情况来用访问修饰符`public,private,protect`，如：一个字段或者方法不需要被外部访问，用`private`修饰
* 应用的图标放在**mipmap**目录下，其他图片资源放在`drawable`目录下


#### 开发工具AndroidStudio规范 
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

#### APP包命名规范
* 【强制】全部小写，以防止和类名、接口名冲突，若有多个单词则直接连接在一起，不能有下划线
    * 符合规范的示例：`com.example.deepspace`
    * 不符合规范的示例：`com.wxample.deepSpace`、`com.example.deep_space`
    
* 【强制】包名前缀必须是能区分一个组织的顶级域名，倒叙写，比如`com.apple`   

* 【强制】包名子路径不能包含java关键词，比如int、protect。

#### 分包命名规范
一个项目肯定会分很多的包，不可能把全部文件放在一个包下，分包是为了**统一管理项目文件**。
* 【推荐】按功能或者作用进行分包，如：utils(工具)、widget(组件)、adapter(适配器)，按功能分包容易找到对应的类位置、容易管理、高度抽象、更容易封装。

* 【强制】不要在对应包名放无关的类或者不属于这个包下的类
#### 模块命名规范
很多时候app会分很多模块，这些模块命名必须简单易懂。
* 【强制】不能有大写中文，全部小写英文
```
base
home
live
database
```

* 【强制】模块混淆配置，不使用`proguardFiles`语句，使用`consumerProguardFiles`,理由如下：
    * `consumerProguardFiles`下的proguard会被打进aar包中，而`proguardFiles`配置的proguard不会被打进aar中。
    * `proguardFiles`下的proguard文件只作用于库文件代码，只在编译发布aar的时候有用，在将库文件作为模块添加到App模块中，库文件的`consumerProguardFiles`配置的proguard文件则会追加到App模块的proguard配置文件中，作用于整个app。

```
buildTypes {
    release {
        //反例
        //proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        //正例
        consumerProguardFiles 'proguard-rules.pro'
    }
}
```

* 【推荐】增加资源命名前缀限制，为了避免模块间资源合并冲突，可以用模块名或者功能作为前缀
```
 android {
    //限定资源前缀命名
    resourcePrefix "wechat_"
 }
```

#### 类命名规范
* 【强制】 类名必须按照`UperCamelCase`(大驼峰)风格类命名，避免单词缩写

    * 业务类：按照**模块+类型**进行命名
    * 技术类：按照**作用+类型**进行命名
|   类  |  描述 | 例子 |
| :-----: | :----: | :----: |
|  基础类 |  Base + 类型 | BaseActivity<br>BaseFragment
|  Activity 类 |  界面+Activity | HomeActivity
|  Fragment类|  界面+Fragment | HomeFragment
|  自定义View |  功能+View/ViewGroup(组件类型) | CircleView/ShapeViewGroup
|  Adapter类 |  功能+Adapter | ShoeDetailAdapter
|  工具类 |  功能+Utils | LogUtils(日志类)<br>GsonUtils(json解析类)<br>ThreadPoolUtils(线程类)
|  抽象类 |  Abstract+类型 | AbstractCircleView<br>AbstractTest
|  异常类 |  异常类型+Exception | NullPointerException(空指针异常)<br>ArithmeticException(运算错误异常)
|  接口类 |  功能(业务模块)+Interface<br>功能+Listener | UserInterface<br>OcrTextInterface<br>OnClickListener
|  接口实现类 |  功能(业务模块)+InterfaceImpl | UserInterfaceImpl<br>OcrTextInterfaceImpl

#### 接口规范
* 【推荐】如果功能比较简单，单用在某个类伤，接口可以写在内部，如果方法功能比较多，建议抽取写成外部，如：
```
public class TextClickUtils {

    public interface OnClickToWebListener{
        void goWeb();
    }

    private OnClickToWebListener mOnClickToWebListener;

    public void setOnClickWebListener(OnClickToWebListener mOnClickToWebListener){
         this.mOnClickToWebListener = mOnClickToWebListener;
    }
}

```
```
public interface OnHttpListener<T> {
    /**
     * 请求开始
     */
    default void onStart(Call call) {}

    /**
     * 请求成功
     */
    void onSucceed(T result);

    /**
     * 请求出错
     */
    void onFail(Exception e);

    /**
     * 请求结束
     */
    default void onEnd(Call call) {}
}
```

* 【推荐】接口实现的类所实现方法要有@link

```
public class HttpCallback<T> implements OnHttpListener<T>,OnDownloadListener {

    /**
     * {@link OnHttpListener}
     * @param call
     */
    @Override
    public void onStart(Call call) {
 
    }


    @SuppressWarnings("unchecked")
    @Override
    public void onSucceed(T result) {
 
    }

    @Override
    public void onFail(Exception e) {

    }

    @Override
    public void onEnd(Call call) {

    }

    /**
     * {@link OnDownloadListener}
     * @param file
     */
    @Override
    public void onStart(File file) {

    }

    @Override
    public void onProgress(File file, int progress) {

    }

    @Override
    public void onComplete(File file) {

    }

    @Override
    public void onError(File file, Exception e) {

    }

    @Override
    public void onEnd(File file) {

    }
}
```
方便快速找到接口类的位置

#### 变量命名
变量包括了常量、局部变量、全局变量，统一规则：

* 是名词或者动词类型，禁止拼音和英文混合方式
* 变量按照`lowerCamelCase`风格,必须遵从小驼峰形式
* 常量命名全部大写，单词间用下划线隔开，为了意思表达完整，不要嫌弃名字过长
* 局部变量或者公开的成员变量以作用来命名。如：
```
public String mobile
public TextView mobileTextView
public LinearLayout mobileLinearLayout
```
* 【推荐】非公开的成员变量以小`m`开头，统一
```
private String mMobile
private TextView mMobileTextView
private LinearLayout mMobileLinearLayout
```
* 【强制】布尔值命名规范，不要在前缀加is，部分框架解析会引起序列化错误(com.alibaba.fastjson.util.TypeUtils.computeGetters有对is开头的方法进行处理)
```
//反例
private boolean isPrintLog
//正例
private boolean printLog
```
* 【推荐】静态变量则用小s开头，统一
```
private static ProxySelector mProxySelector 
```


|   类型  |  描述 | 例子 |
| :-----: | :----: | :----: |
|  常量 |  大写或者与`_`混合,kotlin一定要 const val,Java 要用 static final 修饰 | const val MAX_STOCK_COUNT = 5<br>static final MAX_STOCK_COUNT = 5 
|  变量 |  遵从`lowerCamelCase` | private boolean mDestroyed<br> var doorNumber:Int = 5
|  临时变量 |  整型：`i,j,k` | for (int i = 0; i < len; i++) 

**注意：Kotlin中只读变量用`val`，可变变量用`var`**

* 【推荐】若一个类中有常量或者变量的时候，声明常量在前，变量在后，如：
```
public class DemoTest {
    /*
     * 注释....
     */ 
    public static final int RESULT_CANCELED    = 0;
    /*
     * 注释....
     */ 
    private int mTitleColor = 0;
}
```
* 【强制】 在long或者Long赋值时，数值后使用的大写L，不能是小写的l，小写容易跟数字1混淆，造成误解
如：
```
//反例
Long a = 2l,//不知道是21还是2

//正例
Long number = 2L;
```

* 【推荐】 不要使用一个常量类维护所有常量，要按功能去进行分类，分开管理，放在一个类中，日而久之，杂乱无章，不利于理解和维护

 #### 参考文章
* [https://google.github.io/styleguide/javaguide.html](https://google.github.io/styleguide/javaguide.html)


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


     


        
        