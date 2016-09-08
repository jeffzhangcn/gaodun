Home\Controller\PaperDataController
===============

用户试卷




* Class name: PaperDataController
* Namespace: Home\Controller
* Parent class: [Home\Controller\CommonController](Home-Controller-CommonController.md)





Properties
----------


### $requestArray

    private mixed $requestArray = array()





* Visibility: **private**


### $allowMethod

    protected string $allowMethod = array('get', 'post', 'put', 'delete')

allowMethod



* Visibility: **protected**


### $allowType

    protected string $allowType = array('html', 'xml', 'json')

allowType



* Visibility: **protected**


### $defaultType

    protected string $defaultType = 'json'

defaultType



* Visibility: **protected**


### $_isDec

    protected mixed $_isDec = true





* Visibility: **protected**


Methods
-------


### getIndex

    \Home\Controller\json Home\Controller\PaperDataController::getIndex()

获取用户试卷列表

请求格式
```
  GET  /tiku/paperData
```

请求参数
```
 string combine // 条件查询组合，可用组合[sps](待续)
     说明：
        sps:['student_id','project_id','subject_id']
 json condition //根据查询组合，给出对于组合参数
     说明：
         sps:{"student_id":1,"project_id":1,"subject_id":1}
 int type            自由组卷type为20,所有试卷为-1
 string is_need_page 是否需要分页，'y'为需要,强制分页
 int page            第几页，默认为1
 int offset          每页记录条数，默认为10，最大为25条
 string order        例如：'id desc'
 string source       APP来源,默认为'web'
 string field        查询的字段名,
 string source       来源，如果是app的必传
                     默认为id,title,status,subject_id,project_id,modifydate,type
                     可以查询的有id,student_id,paper_id,runtime,score,report,regdate,status,subject_id,project_id,type,itemcount,modifydate,title,istask,partid,isimitate,source
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result'  => [
             {
                 'id': 学生答题的试卷ID
                 'student_id': 学生ID
                 'paper_id' : 后台试卷ID
                 'runtime': 答卷时间
                 'score': 分数
                 'report': 报告数据
                 'regdate': 生成时间
                 'status': 状态
                 'subject_id': 科目ID
                 'project_id': 项目ID
                 'type': 9为自由组卷
                 'itemcount': 试卷题目数量
                 'modifydate': 修改时间
                 'title': 试卷标题
                 'istask': 是否任务
                 'partid': 小节ID
                 'isimitate': 0为普通试卷，1为无纸化试卷
                 'source': 来源
             }
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '没有数据' => 11013012,
     '没有更多数据' => 11013013,
]
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\PaperDataController::post()

插入用户试卷

请求格式
```
  POST  /tiku/paperData
```

请求参数
```
string type_flag    point 根据知识点创建，paper根据试卷id创建
int student_id      学生ID
string source       来源
string is_need_all  是否需要全部数据，y是需要，n不需要，只返回试卷paper_data_student_log 的 id 默认y
string other_attribute 其他属性(默认无) 用英文逗号分割
       (favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
---------by 【paper】--------------
int paper_id        试卷ID（母卷）
---------by 【point】--------------
int item_num  题目数量，最大90
int item_type  题目类型 eg:单选，多选等   0随机 1单选 2多选 3判断 4填空 5综合题 6简答题 7不定向
int difficulty  难易度 0随机1难2中3易
int from  针对练习，0随机1已做2错题3全新
int takes_test  考试时长 默认90 最大90分钟
int top_icid  顶级知识点ID
string project_id  项目id
string subject_id  科目id
string icids  知识点集合 字符串
string top_icid_is_subjectId  top_icid所传参数是否为科目ID
string type_test  考试类型  1智能 old  2知识点 old  20自由组卷-考试模式
string title_test  试卷名称
int one_icid_item_num  每个知识点的拿题数量 0 为随机

```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result'  => [
         假如is_need_all为n的时候，只返回 "paper_data_log_id": "125"
         以下为is_need_all为y的时候
              {
                 "paper": {
                     "runtime": "考试时间",
                     "pdid": "用户试卷ID",
                     "regdate": "生成时间",
                     "type": "试卷类型",
                     "itemcount": "题目总数",
                     "paper_id": "试卷ID",
                     "title": "题目标题",
                     "subject_id": "项目ID",
                     "project_id": "科目ID",
                     "student_id": "用户ID",
                     "modifydate": "修改时间",
                     "score": "得分"
                     "paper_data_log_id" : "用户试卷单条做卷子记录"
                     "paper_data": [
                         {
                             "id": "ID",
                             "type":"大题类型",// 试卷才有 ，其他为0
                             "len": "题目数量",
                             "lens": "累计题目数量",
                             "examtype": "大题名称", // 试卷才有
                             "istrue": "正确题目数量", // 交卷之后统计
                             "pdata": [
                             {
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",//交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "select": [
                                   {
                                     "item_id": "题目ID",
                                     "item_option": "选项的值",
                                     "option": "选项序号(A,B,C,D)"
                                    }
                                  ],
                                 "answerAnalysis":"题目解析",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "sonitem": [
                                   {
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "partnum": "4",
                                       "yanswer": "",
                                         //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
                                       "select": [
                                         {
                                          "item_id": "题目ID",
                                          "item_option": "选项的值",
                                          "option": "选项序号(A,B,C,D)"
                                         }
                                        ],
                                       "answerAnalysis":"题目解析",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0"
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                  },
                             ],
                         },
                         ],

                      }
                  ],
              }
         }
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000002,
     '数据错误(试卷错误)' => 11013001,
     '试卷无权限' => 11013002,
     '生成试卷失败' => 11013003,
     '生成试卷失败' => 11013004,
     '所选知识点ID为空' => 11013014,
     '自由组卷生成失败' => 11013015,
]
```

* Visibility: **public**




### get

    \Home\Controller\json Home\Controller\PaperDataController::get($name)

获取一张用户试卷

请求格式
```
  GET  /tiku/paperData/2949621
```

请求参数
```
 int student_id 学生ID
 string pdid_is_pdlid 用户试卷id为用户试卷答题记录id //y是，n不是，默认n
 string other_attribute 其他属性(默认无)，用英文逗号分割
         (favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
 string source       来源
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result'  => [
              {
                 "paper": {
                     "runtime": "考试时间",
                     "pdid": "用户试卷ID",
                     "status": "试卷状态",
                     "regdate": "生成时间",
                     "type": "试卷类型",
                     "itemcount": "题目总数",
                     "paper_id": "试卷ID",
                     "title": "题目标题",
                     "subject_id": "项目ID",
                     "project_id": "科目ID",
                     "student_id": "用户ID",
                     "modifydate": "修改时间",
                     "score": "得分"
                     "paper_data_log_id" : "用户试卷单条做卷子记录"
                     "paper_data": [
                         {
                             "id": "ID",
                             "type":"大题类型",// 试卷才有 ，其他为0
                             "len": "题目数量",
                             "lens": "累计题目数量",
                             "examtype": "大题名称",// 试卷才有
                             "istrue": "正确题目数量", // 交卷之后统计
                             "pdata": [
                             {
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",
                                     //交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                       "select": [
                                         {
                                          "item_id": "题目ID",
                                          "item_option": "选项的值",
                                          "option": "选项序号(A,B,C,D)"
                                         }
                                        ],
                                 "answerAnalysis":"题目解析",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "sonitem": [
                                   {
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
                                       "select": [
                                         {
                                          "item_id": "题目ID",
                                          "item_option": "选项的值",
                                          "option": "选项序号(A,B,C,D)"
                                         }
                                        ],
                                       "answerAnalysis":"题目解析",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0"
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                  },
                             ],
                         },
                         ],

                      }
                  ],
              }
         }
         ]
     ]
```

返回码说明
```
 [
     '请求成功' => '00000000',
     '无此用户试卷' => '11013005',
 ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### put

    \Home\Controller\json Home\Controller\PaperDataController::put($name)

更新用户试卷

请求格式
```
  PUT  /tiku/paperData/2949621
```

请求参数
```
 int student_id 学生ID
 string field 需要题目的属性字段 当submit_type为3时有用，允许的参数为：
     'title','option','partnum','icid','type','analysis','pid','rightnum',
     'wrongnum','finishnum','favoritenum','isvideo','videoa','flag','answer'
 string source       来源
 json data 交卷信息,格式化之后：
                     [
                      {
                         "ualist":{"337182":"1","91704":"1","89870":"A"},题目ID为键，用户答案值
                         "rt":"31",// 用时（秒）
                         "pdid":"2949621",// 用户试卷ID
                         "submit_type":"1",// 1是交卷  2是保存 3是一题题交卷
                         "regdate":"1461722845"//交卷时间
                         "is_submit":"0",//当submit_type为3时，is_submit为1时交卷
                         'pdid_is_pdlid':'n' // 用户答题试卷记录id
                       }
                     ]
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result'  => [
             'hasSubmitPaper'=>['用户卷子ID'] //重复提交时返回值,不一定存在
             'hasSubmitItemInfo'=>[ //当submit_type为3时，存在
                 [
                     "88956" =>[
                         "title": "会计法律制度是调整的各种法律、法规、...",
                         "option": "A. 经济关系B. 会计关系C. 会计机构D. 国家在监管会计",
                         "answer": "B",
                         "item_id": 88956
                        ]
                 ]
            ]
         ]
     ]
```

返回码说明
```
[
     '请求成功' => '00000000',
     '无此用户试卷': '11013005',
     '参数错误' : '11013006',
     '请稍后再试' : '11013007',
     '重复交卷' : '11013008',
]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### delete

    \Home\Controller\json Home\Controller\PaperDataController::delete()

重新生成用户试卷(重做)

请求格式
```
  DELETE  /tiku/paperData/2949621
```

请求参数
```
 int student_id 学生ID
 string source 来源
 int is_repeat_exam 重做 1 //todo
 string source       来源
 string is_need_all  是否需要全部数据，y是需要，n不需要，只返回试卷paper_data_student_log 的 id 默认y
 string pdid_is_pdlid 用户试卷id为用户试卷答题记录id //y是，n不是，默认n
 string other_attribute 其他属性(默认无)，用英文逗号分割
        (favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result'  => [
         假如is_need_all为n的时候，只返回 "paper_data_log_id": "125"
         以下为is_need_all为y的时候
              {
                 "paper": {
                     "runtime": "考试时间",
                     "pdid": "用户试卷ID",
                     "regdate": "生成时间",
                     "type": "试卷类型",
                     "itemcount": "题目总数",
                     "paper_id": "试卷ID",
                     "title": "题目标题",
                     "subject_id": "项目ID",
                     "project_id": "科目ID",
                     "student_id": "用户ID",
                     "modifydate": "修改时间",
                     "score": "得分"
                     "paper_data_log_id" : "用户试卷单条做卷子记录"
                     "paper_data": [
                         {
                             "id": "ID",
                             "type":"大题类型",// 试卷才有 ，其他为0
                             "len": "题目数量",
                             "lens": "累计题目数量",
                             "examtype": "大题名称",// 试卷才有
                             "istrue": "正确题目数量", // 交卷之后统计
                             "pdata": [
                             {
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",// 交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "select": [
                                   {
                                     "item_id": "题目ID",
                                     "item_option": "选项的值",
                                     "option": "选项序号(A,B,C,D)"
                                    }
                                  ],
                                 "answerAnalysis":"题目解析",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量",
                                     // 根据请求参数other_attribute确定自己是否需要该属性
                                 "sonitem": [
                                   {
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
                                        "select": [
                                         {
                                             "item_id": "题目ID",
                                             "item_option": "选项的值",
                                             "option": "选项序号(A,B,C,D)"
                                         }
                                             ],
                                       "answerAnalysis":"题目解析",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]",
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0"
                                         // 根据请求参数other_attribute确定自己是否需要该属性
                                  },
                             ],
                         },
                         ],

                      }
                  ],
              }
         }
         ]
     ]
```

返回码说明
```
 [
     '请求成功' => '00000000',
     '所请求的试卷模块的参数错误' => '11013010',
     '无此用户试卷' => '1101300',
 ]
```

* Visibility: **public**




### testReport

    \Home\Controller\json Home\Controller\PaperDataController::testReport()

用户测试报告

请求格式
```
  get  /tiku/paperData/testReport
```

请求参数
```
int student_id  学生ID
int pdid  用户试卷ID
string pdid_is_pdlid 用户试卷id为用户试卷答题记录id //y是，n不是，默认n

```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result'  => [
             "id": "2951540", // 用户试卷ID
             "student_id": "8", // 学生ID
             "paper_id": "3891", // 试卷ID
             "runtime": "3", //用时（秒）
             "score": "50", // 得分
             "paper_data": [
                 {
                     "id": 0, // 序号
                     "type": "1", // "大题类型"，试卷才有 ，其他为0。1单选、2多选、3判断题、4填空题，5综合题、7不定向
                     "len": 2, // 题目数量
                     "lens": 2, // 累计题目数量
                     "examtype": "单选题", // 题目
                     "pdata": [
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",// 交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "select": [
                                   {
                                     "item_id": "题目ID",
                                     "item_option": "选项的值",
                                     "option": "选项序号(A,B,C,D)"
                                    }
                                  ],
                                 "sonitem": [
                                   {
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
                                       "select": [
                                          {
                                             "item_id": "题目ID",
                                             "item_option": "选项的值",
                                             "option": "选项序号(A,B,C,D)"
                                         }
                                         ],
                                  },
                     ],
                     "istrue": 1,// 大题答对题目数量
                     "usertypesocre": 50, // 个人大题得分
                     "typesocre": 100, // 大题总分
                     "typepercentum": 50 // 得分比
                 }
             ],
             "regdate": "1468976427", // 考试开始时间
             "status": "1", // 试卷状态：1交卷
             "subject_id": "26",// 项目ID
             "project_id": "4", // 科目ID
             "type": "3", // 试卷类型
             "itemcount": "2", // 题目数量
             "modifydate": "1468976434", // 交卷时间
             "paper_data_log_id": 352 // 用户答题试卷记录id
             "report": {
                 "avgnum": 25, // 平均分
                 "jb": 100, //击败率
                 "pnum": 1, // 排名
                 "title": "一级：任务制网课（持证无忧计划 ", // 试卷名称
                 "source": "高顿网校", // 来源
                 "score": "100", // 试卷总分
                 "passscore": "60", // 及格分
                 "highest": "50", // 最高分
                 "doPopleNum": "2", // 答题人总数
                 "takes": "120", // 考试推荐时长
                 "userScore": "50" // 个人得分
             }
            ]
     ]
```

返回码说明
```
 [
     '请求成功' => '00000000',
     '无此用户试卷' => '1101300',
 ]
```

* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseController::_initialize()

_initialize



* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)




### handleParameters

    mixed Home\Controller\CommonController::handleParameters()

处理参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### getParam

    mixed Home\Controller\CommonController::getParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### getFormParam

    mixed Home\Controller\CommonController::getFormParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### getAllParam

    mixed Home\Controller\CommonController::getAllParam()





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### getListCommonParam

    mixed Home\Controller\CommonController::getListCommonParam()

获取列表共有参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### delDirAndFile

    mixed Home\Controller\CommonController::delDirAndFile($dirName, $root)





* Visibility: **public**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $dirName **mixed**
* $root **mixed**



### __call

    mixed Home\Controller\BaseController::__call($method, $args)





* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $method **mixed**
* $args **mixed**



### display

    void Home\Controller\BaseController::display(string $templateFile, string $charset, string $contentType, string $content, string $prefix)

模板显示 调用内置的模板引擎显示方法，



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $templateFile **string** - &lt;p&gt;指定要调用的模板文件
默认为空 由系统自动定位模板文件&lt;/p&gt;
* $charset **string** - &lt;p&gt;输出编码&lt;/p&gt;
* $contentType **string** - &lt;p&gt;输出类型&lt;/p&gt;
* $content **string** - &lt;p&gt;输出内容&lt;/p&gt;
* $prefix **string** - &lt;p&gt;模板缓存前缀&lt;/p&gt;



### responseSuccess

    mixed Home\Controller\BaseController::responseSuccess($result)

请求成功响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $result **mixed**



### response

    mixed Home\Controller\BaseController::response($data, $type, $code)

响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $data **mixed**
* $type **mixed**
* $code **mixed**



### appException

    mixed Home\Controller\BaseController::appException(mixed $e)

appException



* Visibility: **public**
* This method is **static**.
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $e **mixed**



### halt

    mixed Home\Controller\BaseController::halt($error)





* Visibility: **public**
* This method is **static**.
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $error **mixed**



### _empty

    mixed Home\Controller\BaseController::_empty(String $name)





* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $name **String**


