# 毕业纪念馆册app
|文档名称|毕业纪念馆册app|
|--|--|
|负责人|陈熙|
## 一、BRD：
- 各个年龄段的用户都有相册留念的需求，用户群体广。

## 二、MRD：
- 当今毕业生对于留念相册新功能新形式需求大。
## 三、PRD
### 价值主张设计
#### 一句话版本
- 本产品集合记录、浏览、识别地点的功能，满足用户的回忆、记录需求。
#### 一分钟版本
- 本产品是一款线上的纪念册APP，用户可以在APP上记录、查看自己的相片，还可以同学们可以浏览亲友们上传的照片，并且可以识别照片中的地点，将记忆带回当时的场景。
#### 背景：目前市场上大部分纪念相册是上传照片生成相册H5页面，难以永久保存，难以满足用户需求。
#### 目标用户：有相册留念需求的各年龄段群体，特别是毕业生
###  功能：
*   识别人物，可知人是谁、联系方式
*   打造社区功能，通过在社区发布照片，让亲友了解近况，维持社交联系
*   识别照片地点
#### 产品目标
- 前期主打相片存储、识别人物、地点功能，通过新功能吸引用户
- 中期打造社区，增加社群用户，增加识别场景导航功能
- 后期不断升级功能，巩固用户群
#### 加值宣言
1.人脸识别
- 提供人脸检测与属性分析、人脸，1：1对比、人脸搜索、活体检测等能力。灵活应用于金融、泛安防、零售等行业场景，满足身份核验、人脸考勤、闸机通行等业务需求。

2.场景识别
- 支持超过10万类常见物体和场景识别，接口返回图片内1个或多个物体的名称，并可获取百科信息。适用于图像或视频内容分析、拍照识图等业务场景
#### 核心价值
- 通过本产品，记录下自己的生活点滴，分享自己的近况和了解亲友近况，维系友谊。
#### 用户痛点
- 用户找不到以前的毕业相册
- 用户浏览以前的照片，却忘记同学的名字
- 用户想要故地重游，却不知道故地的情况
#### 用户需求
- 场景一：用户a找不到以前的毕业相册，这时他可以打开毕业相册app，重温回忆
- 场景二：用户b马上要参加同学聚会，他打开以前的毕业相片，通过人脸识别技术，记起名字
- 场景三：用户c想要重游故地，但是他忘记相片中地点在哪，所以使用场景识别功能
#### API的选择与调用
（一）人脸识别
1.腾讯云人脸识别
- 腾讯人脸识别基于腾讯优图和腾讯AI Lab的深度学习算法和海量数据集，对图片和视频源中面部特征进行提取分析。可实现精准的人脸检测和人脸识别，涵盖人脸检测与分析、五官定位、人脸对比与搜索、跨年龄人脸识别等，为安防监控、人脸美化、智能相册分类等应用场景提供有力的技术支持。
- [技术文档](https://ai.qq.com/doc/detectface.shtml)
- [定价](https://cloud.tencent.com/product/tts/pricing) 

2.Face++人脸识别
- 检测并定位图片中的人脸，返回高精度的人脸框坐标。Face++还支持存储检测到的人脸元数据，以便日后使用。
- [调用文档](https://console.faceplusplus.com.cn/documents/4888373)

- [定价](https://www.faceplusplus.com.cn/v2/pricing/)

3.Azure人脸AI
- 功能：检测并比较人脸，基于相似度将图像组织成组，识别图像中先前标记的人物，在本地或在云中运行
- [操作代码示例](https://docs.microsoft.com/zh-cn/azure/cognitive-services/face/face-api-how-to-topics/howtodetectfacesinimage)
- [定价信息](https://azure.microsoft.com/zh-cn/pricing/details/cognitive-services/face-api/)

（二）场景识别
1.Face++ 场景与物体识别
- 功能与优势：检测图片中的场景与物体，返回检测出的场景与物体名称，以及相应的置信度。场景/物体识别丰富、提供识别置信度、定制化业务模式
- [调用API文档](https://console.faceplusplus.com.cn/documents/5671708)
- [定价](https://www.faceplusplus.com.cn/v2/pricing/)
2. 腾讯云场景识别
- 优势：知识图谱广泛，基于社交生活场景海量图像数据挖掘，能涵盖日常生活照片的各个信息维度，有效解码图片内容信息。
准确率高，业内领先的图像处理算法，可准确识别图片中的场景及物体，并标注其置信度供用户参考，准确率更高。
响应快，核心算法与基础模型经过多轮优化，平均处理时长仅需数百毫秒。
高扩展性，基于语义树扩展的标签体系，能够灵活支持更多自定义标签，具备迁移学习的能力，识别维度和粒度将不断扩展
- [技术文档](https://ai.qq.com/doc/vision_scene.shtml)
- [定价](https://cloud.tencent.com/product/tts/pricing) 
3.百度AI场景识别
- 支持超过10万类常见物体和场景识别，接口返回图片内1个或多个物体的名称，并可获取百科信息。适用于图像或视频内容分析、拍照识图等业务场景。
- [技术文档](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/Xk3bcxe21)
- [定价](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/rk3bcxa9e)

#### 人工智能概率性
- 受图片的清晰度、光线、角度等影响，可能导致人脸、场景识别出错。
- 受识别的人物的妆发、面部表情等影响，可能导致识别人物出错。
#### 其他问题
- 用户隐私保护

