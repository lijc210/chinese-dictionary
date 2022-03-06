# 汉语拼音辞典

本词典主要收录了常用字基本信息，多音字，汉字基本解释，常用词汇、常用成语读音。

## 缘起

中华传统文化，源远流长，博大精深！从古至今，上下五千年，在这历史的长河中先辈们创造出了无数的历史奇迹。
在中国两千多年的漫长帝制社会里，汉字一直是我们中华民族文化传承的重要工具。
从甲骨文到秦始皇统一文字，再到近代简化字，汉字一直在经历演变过程。
汉字总数超过8万，但常用字仅2500个，次常用字1000多个，共3500字。
对于不太常见的汉字，我们通常会使用字典、词典的方式来查询。

**汉语拼音词典** 就属于一个便于用户查询汉字拼音与笔画的电子词典工具。

## 字库

字库的准确性和完整性对于 辞典 工具来说至关重要。
在校对过程中，关于数据准确性没有做严格的把控，特别是很多汉字非常罕见，其中大量古文文献资料的引用更是难以考证。
本词典收集了如下字、词库：

```text
|---- chinese-dictionary
|----|---- data     数据
|----|----|---- character
|----|----|----|---- char_base.json             总收录汉字 14814 拼音与笔画
|----|----|----|---- char_base_detail.json      总收录汉字 20744 解释
|----|----|----|---- char_common.json           常用字 3500 仅汉字
|----|----|----|---- char_common_base.json      常用字 3500 拼音与笔画
|----|----|----|---- char_common_detail.json    常用字 3500 解释
|----|----|----|---- polyphone.json             多音字 1589
|----|----|---- idiom
|----|----|----|---- idiom.json                 总收录成语 超过3万 条
|----|----|---- word
|----|----|----|---- word.json                 总收录词语 超过26万 条
|----|---- scripts    脚本
```

### 数据格式

#### 为何数据是 JSON 格式？

JSON 格式可以方便快捷地转为各种编程语言内部可使用的结构。

此外某些工具支持将 JSON 文件导入后直接结构化。

#### char_base.json 基础汉字

```json
[
  {"index": 1, "char": "一", "strokes": 1, "pinyin": ["yī"], "radicals": "一", "frequency": 0}, 
  {"index": 2770, "char": "咧", "strokes": 9, "pinyin": ["liě", "liē", "lié", "lie"], "radicals": "口", "frequency": 2},
  {"index": 7467, "char": "砭", "strokes": 9, "pinyin": ["biān"], "radicals": "石", "frequency": 3}
]
```

- `index` 表示从 1 开始的自然增长序列，默认按照汉字笔画数排序。
- `char` 表示一个汉字。
- `strokes` 汉字的笔画数。
- `pinyin` 汉字的读音列表。
- `radicals` 汉字的读音偏旁部首。
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用，3 为不常用字。
- `structure` 汉字结构，结构表示的含义见下表。
- `traditional` 表示繁体字写法。

> 常用字（3500） = 最常用字 0（500）+ 较常用字 1（2000）+ 次常用字 2（1000） 


##### 汉字结构

|结 构 方 式					|例 字|间 架 比 例	| 代码 |
|		---		| -- | --| -- 					|
|独 体 结 构		|米、不			|　方正			|0
品 字 形 结 构	|晶、众			|各部分相同		|1
上 下 结 构		|			| 					|2
| - |录、华			|　上下相等					|21
| - |它、花				|上小下大				|22
| - |基、想				|上大下小				|23
上 中 下 结 构		|			| 				|3
| - |意、翼		|上中下相等		 				|31
| - | 量、裹				|上中下不等				|32
上 中 下 结 构		|			| 				|4
| - |村、联			|左右相等 					|41
| - |伟、搞				|左窄右宽				|42
| - |刚、郭				|左宽右窄				|43
左 中 右 结 构		|			| 				|5
| - |街、掰				|左中右相等				|51
| - |辩、傲				|左中右不等				|52
全 包 围 结 构		|圆、国		|全包围			|6
半 包 围 结 构		|			| 				|7
| - |匠、区		        |左包右			 		|71
| - |历、尾				|左上包右下				|72
| - |勾、句				|右上包左下				|73
| - |遍、廷				|左下包右上				|74
| - |冈、闲				|上包下					|75
| - |函、凶				|下包上					|76

#### char_common.json 常用字

```json
[
  {"id": 4, "char": "十", "frequency": 0},
  {"id": 278, "char": "乐", "frequency": 1},
  {"id": 3405, "char": "瞪", "frequency": 2}
]
```

- `id` 表示从 1 开始的自然增长序列，默认按照汉字笔画数排序。
- `char` 表示一个汉字。
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用。


#### char_common_base.json 常用字


```json
[
  {"index": 1, "char": "一", "strokes": 1, "pinyin": ["yī"], "radicals": "一", "frequency": 0},
  {"index": 16, "char": "大", "strokes": 3, "pinyin": ["dà", "dài", "tài"], "radicals": "大", "frequency": 0}
]
```

#### char_explanation.json 汉字解释

```json
[
{
	"char": "为",
	"pronunciations": [
		{
			"pinyin": "wéi",
			"explanations": [
				{
					"content": "(爲的本义是母猴。象形。按字,从爪,古文下象两母猴相对形)"
				},
				{
					"content": "假借为“伪”。做,作,干,搞",
					"detail": [
						"我生之初,尚无为。——《诗·王风·兔爰》",
						"子为不知,我将不墜。——《左传·定公十二年》",
						"为善者,非善也,故善无以为也。——《管子·枢言》",
						"变化则为生,为生则乱矣。——《管子·心术上》",
						"为,施也。又,成也。——《广雅》",
						"有客自云能,帝使为之。——《世说新语·巧艺》",
						"为之难。——《论语》。皇疏:“犹行也。”",
						"可以为师。——《论语》",
						"人之为学。——清·彭端淑《为学一首示子侄》",
						"推为长。——清·徐珂《清稗类钞·战事类》",
						"为之者较少。——蔡元培《图画》"
					]
				},
				{
					"content": "或,抑 ——表示选择关系",
					"detail": [
						"助教顾良戏之曰:“汝姓何,是荷叶之荷,为河水之河?”妥应声曰:“先生姓顾,是眷顾之顾,为新故之故?”——《北史·何妥传》",
						"《太誓》之注不解“五至”,…不知为一日五来,为当异日也。”——《诗·周颂·思文》疏",
						"不审先生梁朝出仕,为复隐居?——《太平广记》"
					]
				},
				{
					"content": "又如:为复(还是,抑或);为是(抑或;还是);为当(抑或;还是)"
				},
				{
					"content": "另见wèi"
				}
			]
		},
		{
			"pinyin": "wèi",
			"explanations": [
				{
					"content": "(爲字的本义是母猴。象形。按字,从爪,下象形。古文象两母猴相对形)"
				},
				{
					"content": "为了",
					"detail": [
						"为市鞍马。——《乐府诗集·木兰诗》",
						"则众何为。——宋·王安石《答司马谏议书》",
						"不为怨者故。",
						"生为之饱。——清·周容《芋老人传》"
					]
				},
				{
					"content": "又如:为国捐躯(为国家献出生命);为好成歉(将好事变成坏事);为许(为此)"
				},
				{
					"content": "表示动作行为所向,可译为“向”、“对”、“朝”",
					"detail": [
						"为具言所闻。——晋·陶渊明《桃花源记》",
						"不足为外人道。",
						"为弟子说前代事。——清·周容《芋老人传》"
					]
				},
				{
					"content": "另见wéi"
				}
			]
		}
	]
}
]
```

其中包含 2 个部分：

1. `char` 表示当前汉字
2. `pronunciations` 表示汉字在各个读音下的不同含义
    - `pinyin` 汉字拼音
    - `explanations` 汉字对应读音的解释
        - `content` 汉字具体解释
        - `detail` 对 content 的例证
        - `now` 说明当前汉字在古代使用，同现在的某个汉字
        - `same` 汉字与某个字含义相同，可以混用
        - `simplified` 表示该汉字是某个汉字的繁体字，含义可以参考简体字
        - `refer` 为一个词组，表示汉字含义需要参考某个词组。
        - `typo` 当前汉字为某个汉字的讹字（错误形式）。

基本的数据格式如下：

```json
[
  {
    "char": "一",
    "pronunciations": [
      {
          "pinyin": "yī",
          "explanations": [
              {
                "content": "",
                "detail":[],
                "same": "",
                "now": "", 
                 "refer": "",
                 "simplified": "",
                 "typo": ""
              }
          ]
      }
    ]
  }
]
```
**数据规范**

- 整体为列表（数组）
- 每个列表项为一个汉字，不重复
- 每个汉字一定会出现 3 个属性：汉字char、读音pronunciations
- 当前汉字 char 不可省略，**不能为空**，且长度为 1
- 读音 pronunciations 为列表，如果是多音字会有多个，**不能为空**，其中每一项包含 pinyin 和 explanations 。
- pinyin 在同一个汉字中数据**不会重复**，且个数等于该汉字的读音个数。
- explanations 为列表，可能有多个，**可能为空**。其中每一项包含 contents 和 details ，**均可为空，但不可同时为空，且为空时，该字段不会出现**。
- content 中是字符串，一般表示独立的含义。
- detail 中是字符串列表，一般表示一组有关联的汉字解释，是对 content 的进一步例证。
- same 为单个汉字，表示当前汉字与 same 含义相同。
- now 为单个汉字，表示当前汉字如今的写法。
- refer 为一个词组，表示汉字含义需要参考某个词组。某些汉字单独出现时没有含义，必须和另外的汉字组词。
- simplified 为单个汉字，表示当前汉字是某个汉字的繁体字，含义可以参考简体字。
- typo 当前汉字的讹字。

> 目前结果集文件中数据不满足上述规范，是因为解析过程中，某些数据有缺失或者格式错乱，在持续改进后，最终会完全满足上述要求。

#### polyphone.json 多音字

polyphone.json 文件中的多音字包含常用字里多音字的 600 余个和其它非常用字的 900 余个，共 1589 条数据。

```json
[
  {"index": 1, "char": "了", "pinyin": ["liǎo", "le"], "frequency": 0, "strokes": 2},
  {"index": 506, "char": "咖", "pinyin": ["kā", "gā"], "frequency": 2, "strokes": 8}
]
```

其中：

- `index` 表示数据索引值，从 1 开始
- `char` 表示该汉字
- `pinyin` 为汉字读音的数组
- `frequency` 表示使用频率，0 为最常用，1 为较常用，2 为次常用，3 为不常用
- `strokes` 表示汉字笔画数

#### idiom.json 成语

```json
[
    {
      "word": "一帆风顺", 
      "pinyin": "yī fán fēng shùn", 
      "abbr": "yffs",
      "quote": {"text": "栉霜沐露多劳顿，喜借得～。", "book": "清·李渔《怜香伴·蹴居》"}, 
      "source": {"text": "定知一日帆，使得千里风。", "book": "唐·孟郊《送崔爽之湖南》"},
      "explanation": "船上的帆挂起来顺着风行驶。比喻事情非常顺利，没有任何阻碍。", 
      "similar": ["万事亨通", "无往不利"], 
      "opposite": ["寸步难行", "一波三折"], 
      "example": "①朋友，在分别之际，我祝你一帆风顺，事业有成。②小明一家要到海南旅游，祝他们一帆风顺，旅途平安。", 
      "usage": "常用来祝愿他人旅途顺利。作祝词时，前面常有“祝你”“祝你们”“祝大家”等词语。多用于褒义。", 
      "notice": "“一帆风顺”和“无往不利”都含有非常顺利的意思。区别在于：①“一帆风顺”指做事毫无挫折，着眼于顺利的程度；“无往不利”指事事顺利，着眼于顺利的范围。②“一帆风顺”用作祝词；“无往不利”无此用法。"
    }
]
```

- 整体为列表（数组），每个列表项为一个汉字，不重复

其中：

- `word` 表示该成语，**唯一且不为空**，长度大于等于 3
- `pinyin` 为成语读音，**不为空**
- `abbr` 拼音的简写，**不为空**
- `quote` 表示哪些出名的著作中使用到了该成语。不必须
- `source` 表示该成语出处。不必须
- `explanation` 表示该成语解释。不必须
- `similar` 表示该成语近义词。不必须
- `opposite` 表示该成语反义词。不必须
- `example` 表示该成语的例句。不必须
- `usage` 表示该成语的用法。不必须
- `structure` 词语结构，结构表示的含义见下表。不必须，仅特殊结构包含该字段
- `notice` 表示该成语使用时应该注意的地方。不必须

##### 词语结构

|结 构 方 式					|例 字|	 代码 |
|		---		| -- | --|
|ABB		|懒洋洋					|122
|ABAB		|乐呵乐呵				|1212
|AABB		|堂堂正正				|1122
|ABAC		|一心一意				|1213
|AABC		|振振有词				|1123
|ABCC		|千里迢迢				|1233


#### word.json 词语

```json
[
    {
      "word": "动脉", 
      "pinyin": "dòng mài", 
      "abbr": "dm", 
      "explanation": "把心脏中压出来的血液输送到全身各部分的血管； 比喻重要的交通干线。"
    }
]
```

- `word` 表示该词语，**唯一且不为空**，长度大于等于 2
- `pinyin` 为词语读音，**不为空**
- `abbr` 拼音的简写，**不为空**
- `explanation` 表示该词语解释，超过 99% 的词语含有释义

词语和成语的所有属性完全相同，且词语库包含成语库。

所有的成语数据 idiom.json 都包含在 word.json 文件中。

## 线上应用

目前 **汉语拼音辞典** 已经在多端上线小程序。

微信小程序：汉语拼音辞典

<img alt="微信小程序" src="https://cdn.mapull.com/char/qrcode/wechat_character.jpg"></img>

百度小程序：码谱汉语拼音辞典

<img alt="百度小程序" src="https://cdn.mapull.com/char/qrcode/baidu_character.png"></img>

抖音、字节跳动小程序：汉语拼音辞典

<img alt="字节跳动小程序" src="https://cdn.mapull.com/char/qrcode/toutiao_character.png"></img>

## 参考资料

字库的基础数据大都来自 Github 及其他开源组织，本项目字库参考但不限于如下资源：

- [Github] [funNLP](https://github.com/fighting41love/funNLP)
- [Github] [pinyin-data](https://github.com/mozillazg/pinyin-data)
- [Github] [chinese-xinhua](https://github.com/pwxcoo/chinese-xinhua)
- [Github] [phrase-pinyin-data](https://github.com/mozillazg/phrase-pinyin-data)
- [开源] [CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict)
- [官方] [中国语言文字网](http://www.china-language.edu.cn/)
- [商用] [汉典](https://www.zdic.net/)
- [商用] [字海，叶典网](http://zisea.com/)

> 参考商用数据是为了人工校对数据的准确性，并没有对其数据进行爬取。

## 版权

该项目是为了支持 **汉语拼音辞典** 的线上数据。在使用小程序的过程中，发现有些汉字读音有误，如果人工校对将是一个庞大的工程，于是对现有的开源语料库进行了多维分析。如果不确定的读音，还参考了部分商业应用如汉典网的数据进行人工比对。

本项目汇总得到的数据结果采用 MIT License 开源。

因为某些收集来的数据，无法确认数据的最初来源，使用它们可能存在风险。