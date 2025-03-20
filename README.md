# 🌟 **电视壳子**（ShellTV）! 🚀

![Profile Views](https://komarev.com/ghpvc/?username=your-username&color=blue) ![Stars](https://img.shields.io/github/stars/your-username?style=social) ![Followers](https://img.shields.io/github/followers/your-username?style=social)

---

## 📌 关于此项目
- 本项目修改自开源项目 https://github.com/CatVodTVOfficial/TVBoxOSC 在此致敬！🌹🌹🌹 
- 本项目在功能上没有太多改进，主要对操作体验依个人喜好进行了优化 
- 增加基于影片的关联推荐，以及基于影人的关联推荐
- 对数据源文件的语法定义进行了扩展，以更好处理影片元数据缺失问题（如海报等）
- 直播节目收藏等其它一些功能
- 联系方式:  QQ 3877275490 [给我邮件](mailto:3877275490@qq.com)

--- 

## 🛠️ 对源配置文件语法的补充定义
为改进用户体验，**电视壳子**对TvBox项目的源配置文件的语法定义进行了扩展，如果你是进阶玩家（致力于定制属于自己的配置文件），可以使用这些扩展定义，并配合**电视壳子**使用，以获取更好的使用体验（如，避免收藏与历史记录中出现大量无意义的海报）。这些补充定义多用于网盘搜索类、原数据无人维护的源。

以下是这些扩展语法的语义描述：

| 属性       | 描述                     | 缺省值   |
|------------|--------------------------|--------|
| hasPoster| 该源提供海报，1：提供，0：不提供  | 1 |
| hasMeaningfulTitle| 该源提供准确标题，1：提供，0：不提供| 1 |
| hasTags       | 该源提供影片的原数据，1：提供，0：不提供      | 1|

样例如下：
[源配置样例.json](./源配置样例.json)

--- 

## 🛠️ 界面截图

### 主页

<img src="images/home.png" alt="Example Image" width="600" >

### 搜索页

<img src="images/fastSearch.png" alt="Example Image" width="600" >

### 详情页

<img src="images/detail.png" alt="Example Image" width="600" >

### 影人关联

<img src="images/personage.png" alt="Example Image" width="600" >

--- 

## 📥 玩法

### 入门玩家
1. 下载源配置文件
2. 将源配置文件放置在电视壳子的源配置文件夹下
3. 在电视壳子->系统 -> 配置源地址，输入 -> 确定、退出

### 进阶玩家
1. 百度或Github 一个你基本满意的配置文件，作为模板（注，如果你想做全套，还要将源配置文件中索引的其它文件一并下载，如.jar文件等）
2. 根据基础语法和上述补充语法定义，对模板进行修改，包括，删除不喜欢的源、排序等
3. 将修改后的配置文件和相关的其它文件上传到机顶盒（方法）
4. 在电视壳子->系统 -> 配置源地址，输入 -> 确定、退出

---

## 📥 捐赠
由于**电视壳子**部分特色功能依赖于服务器资源，为覆盖基本开销，我们接受捐赠。您的捐赠将用于支付服务器费用、域名费用等。
方式：在应用首页，点击捐赠按钮

### 捐赠界面

<img src="images/donation.png" alt="Example Image" width="600" >



