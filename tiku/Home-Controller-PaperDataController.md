Home\Controller\PaperDataController
===============

用户试卷




* Class name: PaperDataController
* Namespace: Home\Controller
* Parent class: Home\Controller\CommonController







Methods
-------


### getIndex

    \Home\Controller\json Home\Controller\PaperDataController::getIndex()

获取用户试卷列表

请求格式
```
  GET  /tiku/paperData
```
返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',

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
 string other_attribute 其他属性(默认无) 用英文逗号分割
        (favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
 ---------by 【paper】--------------
 int paper_id        试卷ID（母卷）
 ---------by 【point】--------------
 string etype        试卷类型1智能，2知识点，3真题，4组卷
 string projectId    项目id
 string subjectId    科目id
 string icids        知识点集合
 string num          选题总数
 string type         0新题目，1已做题目
 string items_type   0随机，1单选，2多选，3判断题，4简答题，5综合
 string rank         难易度
 string mark         标识存储过程的执行（与效率有关）
 string pid          试卷id
 string from         来源  1favorite，2error
 string sessionId    sessionId
 string liveType     0正常生成题目， 1实时解析
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
                                 "ID": '1',
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "link_ExamID": "",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",//交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
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
                                       "ID": "题目顺序",
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "link_ExamID": "关联题目",
                                       "partnum": "4",
                                       "yanswer": "",
                                         //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
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
     '数据错误' => 11013001,
     '试卷无权限' => 11013002,
     '生成试卷失败' => 11013003,
     '生成试卷失败' => 11013004,
]
```

* Visibility: **public**




### get

    \Home\Controller\json Home\Controller\PaperDataController::get()

获取一张用户试卷

请求格式
```
  GET  /tiku/paperData/2949621
```

请求参数
```
 int student_id 学生ID
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
                                 "ID": '1',
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "link_ExamID": "",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",
                                     //交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
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
                                       "ID": "题目顺序",
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "link_ExamID": "关联题目",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
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
 string other_attribute 其他属性(默认无)，用英文逗号分割
        (favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
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
                                 "ID": '1',
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "link_ExamID": "",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",// 交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
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
                                       "ID": "题目顺序",
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "link_ExamID": "关联题目",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
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
                                 "ID": '1',
                                 "ExamID": "题目ID",
                                 "userAnswer": "用户答案",
                                 "scoreses": "分数",
                                 "userScore": "用户分数",
                                 "istrue": "是否正确",
                                 "type": "题目类型",
                                 "sorts": "排序",
                                 "link_ExamID": "",
                                 "partnum": "选项数量",
                                 "yanswer": "答案",// 交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "sonitem": [
                                   {
                                       "ID": "题目顺序",
                                       "ExamID": "题目ID",
                                       "userAnswer": "用户答案",
                                       "scoreses": "分数",
                                       "userScore": "用户分值",
                                       "istrue": "是否正确",
                                       "type": "题目类型",
                                       "sorts": "顺序",
                                       "link_ExamID": "关联题目",
                                       "partnum": "4",
                                       "yanswer": "", //交卷之后提供正确答案
                                       "title": "题目题干",
                                       "option": "题目选项",
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
             "report": {
                 "avgnum": 25, // 平均分
                 "jb": 100, //击败率
                 "pnum": 1, // 排名
                 "title": "一级：任务制网课（持证无忧计划）-SS8：Financial Reporting and Analysis：The Income Statement, Balance Sheet, and Cash ", // 试卷名称
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



