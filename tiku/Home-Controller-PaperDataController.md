Home\Controller\PaperDataController
===============






* Class name: PaperDataController
* Namespace: Home\Controller
* Parent class: Home\Controller\CommonController





Properties
----------


### $description

    protected array<mixed,callable> $description = null





* Visibility: **protected**


Methods
-------


### getIndex

    mixed Home\Controller\PaperDataController::getIndex()

获取用户试卷列表

请求格式
```
  GET  /tiku/paperData
```
返回格式
```
     [
         'status'   => '', //提示码
         'info'  => '', //提示信息

     ]
```

* Visibility: **public**




### post

    array Home\Controller\PaperDataController::post()

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
 string source       APP来源
 string sessionId    sessionId
 string liveType     0正常生成题目， 1实时解析
```

返回格式
```php
     [
          'status'   => '', //提示码
          'info'  => '', //提示信息
          'resut'  => [
              "paper": {
                 "runtime": "未使用的答题时间",
                 "id": "试卷数据ID",
                 "pdid": "试卷数据ID",
                 "regdate": "生成时间",
                 "type": "生成类型",
                 "itemcount": "题目总数",
                 "paper_id": "试卷ID",
                 "title": "试卷标题",
                 "subject_id": "科目ID",
                 "project_id": "项目ID",
                 "student_id": "1878488",
                 "modifydate": "1461655112",
                 "score": "0"
                 "paper_data":
                 [
                     {
                     "id": "题目顺序",
                     "type": "类型",
                     "len": "题目数量",
                     "lens": "题目数量",
                     "examtype": "题目类型",
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
                             "title": "题目题干",
                             "option": "题目选项",
                             "answerAnalysis": "题目解析",
                             "favorite": "是否收藏",
                             "knowledge_point_tag": "[知识点标签]",
                             "notenum": "笔记数量"
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
                                       "answer": "B,D",
                                       "notenum": "0"
                                  },
                             ],
                             },
                         ]
                     },
                  ]
             }
            ]
     ]
```
错误码说明
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

    array Home\Controller\PaperDataController::get()

获取一张用户试卷

请求格式
```
  GET  /tiku/paperData/1
```
请求参数
```
 int student_id 学生ID

```
返回格式
```
     [
         'status'   => '', //返回码
         'info'  => '', //提示信息
         'resut'  => [
              {
                 "paper": {
                     "runtime": "考试时间",
                     "id": "用户试卷ID",
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
                             "type":"题目类型",
                             "len": "题目数量",
                             "lens": "题目数量",
                             "examtype": "试题类型",
                             "istrue": "正确题目数量",
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
                                 "yanswer": "答案",//交卷之后提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "answerAnalysis": "题目解析",
                                 "favorite": "是否收藏",
                                 "knowledge_point_tag": "[知识点标签]",
                                 "notenum": "笔记数量"
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
                                       "notenum": "0"
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

    mixed Home\Controller\PaperDataController::put($name)

更新用户试卷

请求格式
```
  PUT  /tiku/paperData/2949602
```
请求参数
```
 int student_id 学生ID
 json data 交卷信息,格式化之后：
                     [
                      {
                         "ualist":{"337182":"1","91704":"1","89870":"A"},题目ID为键，用户答案值
                         "rt":"31",// 用时（秒）
                         "pdid":"2949621",// 用户试卷ID
                         "submit_type":"1",// 1是交卷  2是保存
                         "regdate":"1461722845"//交卷时间
                       }
                     ]
```
返回格式
```
     [
         'status'   => '', //提示码
         'info'  => '', //提示信息
         'resut'  => [
             "重复提交时返回值":'用户卷子ID'

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

    mixed Home\Controller\PaperDataController::delete()

删除用户试卷

请求格式
```
  DELETE  /tiku/paperData
```
返回格式
```
     [
         'status'   => '', //提示码
         'info'  => '', //提示信息
         'resut'  => [

            ]
     ]
```

* Visibility: **public**



