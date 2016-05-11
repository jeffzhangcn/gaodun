Home\Controller\PaperDataController
===============






* Class name: PaperDataController
* Namespace: Home\Controller
* Parent class: [Home\Controller\CommonController](Home-Controller-CommonController.md)





Properties
----------


### $_requestArray

    private mixed $_requestArray = array()





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
 string other_attribute 其他属性(默认无)，用英文逗号分割(favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
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
                                 "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量" // 根据请求参数other_attribute确定自己是否需要该属性
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
                                       "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0" // 根据请求参数other_attribute确定自己是否需要该属性
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
 string other_attribute 其他属性(默认无)，用英文逗号分割(favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
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
                                 "yanswer": "答案",//交卷之后、已经做过提供正确答案
                                 "title": "题目题干",
                                 "option": "题目选项",
                                 "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量" // 根据请求参数other_attribute确定自己是否需要该属性
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
                                       "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0" // 根据请求参数other_attribute确定自己是否需要该属性
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
 string field 需要题目的属性字段 当submit_type为3时有用，允许的参数为：'title','option','partnum','icid','type','analysis','pid','rightnum','wrongnum','finishnum','favoritenum','isvideo','videoa','flag','answer'
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
                         "title": "会计法律制度是调整（&nbsp;&nbsp;&nbsp;&nbsp;）的各种法律、法规、规章和规范性文件的总称。",
                         "option": "<p>A. 经济关系&nbsp;&nbsp;&nbsp;</p><p>B. 会计关系&nbsp;</p><p>C. 会计机构、会计人员在办理会计事务过程中发生的经济关系&nbsp;</p><p>D. 国家在监管会计工作中发生的经济关系</p>",
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
 string other_attribute 其他属性(默认无)，用英文逗号分割(favorite,knowledge_point_tag,notenum,answerAnalysis) : 收藏、知识点标签、笔记数量
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
                                 "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                 "notenum": "笔记数量" // 根据请求参数other_attribute确定自己是否需要该属性
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
                                       "answerAnalysis":"题目解析", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "favorite": "是否收藏", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "knowledge_point_tag": "[知识点标签]", // 根据请求参数other_attribute确定自己是否需要该属性
                                       "notenum": "0" // 根据请求参数other_attribute确定自己是否需要该属性
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




### submitPaperOnlyOneItem

    \Home\Controller\json Home\Controller\PaperDataController::submitPaperOnlyOneItem()

交卷一题一题交卷判断，并且返回答案等等

请求格式
```
  POST  /tiku/paperData/submitPaperOnlyOneItem
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result'  => [

            ]
     ]
```

* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseController::_initialize()

_initialize



* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)




### _handleParameters

    mixed Home\Controller\CommonController::_handleParameters()

处理参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### _getParam

    mixed Home\Controller\CommonController::_getParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### _getListCommonParam

    mixed Home\Controller\CommonController::_getListCommonParam()

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



### _responseSuccess

    mixed Home\Controller\BaseController::_responseSuccess($result)

请求成功响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $result **mixed**



### _response

    mixed Home\Controller\BaseController::_response($data, $type, $code)

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


