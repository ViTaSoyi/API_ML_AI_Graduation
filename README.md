# API_ML_AI_Graduation

|   发布时期  |   2019-12-28  |
| --- | --- |
| 史诗名称    |  智能毕业纪念APP   |
|  文件现状   |  未完成  |
|  文件的主人   |  谭怡颖   |
|  领头设计者   |   谭怡颖  |
|  领头开发者   |  谭怡颖   |
|  领头测试者   |  谭怡颖   |  

### （一）背景  
无论是以前还是现在，毕业纪念册都是纪念毕业最流行的一种形式，但传统的毕业纪念册使用形式以及功能十分单一。并且在手机不离身的时代，人们变得更少地关注纸质版的东西，更多的注意力在屏幕上。同时，目前市场上也未有毕业纪念相关的软件。  

### （二）价值主张  
智能毕业纪念APP让用户能够回忆纪念曾经美好的青葱校园时光。在产品中用户可以通过留言功能给同学留言以及收到他人对自己的留言。除了最基本的毕业册留言功能外，本产品还会提供人脸识别功能，识别照片上的人脸，帮助用户快速获得该人脸的人物基本信息以及他公开分享的信息；同时还会选取50张包含用户在内的照片自动生成精美的相片集，激起用户曾经与ta的回忆，重新建立或者加强和ta之间的联系。产品还提供回忆功能。用户可能会忘记那天、那地他做曾经了什么，而APP会记住用户曾经的定位和内容发布时间，当用户毕业后某天再次回到某地，经过/到达曾经定位过的地点时或者到达某个时间时会推送给用户曾经在此地/此时“你做了什么”的内容，帮助用户重新回想起以前的美好回忆；并且用户还能对未来的自己留言，到达设定时间，APP会将内容通知给未来的自己。

### （三）加值宣言  
智能毕业纪念APP将使用face++人脸识别API，通过检测并定位照片上的人脸，然后从人脸库中查找相似度较高的几张人脸，选出相似度最高的一张人脸，返回该人脸元数据。同时还会使用高德定位API，不管软件是处于前台还是后台都能够快速的帮用户定位手机当前的所在位置。

### （四）核心价值  
基于毕业后大多数人各奔东西，联系减少/困难的现象，APP会帮助用户拾起回忆以及加强与同学的联系。

### （五）核心价值与用户痛点
- 痛点一：怎么可以不尴尬地获得某位同学的基本信息。
- 痛点二：想搜集自己和同学一起的合照做成相册，但是搜集好麻烦，整理也好麻烦呀~
- 痛点三：想念自己曾经在学校里做过有趣/开心/伤心等的事情，但是有些记不清/记不起了 。 

### （六）需求列表    
| 标题 | 用户案例 | 重要程度 | 笔记 |
| ---- | -------- | -------- | ---- |
|  人脸识别    |    路上突然遇见老同学，但是忘记他是谁了      |    重要      |  通过拍照上传照片或已有的照片，对人脸进行识别，反馈用户人脸主人公开的信息    |
|   定位API    |    好怀念我曾经在这里做过的一些事情啊~      |    重要      |      |
|   定时内容反馈   |    当年我在学校这个时候做了什么？      |    重要      |  目前无API技术提供 NOT DOING   |

### （七）人工智能概率性
- **face++人脸识别API**  
人脸识别在识别单人以及几人和清晰的场景下时，能够精准地识别出该人脸并返回相关信息。但在识别多人以及双胞胎和模糊不清晰的场景下，可能无法准确识别出每个人。产品针对的是个人用户体，在使用上的准确度需求没有公安监测那么严格，并且根据市场调查，用户使用人脸识别一次通常只会想要获得个人，单人以及几人的信息。因此该功能的使用对用户体验的负面影响不至于压过正面影响。
- **高德定位API**  


### （七）API调用和可行性分析  
#### face++人脸识别调用
1. [旷视人脸识别api调用代码档](https://gitee.com/VirginiaT/yearbook/blob/master/face%20%20%E4%BA%BA%E8%84%B8%E6%90%9C%E7%B4%A2.ipynb)  
- 创建人脸库  
![](https://images.gitee.com/uploads/images/2019/1201/183153_e95ab76e_1648197.png "创建人脸库.png")  
- 添加人脸  
![](https://images.gitee.com/uploads/images/2019/1201/183309_c20e7697_1648197.png "添加人脸.png")  
- 添加人脸信息  
![](https://images.gitee.com/uploads/images/2019/1201/183647_a4d41104_1648197.png "人脸信息.png")  
- 人脸搜索  
![](https://images.gitee.com/uploads/images/2019/1201/183710_1fa7a307_1648197.png "人脸搜索.png")  
- 人脸关联信息  
![](https://images.gitee.com/uploads/images/2019/1201/183750_86609835_1648197.png "人脸关联信息.png")  

2. **face++与百度与云从的对比**  
> 根据[2019《互联网周刊》&eNet研究院选择](http://www.enet.com.cn/article/2019/1031/A201910311029320.html)排行，选择了目前人脸识别技术排名靠前并且提供接口服务的3个平台。  

|        | 旷视 | 百度 | 云从 |
| ------ | ---- | ---- | ---- |
| 成熟度 |  具有自主原创的深度学习框架Brain++，以及全球领先的识别准确率，处理速度上缩短在1秒内，支持高并发承载与高可用性保证   |  人脸识别可靠性保障高达99.99%，灵活应用于金融、泛安防、零售等行业场景，满足身份核验、人脸考勤、闸机通行等业务需求    |  拥有先进的三级研发架构、国内首发“3D结构光人脸识别技术”以及首次商用跨镜追踪技术，具有99.99%的可靠性保障    |
| 性价比 |  可免费调用，100元/QPS/天；1000元/QPS/月    |   可免费调用，价目表看下图   |   部分功能可免费调用，部分功能需授权才可调用，价格不一，QPS限制为10  |  

百度人脸识别价目表  
![](https://github.com/ViTaSoyi/API_ML_AI_Graduation/blob/master/%E7%99%BE%E5%BA%A6%E4%BA%BA%E8%84%B8%E4%BB%B7%E7%9B%AE%E8%A1%A8.png)

3. **API使用风险报告**
- API市场竞争程度：人脸识别API市场竞争比较激烈。与指纹识别、虹膜识别、视网膜识别等生物识别技术相比，人脸识别不需要专门的设备，一个普通摄像头加显示器就可以构成人脸识别系统，接受程度很高。根据新思界发布的《2019-2023年中国人脸识别行业深度研究及市场投资风险咨询报告》，2018年，中国人脸识别行业市场规模为131亿元，年均复合增长率为37%，充分显示出了人脸识别巨大的商用价值。[参考资料](http://www.elecfans.com/consume/937221.html)
- 输入输出限制：进行图片人脸识别时，图片格式有需求，通常为JGP格式，图片像素尺寸、文件大小和最小人脸像素尺寸都有需求。输出内容基本为人脸的属性特征，如需要获得人脸主人的其余信息，则需要自定义人脸属性，工程量大。
- 定价：通常用量越多，价格越优惠。人脸识别的价格相对于其他API更贵，主要是人脸识别的实现需要多个API的协助。






