# 回忆卡--智能相册管家
发布日期|2019/12/20
  ----  | ----    
Epic|回忆卡--智能相册管家
文件现状	|完成
文件主人|杨亦昊
领头设计者|杨亦昊
领头开发者|杨亦昊
领头测试者|杨亦昊
## 价值主张设计
### 一句话：
回忆卡--智能相册管家通过获取用户手机的图片基于图像识别API，为图片进行智能分类，自动生成分类相册，为用户省去图片分类的麻烦，同时在智能分类相册的基础上，相册管家还将结合文字识别API，通过识别图片文字，帮助用户整理图片文字形成文字笔记。
### 一分钟：
随着手机存储空间的增加，手机能储存的图片越来越多。用户对手机相册的功能要求也越来越的高。而目前手机自带的相册功能比较单一，繁琐的操作使得用户需要花费一定的时间去进行图片分类。目前APP应用市场上的手机相册产品种类、功能也较少，大部分产品也与手机自带相册功能雷同。我们团队将基于图像识别、文字识别技术，着眼于用户对手机照片分类以及图片文字笔记的整理的基本需求，打造一款集智能分类、笔记整理、社交共享功能于一体的智能相册管家APP。即通过获取用户手机的图片，基于图像识别API，为图片进行智能分类。自动生成分类相册，为用户省去图片分类的麻烦。在智能分类相册的基础上，结合文字识别API，通过识别图片文字，帮助用户整理图片文字形成文字笔记。满足用户对手机相册图片分类、记录、分享的需求。
## 20X20价值主张设计
## [PPT下载地址](https://raw.githubusercontent.com/GITHUBLITTLECAT/API_check/master/20x20.pptx)
# 第一部分：产品需求概述
******
## （一）背景概述
* 随着手机存储空间的增加，手机能储存的图片越来越多。用户对手机相册的功能要求也越来越的高。而目前手机自带的相册功能比较单一，繁琐的操作使得用户需要花费一定的时间去进行图片分类。
* 目前APP应用市场上的手机相册产品种类、功能也较少，大部分产品与手机自带相册功能雷同。无法满足用户对手机相册图片分类、记录、分享的需求。
## （二）产品定位
本产品旨在为广大智能手机用户提供相册分类、笔记整理、共享相册等服务，满足用户对手机相册图片分类、记录、分享的需求。
* 目标用户群体：广大智能手机用户
## （三）产品介绍--价值宣言
回忆卡--智能相册管家通过获取用户手机的图片，基于图像识别API，为图片进行智能分类。自动生成分类相册，为用户省去图片分类的麻烦。在智能分类相册的基础上，相册管家还将结合文字识别API，通过识别图片文字，帮助用户整理图片文字形成文字笔记。

## （四）用户痛点

用户|用户痛点|用户需求|重要程度
  ----  | ----  |  ----  |  ----
普通智能手机用户|手机图片过多，寻找过程比较麻烦|通过分类找到自己想要的图片|重要
上班族、学生党|想要整理图片文字笔记，但图片看起来不方便|记录图片上的文字信息|重要
普通智能手机用户|手机图片过多，浪费手机空间|清理手机多余的图片|次重要
青年群体|毕业纪念等重要时刻，想要共有册作为留念|想要建立共同相册|一般

## （五）核心价值(最小可行性产品)--功能优先级
* 最小可行性产品：着眼于用户最基本的需求，解决手机图片分类繁琐的问题，提供智能相册分类服务。
 
用户|功能|使用场景|重要程度
  ----  | ----  |  ----  |  ----
普通智能手机用户|相册智能分类|用户需要手动分类照片时|重要
上班族、学生党|图片文字转文字笔记|用户需要记录图片文字时|重要
普通智能手机用户|清理相似、模糊的图片|用户需要删除图片时|次重要
青年群体|建立共享相册|毕业纪念 情侣纪念等重要时刻|一般

## （六）人工智能概率性考量
此产品将作为辅助用户手机图片分类的助手型APP帮助用户更高效率完成图片分类、图片文字记录等工作，不需要用户分散过多的精力，正面影响高于负面影响。
# 第二部分：产品规划及API测试
***********
## （一）产品目标
### 前期目标：
1.导入图片，能识别图片的类型，实现相册分类功能
2.导入文字图片，能识别图片中的文字，实现图片文字转化为文本的功能
### 后期目标（先不做）：
1.识别清理相似、模糊的图片
2.完成共享相册功能，可提供多人编辑的相册
## （二）API使用水平
### （一）图像分类
* 预输入：普通图片
* 预输出：图像的标签分类

#### API测试案例一：

所调用的API：[百度图像识别--通用物体和场景识别](https://ai.baidu.com/tech/imagerecognition/general)

代码示例文档：[技术文档](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/Xk3bcxe21)

输入：
![输入的图片](https://upload-images.jianshu.io/upload_images/9455351-9263d630baa1cde8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输出：
```
{
	"log_id": "7203147587967703094",
	"result_num": 5,
	"result": [
		{
			"score": 0.203018,
			"root": "植物-树",
			"baike_info": {
				"baike_url": "http://baike.baidu.com/item/%E6%A0%91/2699484",
				"image_url": "http://imgsrc.baidu.com/baike/pic/item/6159252dd42a2834218a2c2154b5c9ea15cebfef.jpg",
				"description": "树状图是一种数据结构，它是由n(n>=1)个有限结点组成一个具有层次关系的集合。把它叫做“树”是因为它看起来像一棵倒挂的树，也就是说它是根朝上，而叶朝下的。它具有以下的特点：每个结点有零个或多个子结点；没有父结点的结点称为根结点；每一个非根结点有且只有一个父结点；除了根结点外，每个子结点可以分为多个不相交的子树；"
			},
			"keyword": "树"
		},
		{
			"score": 0.15084,
			"root": "自然风景-其他",
			"keyword": "风景"
		},
		{
			"score": 0.100728,
			"root": "自然风景-天空",
			"keyword": "天空"
		},
		{
			"score": 0.052704,
			"root": "商品-工艺品",
			"keyword": "工艺品"
		},
		{
			"score": 0.003729,
			"root": "商品-工艺品",
			"keyword": "佛像"
		}
	]
}
```
#### API测试案例二：

所调用API：[腾讯云--图像分析](https://cloud.tencent.com/act/event/tiiademo)

代码示例文档：[技术文档](https://cloud.tencent.com/document/api/865/35471#4.-.E7.A4.BA.E4.BE.8B)

输入：
![输入的图片](https://upload-images.jianshu.io/upload_images/9455351-2f702bbca7858533.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
```
DetectLabel:
{
    "CameraLabels": [
        {
            "Name": "建筑",
            "FirstCategory": "场景",
            "SecondCategory": "建筑",
            "Confidence": 67
        },
        {
            "Name": "寺庙",
            "FirstCategory": "场景",
            "SecondCategory": "建筑",
            "Confidence": 6
        },
        {
            "Name": "园林",
            "FirstCategory": "场景",
            "SecondCategory": "生活/娱乐场所",
            "Confidence": 2
        },
        {
            "Name": "宫殿",
            "FirstCategory": "场景",
            "SecondCategory": "建筑",
            "Confidence": 2
        },
        {
            "Name": "丛林",
            "FirstCategory": "场景",
            "SecondCategory": "自然风光",
            "Confidence": 2
        }
    ],
    "Labels": null,
    "AlbumLabels": null,
    "RequestId": "6e795cd9-b4cc-40e2-8a5c-6bbf6475ffba"
}
```
#### 测试结果及分析：
百度API：
* 多次测试，记录响应时间大概3-5s
* 输出返回图片分类标签树0.203、风景0.150、天空0.101、佛像0.003
* 输出结果基本正确，可以根据图像内容做基本的分类

腾讯API：
* 多次测试，记录响应时间大概2-3s
* 输出返回图片分类标签建筑0.67、寺庙0.06、宫殿0.02、丛林自然风光0.02
* 输出结果更精确，可以根据图像内容做更精确的分类


### （二）文字识别


* 预输入：带有文字的图片
* 预输出：图片里的文字的文本

#### API测试案例一：

所调用的API:[百度文字识别--通用文字识别](https://ai.baidu.com/tech/ocr/general)

代码示例文档：[示例文档](https://ai.baidu.com/docs#/OCR-API-GeneralBasic/db0895e7)

输入：
![输入的图片](https://upload-images.jianshu.io/upload_images/9455351-2a3da1fc6ab6a22e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

输出：
```
{
	"log_id": "1261572636821778326",
	"words_result_num": 2,
	"words_result": [
		{
			"words": "思考,快与慢"
		},
		{
			"words": "[美]丹尼尔·卡尼曼◎著胡晓姣李爱民何梦莹译"
		}
	]
}
```
#### API测试案例二：

所调用的API：[腾讯云--文字识别](https://cloud.tencent.com/act/event/ocrdemo)

代码示例文档：[技术文档](https://cloud.tencent.com/document/product/866/34937)

输入：
![输入的图片](https://upload-images.jianshu.io/upload_images/9455351-8a9c0ebbf9192046.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
输出
```
{
  "TextDetections": [
    {
      "DetectedText": "思考，",
      "Confidence": 99,
      "Polygon": [
        {
          "X": 288,
          "Y": 289
        },
        {
          "X": 519,
          "Y": 241
        },
        {
          "X": 535,
          "Y": 322
        },
        {
          "X": 305,
          "Y": 369
        }
      ],
      "AdvancedInfo": "{\"Parag\":{\"ParagNo\":1}}"
    },
    {
      "DetectedText": "，快与慢",
      "Confidence": 88,
      "Polygon": [
        {
          "X": 521,
          "Y": 239
        },
        {
          "X": 842,
          "Y": 172
        },
        {
          "X": 860,
          "Y": 260
        },
        {
          "X": 539,
          "Y": 326
        }
      ],
      "AdvancedInfo": "{\"Parag\":{\"ParagNo\":1}}"
    },
    {
      "DetectedText": "[美]丹尼尔.卡尼曼口著胡晓姣李爱民何梦莹口译",
      "Confidence": 95,
      "Polygon": [
        {
          "X": 317,
          "Y": 384
        },
        {
          "X": 875,
          "Y": 269
        },
        {
          "X": 881,
          "Y": 293
        },
        {
          "X": 322,
          "Y": 409
        }
      ],
      "AdvancedInfo": "{\"Parag\":{\"ParagNo\":1}}"
    },
    {
      "DetectedText": "动",
      "Confidence": 58,
      "Polygon": [
        {
          "X": 235,
          "Y": 757
        },
        {
          "X": 257,
          "Y": 752
        },
        {
          "X": 261,
          "Y": 775
        },
        {
          "X": 240,
          "Y": 779
        }
      ],
      "AdvancedInfo": "{\"Parag\":{\"ParagNo\":2}}"
    }
  ],
  "Language": "zh",
  "RequestId": "fd6bd3ff-7a37-45a0-9b6b-068f0c2ab8a2"
}
```
#### 测试结果及分析：
百度API：
* 多次测试，记录响应时间大概2-3s
* 输出图片文字对应的文本 "思考,快与慢""[美]丹尼尔·卡尼曼◎著胡晓姣李爱民何梦莹译"
* 输出文本基本正确，可以根据图片文字转化为较准确的文本

腾讯API：
* 多次测试，记录响应时间大概2-3s
* 输出图片文字对应的文本“思考,快与慢"[美]丹尼尔·卡尼曼◎著胡晓姣李爱民何梦莹口译，动"
* 输出的文本基本正确，可以根据图片文字转化为基本准确的文本

## （三）API使用比较分析--AI产品概率性
### 1.API定价：
* 百度图像识别--通用物体和场景识别：[定价文档](https://ai.baidu.com/ai-doc/IMAGERECOGNITION/gk3bcx9n1)

![图像识别定价](https://upload-images.jianshu.io/upload_images/9455351-0acf500ea38fdca4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 百度文字识别--通用文字识别：[定价文档](https://ai.baidu.com/ai-doc/OCR/9k3h7xuv6)

![文字识别定价](https://upload-images.jianshu.io/upload_images/9455351-8023e146ce85a7d4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 腾讯云图像分析--图片标签：[定价文档](https://buy.cloud.tencent.com/price/imagetag)

![image.png](https://upload-images.jianshu.io/upload_images/9455351-354d25f5e0611457.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 腾讯云文字识别--通用文字识别：[定价文档](https://buy.cloud.tencent.com/price/ocr#E4BAA7E59381E4BBB7E6A0BC)

![文字识别](https://upload-images.jianshu.io/upload_images/9455351-1ed363cddbe7f6e3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.AI产品概率性评估
图像识别标签分类
* 百度API虽然成功识别风景、树木，但是也有15%将风景图中的塔楼误识别为了工艺品，在识别的速度上也要慢于腾讯云API，总体识别精确度也要低于腾讯云API
* 腾讯云API成功识别出画面主体的塔楼是建筑物。同时识别出了这是寺庙、自然风光，在识别的速度上要快于百度API，总体识别精度也要高于百度API

通用文字识别
* 百度API基本能识别出图片中的文字信息并且转化为较准确的文本，识别速度两者差异不大
* 腾讯API基本能识别出图片中的文字信息并且转化为较准确文本，但是有些文字符号识别不出来，识别速度两者差异不大。

## （四）API使用后风险评估报告
AI产品准确性评估：
* 目前人类对ImageNet图像的识别错误率大约在5%，微软的人工智能系统的错误率为4.94%，谷歌为4.8%。百度如今已将这一错误率进一步降至4.58%。百度API可识别出10万+物体及场景标签
* 腾讯云API基于多项行业领先的人工智能技术，支持数千个标签，可以实现一级标签平均精确率95%以上，二级标签平均精确率90%以上。 
* 百度API针对图片模糊、倾斜、翻转等情况进行了优化，鲁棒性强，识别速度快，且支持2W+大字库，总体识别准确率高达99%，同时支持多种语言识别
* 腾讯云API支持图片中文字的自动定位和识别，印刷体整体识别准确率达95%以上，手写体达90%以上，保证99.5%以上产品可用性，同时支持多种语言识别。

处理方法
* 根据用户部分的手动分类操作记录数据，提升图片识别分类、文字识别的准确性

# 第三部分：产品架构与原型设计--[完整原型文档](http://baiyingv.gitee.io/api-huiyi)
**********
## （一）产品信息结构图
![产品信息结构](https://upload-images.jianshu.io/upload_images/9455351-d149e71c23ade50a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## （二）产品功能结构图
![产品功能结构](https://upload-images.jianshu.io/upload_images/9455351-12ffcb891cbe7f2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## （三 ）产品核心功能流程图
![产品核心功能流程](https://upload-images.jianshu.io/upload_images/9455351-55a3398e352e78b9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## （四）产品原型设计--[完整原型文档](http://baiyingv.gitee.io/api_final)
![相册](https://upload-images.jianshu.io/upload_images/9455351-e6f227852ac164a6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![智能相册](https://upload-images.jianshu.io/upload_images/9455351-c92dee2917ef6fba.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![其他相册](https://upload-images.jianshu.io/upload_images/9455351-8423276075711b47.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![功能](https://upload-images.jianshu.io/upload_images/9455351-ff2c7706722ae765.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![笔记本](https://upload-images.jianshu.io/upload_images/9455351-37b51b4bc88a1cb3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![我的笔记](https://upload-images.jianshu.io/upload_images/9455351-99346bba60dd537c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![清理相似/模糊的图片A](https://upload-images.jianshu.io/upload_images/9455351-401e3d871e114906.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![清理相似/模糊的图片B](https://upload-images.jianshu.io/upload_images/9455351-8ecd1bfa17cacd4a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![回收站](https://upload-images.jianshu.io/upload_images/9455351-1f3c6eddc739df2c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![共享相册](https://upload-images.jianshu.io/upload_images/9455351-c15f325aafed0e26.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![我的](https://upload-images.jianshu.io/upload_images/9455351-8a299615054b70bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

