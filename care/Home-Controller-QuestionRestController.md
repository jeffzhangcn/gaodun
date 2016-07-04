Home\Controller\QuestionRestController
===============

QuestionRestController




* Class name: QuestionRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


### $askLogic

    protected mixed $askLogic = null





* Visibility: **protected**


### $askQuestionsLogic

    protected mixed $askQuestionsLogic = null





* Visibility: **protected**


### $page

    protected mixed $page = 1





* Visibility: **protected**


### $ps

    protected mixed $ps = 10





* Visibility: **protected**


### $allowMethod

    protected string $allowMethod = array('get', 'post', 'put')

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


Methods
-------


### getIndex

    mixed Home\Controller\QuestionRestController::getIndex()

请求提问列表

请求格式
```
     GET  /care/home/list

     query [
     (string)type //1课程(视频+知识点反馈+无归属);2题目;3线下答疑;4论坛;(app和v如果要全部请传'1,2',别拿3和4的,会出错;)
     (int)course_id //type为1时，课程id
     (int)item_id //type为2时，题目id
     (int)course_ware_id //课件id
     (int)courseware_part_id //课件段id
     (string)project_id //项目id 多个可用逗号隔开 '1,3,4'
     (string)subject_id //科目id 多个可用逗号隔开 '11,12,13'
     (string)order='id desc'//排序规则
     (int)ps //每页数量
     (int)page_num //第几页数据
     (int)studnet_id //0:全部问题, 其他:指定获取某个student_id的提问
     (int)data_begin_time //时间范围,起始日期
     (int)data_end_time //时间返回,截止日期
     (string)reply  //'each_recently_reply':每个问题带一个最近回复,'each_full_zhuiwen' 每个问题带完整的回复和追问回答列表
     (int) q_status //问题的状态
    ]
     部分选填
     header [
     Accept: application/json
     App-Id-Key: gd_care_partner
     App-Timestamp: 464666145
     App-Nonce: jksfjkjf
     App-Signature: babc722817e366cf62f883e2b61532505c674920a
    ]
```
返回格式
```
[
   status    => 0,//错误代码
      info       => '',//错误信息
   result   => [
      questions => [
            0=>[
          'id' => '2',
          'from_ask_id' => '0',
          'admin_id' => '0',
          'get_id' => '0',
          'course_id' => '180',
          'course_ware_id' => '2406',
          'courseware_part_id' => '9865',
          'class_id' => '0',
          'student_id' => '2643',
          'content' => 'Mail capabilities required? ',
          'more_content' => NULL,
          'status' => '0',
          'regdate' => '1368353871',
          'modifydate' => '0',
          'is_display' => '0',
          'click_count' => '0',
          'inform_num' => '0',
          'isdel' => '1',
          'type' => '1',
          'feedback_type' => '0',
          'video_time' => '0',
          'isreply' => '0',
          'project_id' => '1',
          'subject_id' => '61',
          'file_url' => '',
          'timage_url' => '',
          'accept' => '0',
          'is_view' => '0',
          'ask_more_num' => '0',
          'source' => '0',
          'icid' => '0',
          'answer_time' => '0',
          'assign_time' => '0',
          'accept_time' => '0',
          'source_type' => NULL,
          'sort' => NULL,
          'is_top' => '0',
          'custom_flag' => '0',
          'item_id' => '0',
          'big_course_id' => NULL,
          'type_id' => NULL,
            ]
           1=>[...]
           ...
           ]
         total=>102,//总数量
         page=>1,//页码
          ps=>10,每页数量
       ]
]
```

* Visibility: **public**




### addAsk

    mixed Home\Controller\QuestionRestController::addAsk()

*  添加新问题
```
 POST  /care/home/ask
 form-param [
     course_id(选填)
     course_ware_id(选填)
     course_ware_part_id(选填)
     student_id(必填)
     content(必填)
     more_content(选填)
     type :(必填) 1 视频, 2 题库 3论坛 4 线下
     icid :(选填)
     source_type : (必填)string ('bbs'|'app'|'tiku'|'ft_college'|'v')
     subject_id :(必填)
     project_id :(必填)
     class_id :(选填)
     item_id : (选填)type2时必穿,题目id
     type_id : (选填)cfa分类
     big_course_id :(选填)
     position :来源为ft_college记录来源位置(选填)
     custom_flag : (选填)与source_type对应记录id,source_type为bbs时为bbs表的tid,ft_college时为财税表的id

]
 header [
   Accept: application/json
   App-Id-Key: gd_care_partner
   App-Timestamp: 464666145
   App-Nonce: jksfjkjf
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
   status    => 0,//错误代码
   info       => '',//错误信息
   result   => (int)id //新添加的主键id

```

* Visibility: **public**




### getOneAskInfo

    mixed Home\Controller\QuestionRestController::getOneAskInfo()

获取问题详情
```
 GET  /care/home/askdetail
 query[
    (int)ask_id: 问题id
   ]
   post参数均选填
 header [
   Accept: application/json
   App-Id-Key: gd_care_partner
   App-Timestamp: 464666145
   App-Nonce: jksfjkjf
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
   status    => 0,//错误代码(160000为model验证错误)
   info       => '',//错误信息
   result   => [
'id' => string '262968' (length=6)
'from_ask_id' => string '0' (length=1)
'admin_id' => string '1' (length=1)
'get_id' => string '1' (length=1)
'course_id' => string '42' (length=2)
'course_ware_id' => string '15715' (length=5)
'courseware_part_id' => string '80192' (length=5)
'class_id' => string '0' (length=1)
'student_id' => string '1694789' (length=7)
'content' => string 'addask11111' (length=11)
'more_content' => null
'status' => string '1' (length=1)
'regdate' => string '1467020233' (length=10)
'modifydate' => string '1467022081' (length=10)
'is_display' => string '0' (length=1)
'click_count' => string '5' (length=1)
'inform_num' => string '0' (length=1)
'isdel' => string '0' (length=1)
'type' => string '1' (length=1)
'video_time' => string '0' (length=1)
'project_id' => string '2' (length=1)
'subject_id' => string '114' (length=3)
'file_url' => string '' (length=0)
'timage_url' => null
'accept' => string '0' (length=1)
'is_view' => string '0' (length=1)
'ask_more_num' => string '1' (length=1)
'source' => string '0' (length=1)
'icid' => string '0' (length=1)
'last_answer_time' => string '0' (length=1)
'last_ask_time' => string '0' (length=1)
'accept_time' => string '0' (length=1)
'source_type' => null
'sort' => string '0' (length=1)
'is_top' => string '0' (length=1)
'custom_flag' => string '0' (length=1)
'item_id' => string '0' (length=1)
'big_course_id' => null
'type_id' => string '0' (length=1)
'position' => null
'current_zhui_num' => string '0' (length=1)
'last_duration' => string '0' (length=1)
'other_anwer' =>[ (其他回答,若无其他回答此值为空数组)
0 =>
array (size=17)
'id' => string '65379' (length=5)
'pid' => string '0' (length=1)
'ask_id' => string '262968' (length=6)
'student_id' => string '247004' (length=6)
'content' => string 'connie<br />' (length=12)
'status' => string '3' (length=1)
'regdate' => string '1467022081' (length=10)
'isdel' => string '0' (length=1)
'isteach' => string '0' (length=1)
'file_url' => string '' (length=0)
'accept' => string '0' (length=1)
'answer_id' => string '0' (length=1)
'up_num' => string '0' (length=1)
'custom_id' => null
'recommendation' => null
'modifydate' => string '0' (length=1)
'is_display' => string '0' (length=1)
]

'answer' => [ (最佳回答及最佳回答的追问,追问回答列表)
'id' => string '65376' (length=5)
'pid' => string '0' (length=1)
'ask_id' => string '262968' (length=6)
'student_id' => string '1' (length=1)
'content' => string '<p>老师的回答1</p>' (length=23)
'status' => string '2' (length=1)
'regdate' => string '1467020407' (length=10)
'isdel' => string '0' (length=1)
'isteach' => string '1' (length=1)
'file_url' => null
'accept' => string '1' (length=1)
'answer_id' => string '0' (length=1)
'up_num' => string '0' (length=1)
'custom_id' => null
'recommendation' => null
'modifydate' => string '1467020407' (length=10)
'is_display' => string '1' (length=1)
'trace_list' =>[ (最佳回答的追问,追问回答列表,isteach=0表示追问,为1表示老师回答,已经按时间排序,顺序为追问,回答追问,追问,回答追问.....,如无追问此值为空数组[])
0 =>
array (size=17)
'id' => string '65377' (length=5)
'pid' => string '65376' (length=5)
'ask_id' => string '262968' (length=6)
'student_id' => string '1694789' (length=7)
'content' => string '追问咯1' (length=10)
'status' => string '0' (length=1)
'regdate' => string '1467020465' (length=10)
'isdel' => string '0' (length=1)
'isteach' => string '0' (length=1)
'file_url' => null
'accept' => string '0' (length=1)
'answer_id' => string '0' (length=1)
'up_num' => string '0' (length=1)
'custom_id' => null
'recommendation' => null
'modifydate' => string '0' (length=1)
'is_display' => string '0' (length=1)
1 =>
array (size=17)
'id' => string '65378' (length=5)
'pid' => string '65376' (length=5)
'ask_id' => string '262968' (length=6)
'student_id' => string '1' (length=1)
'content' => string '<p>回答追问1</p>' (length=20)
'status' => string '2' (length=1)
'regdate' => string '1467021815' (length=10)
'isdel' => string '0' (length=1)
'isteach' => string '1' (length=1)
'file_url' => null
'accept' => string '0' (length=1)
'answer_id' => string '0' (length=1)
'up_num' => string '0' (length=1)
'custom_id' => null
'recommendation' => null
'modifydate' => string '1467021815' (length=10)
'is_display' => string '1' (length=1)

]
```

* Visibility: **public**




### traceAsk

    mixed Home\Controller\QuestionRestController::traceAsk()

追问
```
 GET  /care/home/trace
 form-param [
(int)ask_id:要追问的提问id(必须)
     (string)content:追问内容(必须)
     (int)student_id:学生id(必须)
   ]
 header [
   Accept: application/json
   App-Id-Key: gd_care_partner
   App-Timestamp: 464666145
   App-Nonce: jksfjkjf
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```

返回格式
```
[
   status    => 0,//错误代码(160000为model验证错误)
   info       => '',//错误信息
   result   => (int)id //追问的id

```

* Visibility: **public**




### answer

    mixed Home\Controller\QuestionRestController::answer()

学生回复问题
```
 POST  /care/home/answer
 form-param [
     ask_id 必须
     content 必须
     student_id 必须
     isteach 必须 = 0

]
   post参数均选填
 header [
   Accept: application/json
   App-Id-Key: gd_care_partner
   App-Timestamp: 464666145
   App-Nonce: jksfjkjf
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
   status    => 0,//错误代码
   info       => '',//错误信息
   result   => (int)id //新添加的主键id

```

* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseRestController::_initialize()

_initialize



* Visibility: **public**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)




### __construct

    mixed Home\Controller\BaseRestController::__construct()





* Visibility: **public**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)




### __call

    mixed Home\Controller\BaseRestController::__call($method, $args)





* Visibility: **public**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)


#### Arguments
* $method **mixed**
* $args **mixed**



### display

    void Home\Controller\BaseRestController::display(string $templateFile, string $charset, string $contentType, string $content, string $prefix)

模板显示 调用内置的模板引擎显示方法，



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)


#### Arguments
* $templateFile **string** - &lt;p&gt;指定要调用的模板文件
默认为空 由系统自动定位模板文件&lt;/p&gt;
* $charset **string** - &lt;p&gt;输出编码&lt;/p&gt;
* $contentType **string** - &lt;p&gt;输出类型&lt;/p&gt;
* $content **string** - &lt;p&gt;输出内容&lt;/p&gt;
* $prefix **string** - &lt;p&gt;模板缓存前缀&lt;/p&gt;


