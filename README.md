* **什么叫规范？**

    对于某一工程作业或者行为进行定性的信息规定。主要是因为无法精准定量而形成的标准，所以，被称为规范。在平时日常开发中，编写代码如果不遵守编译器规定，编译器就会在编译的时候报错，这个规定就是这个语言的规则，有一种规定是一种人为约定成俗的，即使不按照规定也不会出错，而这种规定就叫做规范。
    
    假如大家都不按照规范来写代码，虽然运行不会出错，但是代码会很乱，到后面也很难维护。当我们养成一种不好的代码习惯后，这种习惯也许会陪伴自己的职业生涯，也许将来面试或者工作会让自己失去很多机会。
* **代码规范的好处**

    我写过没有规范的代码，也深知其危害，遵守代码规范可以说让自己赢在写代码之前上。**我自己规范代码就是一点：面向理解编程**。代码规范最直观的好处就是看起来整洁舒服，现在假如不按规范写几万行代码后，等过一段时间再看自己写的代码就会非常吃力，更不要说其他人看了，所以代码要尽可能得规范，个人觉得在怎么烂得代码注释要到位，把重点的方法写好注释，如：入参意义，方法功能等。按照软件工程的思想，注释要占整个文档的20%以上，因此注释要写的尽可能详细，格式也要规范。
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
* [变量命名规范](#变量命名规范)
* [方法命名规范](#方法命名规范)
* [资源命名规范](#资源命名规范)
    * [布局资源文件命名规范](#布局资源文件命名规范)
    * [图片资源文件命名规范](#图片资源文件命名规范)
    * [图片样式文件命名规范](#图片样式文件命名规范)
    * [String命名规范](#String命名规范)
    * [Color命名规范](#Color命名规范)
    * [动画资源命名规范](#动画资源命名规范)
    * [布局资源id命名](#布局资源id命名)
    * [Style命名规范](#Style命名规范)
* [XML规范](#XML规范)
    * [预览属性约定](#预览属性约定)
* [版本迭代命名规范](#版本迭代命名规范) 
* [注释规范](#注释规范)
    * [方法注释](#方法注释)
    * [类全局变量注释规范](#类全局变量注释规范)
    * [方法内注释规范](#方法内注释规范)
* [代码样式规范](#代码样式规范)
    * [代码换行规范](#代码换行规范)
    * [类成员顺序规范](#类成员顺序规范)
* [依赖第三方库规范](#依赖第三方库规范)
* [异常捕抓规范](#异常捕抓规范)
* [参考文章](#参考文章)

#### 前言
   * 代码规范原则
     
     * **代码简洁易懂，逻辑清晰**因为软件是需要人来维护的。这个人在未来很可能不是你。所以首先是为人编写程序，其次才是计算机。
         
         1. 不要过分追求技巧，降低程序的可读性。
         2. 简洁的代码可以让bug无处藏身。要写出明显没有bug的代码，而不是没有明显bug的代码。
     * **面向变化编程，而不是仅仅面向需求编程**本次迭代不能仅仅为了当前的需求，写出扩展性强，易修改的程序才是负责任的做法，对自己负责，对公司负责。
     * **先保证程序的正确性，防止过度工程**`过度工程（over-engineering）`：在正确可用的代码写出之前就过度地考虑扩展，重用的问题，使得工程过度复杂，`《编程的智慧》`里面有说到：
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
* 删除未使用的局部变量、方法参数、私有方法、字段和多余的括号，无用的引入，禁用s1,s2,s3,y1这种命名
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
* 不要在**Application**对象中缓存数据(因为有可能会因系统内存不足而进行回收，但是这时候重新打开应用的时候，会创建一个新的Application对象，但是可能会启动回收前用户打开的界面，这样会造成缓存数据重新初始化，造成不可预期的结果)
* 判断是否空集合用`Collection.isEmpty`比`Collection.size == 0`获得更好的性能，判断是否为`null`可以用`CollectionUtils.isEmpty(collection)`
* 循环使用`StringBuilder`比`String`拼接，替换字符串更优
* 工具类中屏蔽构造函数，一般来说工具类是一堆静态字段和函数的集合，其不应该被实例化


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

#### 变量命名规范
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
    public static final int RESULT_CANCELED = 0;
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

#### 方法命名规范
* 【强制】方法名都以`lowerCamelCase`风格编写，是名词或者动词类型，禁止拼音和英文混合方式

|   方法  |  说明 | 
| :-----: | :----: | 
|  initXXX() |  初始化(initData、initView) | 
|  getXXX() |  返回某个值(getTextSize、getTextPadding) | 
|  setXXX() |  设置某个属性值(setTextSize、setTextPadding) | 
|  checkXXX()、isXXX() |  返回布尔类型的值(checkLogin) | 
|  showXXX() |  显示View或者页面提示信息(showNetworkMessage) |
|  updateXXX() |  更新数据或者更新页面(updateLoginMessage) |
|  saveXXX()、insertXXX() |  保存数据(saveLoginMessage)、插入数据(insertArticle) |
|  resetXXX() |  重置数据或者视图状态等(resetLoginMessage)、插入数据(insertArticle) |
|  clearXXX() |  清除数据(clearLoginMessage) |
|  removeXXX() |  移除数据(removeLoginMessage) |
|  deleteXXX() |  删除数据(deleteLoginMessage) |
|  queryXXX() |  查询数据(queryLoginMessage) |

#### 资源命名规范
##### 布局文件命名规范
* 【推荐】 **模块+类型**进行命名，采用下划线命名方式

|   布局  |  例子 | 
| :-----: | :----: | 
|  activity |  home_activity.xml |
|  fragment |  home_fragment.xml |
|  adapter |  home_articles_adapter.xml |
|  dialog |  home_articles_dialog.xml |
|  menu |  menu_item.xml |

对`layout`可以进行分包处理，在`build.gradle`文件下配置,例子如下：
```
android {
    main {
        res.srcDirs =
                    [
                            'src/main/res/layouts/activitys',
                            'src/main/res/layouts/fragments',
                            'src/main/res/layouts/adapters',
                            'src/main/res/layouts/items',
                            'src/main/res/layouts/dialogs',
                            'src/main/res/layouts',
                            'src/main/res'

                    ]
    }
}
```
配置完编译一下，结构如下：
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_resource.png)

##### 图片资源文件命名规范
* 【推荐】如果是与业务相关的，直接以**模块(页面)+用作view的缩写+类型**，采用下划线命名方式，如：

|   图片  |  例子 | 
| :-----: | :----: | 
|  png |  home_iv_cancel_ic.png(首页关闭图标) |
|  png |  wecaht_iv_share_link_ic.png(wechat模块下分享链接图标) |
|  jpg |  message_tv_delete_ic.jpg(message模块下删除图标) |
|  jpg |  message_rl_main_bg.jpg(message模块下主页的背景图片) |

* 【推荐】如果是多个业务都用一个图标，或者和业务无相关，直接以**作用+类型**，采用下划线命名方式，如：

|   图片  |  例子 | 
| :-----: | :----: | 
|  png |  close_ic.png(关闭图标) |
|  png |  share_link_ic.png(分享链接图标) |
|  jpg |  copy_ic.jpg(复制图标) |
|  jpg |  splash_bg.jpg(复制图标) |

有些开发者以`类型`开头命名(`ic_copy.png`、`ic_share_link.png`、`bg_splash.jpg`)也没问题,这个看自己和公司规范

#####  图片样式文件命名规范
* 【推荐】如果是与业务相关的，直接以**模块(页面)+用作view的缩写+类型**，采用下划线命名方式，如：

|   名称  |  例子 | 
| :-----: | :----: | 
|  selector |  login_btn_rect_selector.xml(登录按钮直角样式) |
|  selector |  live_share_tv_selector.xml(直播分享样式) |
|  selector |  register_btn_round_selector.xml(注册按钮圆角样式) 

* 【推荐】如果是非业务的资源，以**作用+用作view的缩写+类型来命名**，采用下划线命名方式，如：

|   名称  |  例子 | 
| :-----: | :----: | 
|  selector |  btn_rect_selector.xml(通用按钮直角样式) |
|  selector |  top_btn_round_selector.xml(通用上部分按钮圆角样式) |

有些开发者以`类型`开头命名(`selector_btn_rect.xml`、`selector_top_btn_round.xml`)也没问题,这个看自己和公司规范

##### String命名规范
* 【推荐】项目适配了多语种，没有特殊需要 则严禁写死在代码里或者布局文件中，将资源定义在`string.xml`文件中
* 【推荐】以**模块(页面)+功能**，采用下划线命名方式，如：
```
<!--主模块-->
<string name="home_cancel">取消</string>
<string name="home_save">保存</string>
<string name="home_search_histroy">搜索历史</string>
<string name="home_search_hint">请输入搜索关键字</string>

<!--设置模块-->
<string name="set_language_mode">设置语言模式</string>
<string name="set_title">设置</string>
<string name="set_logout">退出</string>
<string name="set_clear_cache">清除缓存</string>

<!--注册模块-->
<string name="register_title">注册</string>
<string name="register_account">注册账号</string>
<string name="register_account_hint">请输入长度不超过16位，包含数字英文大小写字母的账号</string>
<string name="register_password_hint">请输入密码</string>
<string name="register_password_again">请在一次输入密码</string>
<string name="register_password_input_error">密码输入错误</string>

<!--广场模块-->
<string name="square_title">广场</string>
<string name="square_share_article_success">分享文章成功</string>
<string name="square_articel_title_input">请输入文章标题</string>
<string name="square_articel_link_input">请输入以：http或者https开头的文章链接</string>
<string name="square_share_article_confim">分享文章</string>
```

* 【推荐】有时候可能多个模块都需要用，以**通用前缀+作用**，采用下划线命名方式，如：

```
<string name="common_loading">加载中...</string>
<string name="common_cancel">取消</string>
<string name="base_confim">确定</string>
<string name="base_save">保存</string>
```

##### Color命名规范
* 【推荐】适配了深色模式下，没有特殊需求严禁直接定义在布局文件中
* 【推荐】以**模块(页面)+作用**，采用下划线命名方式，如：
```
<!--登录按钮颜色-->
<color name="login_button_color">#FFFFFFFF</color>
<!--注册按钮颜色-->
<color name="register_button_color">#FFFFFFFF</color>
<!--微信分享按钮颜色-->
<color name="wechat_share_button_color">#FFFFFFFF</color>
<!--信息未读颜色-->
<color name="mesage_unread_color">#FFFFFFFF</color>
```
* 【推荐】有时候可能多个模块需要引用，以**通用前缀+作用**，采用下划线命名方式，如：
```
<!--通用按钮按压颜色-->
<color name="common_button_pressed_color">#FFFFFFFF</color>
<!--通用按钮按压颜色-->
<color name="common_button_default_color">#FFFFFFFF</color>
<!--通用分割线颜色-->
<color name="common_line_color">#FFFFFFFF</color>
```

* 【不推荐】 在实际过程中，会遇到下面这种命名方式，如：
```
<name=""color_999999>#999999</color>
```
这种命名规则虽然以颜色值为命名，看上去很清楚显示用了什么颜色值，但是随着版本迭代，假如后面项目有500个地方用了这个颜色值，但是不知道这个颜色值是用来干什么的，可能后面某个需求某些个按钮文本颜色更改(将这个颜色值改为另外一个颜色)，那么是，这时候你就要区分这500个地方，哪些需要改哪些不需要改。

##### 动画资源命名规范
Android分为属性动画和视图动画，视图动画包括补间动画和帧动画，属性动画文件需放在`res/animator/`下，视图动画放在`res/anim/`下。
* 【推荐】以`模块(页面)+用作view+作用`，采用下划线命名方式，如：

|   名称  |  说明 | 
| :-----: | :----: | 
|  login_btn_fade_in |  登录模块按钮淡入 |
|  login_btn_fade_out |  登录模块按钮淡出 |
|  login_tv_push_down_in |  登录模块文本从下方推入 |
|  login_tv_oush_down_out |  登录模块文本从下方推出 |
|  message_btn_zoom_enter |  消息模块按钮变形进入 |
|  message_tv_slide_in |  消息模块文本滑动进入 |
|  login_tv_oush_down_out |  登录模块文本从下方推出 |


##### 布局资源id命名
* 【推荐】以`控件缩写+模块名+作用`，采用下划线命名方式，如：

|   类型  |  规范 | 示例 | 解释
| :-----: | :----: | :----: | :----: | 
|  TextView | tv_xxx | tv_login_account | 登录界面账号文本
|  EditText | et_xxx_| et_login_account | 登录界面账号输入
|  ImageView | iv_xxx_| iv_login_head | 登录界面头像显示
|  CheckBox | cb_xxx_| cb_login_save_password | 登录界面记住密码选择
|  LinearLayout | ll_xxx_| ll_login_account | 登录界面账号线性布局
|  Recycleview | rv_xxx_| rv_home_article | 首页界面文章列表
|  ConstraintLayout | cl_xxx_| cl_home_root | 首页界面根布局
|  FrameLayout | fl_xxx_| fl_mine_root | 我的界面根布局

##### Style命名规范
`<style>`使用`UperCamelCase`大驼峰命名法。
* 【推荐】对于一些常用并且样式统一的的控件`Button`、`TextView`的样式进行抽取，避免属性重复定义
* 【推荐】主题相关的以`Thmem`来结尾，命名尽可能简单易懂
* 【推荐】控件相关的以`Style`来结尾，命名尽可能简单易懂
```
<!-- 应用主题样式 -->
<style name="AppTheme" parent="Theme.AppCompat.DayNight.NoActionBar">
     <item name="colorPrimary">@android:color/white</item>
     <item name="colorPrimaryDark">@android:color/white</item>
     <item name="colorAccent">@android:color/white</item>
     <item name="windowActionBar">false</item>
     <item name="windowNoTitle">true</item>
     <item name="android:windowAnimationStyle">@android:style/Animation.Toast</item>
</style>

<!-- 启动页主题样式 -->
<style name="AppSplashTheme" parent="Theme.AppCompat.Light.NoActionBar">
    <item name="android:windowBackground">@drawable/bg_splash</item>
    <item name="android:windowNoTitle">true</item>
    <item name="android:windowFullscreen">true</item>
</style>

<!-- 闪屏页主题样式 -->
<style name="FullScreenTheme" parent="Theme.AppCompat.DayNight.NoActionBar">
    .....
</style>

```
```
<!-- 确定按钮样式-->
<style name="BtnPositiveStyle" parent="Widget.AppCompat.Button.ButtonBar.AlertDialog">
     <item name="android:textColor">xxx</item>
</style>

<!-- 默认文本框样式 -->
<style name="EditTextStyle">
    .....
</style>

<!--弹窗动画样式-->
<style name="CommonDialogStyle" parent="@android:style/Animation.Dialog">
     <item name="android:windowEnterAnimation">@anim/xxx</item>
     <item name="android:windowExitAnimation">@anim/xxx</item>
</style>

```

#### XML规范

* 【推荐】没有子节点的情况下，以`/>`来结尾
```
<ImageView
     android:layout_width="wrap_content"
     android:layout_height="wrap_content"/>

<TextView
     android:layout_width="wrap_content"
     android:layout_height="wrap_content"/>
     
```

* 【推荐】ImageView宽高定义成`match_parent`，另外一项不能写死，而是应该使用`wrap_content`，否则可能因为比例不对导致变形，另外需要使用`android:adjustViewBounds="true"`,进行根据图片宽高调整自己的宽高
```
<ImageView 
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:adjustViewBounds="true"
    android:src="@drawable/xxxx"/>
```

##### 预览属性约定
* 【推荐】在每个布局中定义`tools:context`这样子方便找到对应的类
```
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".ui.Fragment.MineFragment">

</FrameLayout>
```
在`tools:context=".ui.Fragment.MineFragment"`按住`crtl`并且点击鼠标即可快速找到对应的类

在适配器布局同理一样，有布局文件都可以添加：
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context="com.knight.wanandroid.adapter.UserDetailCoinAdapter"
    android:layout_width="match_parent"
    android:layout_height="80dp">
</ConstraintLayout>    

```
* 【推荐】如果**TextView**显示字符串是一成不变，可以直接定义在布局文件里，如果是动态变化，应该使用`tools：text`预览属性，而不应该使用`android:text`，为什么呢?因为在写布局代码的时候，有些效果是在运行之后才能看到，比如：**TextView**在xml中没有设置任何字符，而是在类(activity或者fragment)中设置的，但是为了看预览效果，就设置了`android:text`属性，很多时候告诉自己，写完代码会把这一行删了，但是很有可能忘了，到最后这些代码会在自己APP里。因此，如果要在运行时胡磊，只在设计布局有效，应该用`tools:text`，这样子运行的时候本身会被忽略，不会带进apk中，同理也可以用在`ImageView`等。

#### 版本迭代命名规范
* 【推荐】版本名至少应该由三段整数组成，中间以`.`分隔,例如微信：8.0.11
```
versionName = "8.0.11"
```
  * 第一段：重大版本，架构升级，UI风格大改版，业务重构等改变特大时候+1
  * 第二段：强制需求版本，每个需求完成发版+1
  * 第三段：非强制需求版本，每个需求完成发版+1
**注意:有时候遇到生产Bug需要发版时，可以通过第三段+1来发强制更新版本**  

后两段最大大小自己按需求限制，如20，30


#### 注释规范
##### 方法注释
* 【推荐】每一个成员方法(自定义成员方法，覆盖方法，属性方法)的前面必须做好注释，默认是在方法前输入`/**+回车`即可出来。
也可以自定义模板注释：
* 首先创建`Template Group...`
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_annoation_one.png)
* 接着创建`Live Template`
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_annoation_two.png)
* 在`Abbreviation` 输入快捷键，在`Template text`定义自己的注释
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_annoation_three.png)
* 因为模板里设置了日期时间，因此点击`Edit variables`需要给`date`和`time`赋值
![](https://gitee.com/MengSuiXinSuoYuan/wanandroid_server/raw/master/AndroidStandardCode_picture/android_studio_annoation_four.png)

设置完模板后，新建一个方法，在方法前输入`ann`+回车即可出现方法模板注释

```
 /**
     * @Description:${todo}
     * @param ${tags}
     * @return ${return_type}
     * @author ${user}
     * @date 2021/9/2 15:08
     */ 
    public WechatArticleAdapter(@Nullable List<WechatArticleEntity> data){
        super(R.layout.base_text_item,data);

    }
```

##### 类全局变量注释规范
* 【强制】类、类属性、类方法的注释必须使用javadoc规范，使用`/**内容*/`格式，不得使用`//xxx`方式和`/*xxx*/`方式。
```
 /**
  * 文章url
  */
String mWebUrl = "";

```

##### 方法内注释规范
* 【强制】方法内注释使用`//xxx注释`或者`/*xxx*/`,并且在代码前进行注释，不能再代码后面注释
```
 //正例
 private void init() {
        //获取屏幕密度
        mDensity = getContext().getResources().getDisplayMetrics().density;
 }
 
 //反例
  private void init() {
        mDensity = getContext().getResources().getDisplayMetrics().density;//获取屏幕密度
 }
```

#### 代码样式规范
* 【强制】代码之间应该有适当的空格，不能多也不能太少
* 【推荐】左大括号不需要单独一行，与前面代码同一行并用空格隔开
```
//反例
if (xxx)
{
}

//正例
if (xxx) {

}
```

* 【强制】每个判断语句都需要加左右括号
```
//反例
if () xxxx

//正例
if () {
    xxxx
}
```

##### 代码换行规范

* 【推荐】单行代码较长可以适当换行
```
// 反例
ScaleAnimation mScaleAnimation = new ScaleAnimation(1.0f, 1.1f, 1.0f, 1.1f, Animation.RELATIVE_TO_SELF, 0.5f, Animation.RELATIVE_TO_SELF, 0.5f);
imageview.startAnimation(mScaleAnimation);

//正例
ScaleAnimation mScaleAnimation = new ScaleAnimation(1.0f, 1.1f, 1.0f, 1.1f,
        Animation.RELATIVE_TO_SELF, 0.5f, Animation.RELATIVE_TO_SELF, 0.5f);
imageView.startAnimation(mScaleAnimation);
```
* 【推荐】当一个方法有很多参数的时候，应该在每个参数`,`换行
```
//反例
setArrowAnimate(mTopArticleAdapter, topArticleFootView.findViewById(R.id.home_iv_toparticlearrow), true,true);

//正例
setArrowAnimate(mTopArticleAdapter,
                        topArticleFootView.findViewById(R.id.home_iv_toparticlearrow),
                        isShowOnlythree,
                        true,
                        true);
```

* 【强制】当一行中调用多个函数时，每个函数单独一行，换行符在`.`之前
```
//反例
Glide.with(context).load(resourceId).transition(withCrossFade()).into(imageView);

//正例
Glide.with(context)
         .load(resourceId)
         .transition(withCrossFade())
         .into(imageView);
```

* 【推荐】方法参数排序可以按照重要程度进行排序


##### 类成员顺序规范
* 【推荐】类成员可以按照如下顺序
    * 常量(Kotlin伴生对象要在开头)
    * 字段(可以按执行顺序，重要程度)
    * 构造函数
    * 重写函数
    * 共有函数
    * 私有函数
    * 内部类和接口
 
`Activity`和`Fragment`如有多个生命周期重写函数，则按调用生命周期顺序来排序

#### 依赖第三方库规范
* 【强制】每一行依赖库之前必须有注释，出自哪里
```
//正例
//全局加载视图框架 https://github.com/KingJA/LoadSir
implementation "com.kingja.loadsir:loadsir:$loadsirVersion"

//反例
implementation "com.kingja.loadsir:loadsir:$loadsirVersion"
```
* 【强制】尽量使用一直维护的库，长时间不维护的(3年以上)需要慎重考虑
* 【强制】每个依赖库不能用`latest-version`,必须指定某个版本，因为有时候第三方库发布了最新版本，出现问题，而你又引用了，但是测试没测试，有可能漏到生产上

* 【推荐】框架有问题时，及时联系库作者进行反馈

#### 异常捕抓规范
* 【强制】不能为了减少`崩溃`而大量使用`try catch`,具体看需求看场景
* 【强制】必须捕获具体异常，不能用`Exception`来捕抓，并且在代码输出对应日志
```
//反例
try {
    xxxx
} catch (Exception e) {}

//正例
try {
    xxxx
} catch (FileNotFoundException e) {
    e.printStackTrace();
    //进行上报服务器处理
} catch (IOException e) {
    e.printStackTrace();
    //进行上报服务器处理
}

```

* 【强制】不是有异常就要用`try catch`，不能通过捕获处理异常，可以通过一些逻辑判断避免进入一些异常
```
//反例
try {
    Layout mNamelayout = getLayout();
    float mSpacingMult = mNamelayout.getSpacingMultiplier()
} catch (NullPointerException e) {
    //当mNameLayout为空进来
}

//正例
Layout mNamelayout = getLayout();
if (mNamelayout == null) {
  return;
}
float mSpacingMult = mNamelayout.getSpacingMultiplier()
```

 #### 参考文章
* [https://google.github.io/styleguide/javaguide.html](https://google.github.io/styleguide/javaguide.html)
* [https://github.com/android/architecture-samples](https://github.com/android/architecture-samples)
* [https://source.android.com/source/code-style](https://source.android.com/source/code-style)

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


     


        
        