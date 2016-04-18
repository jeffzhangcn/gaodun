Home\Controller\QuestionRestController
===============

QuestionController




* Class name: QuestionRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


### $_askLogic

    protected mixed $_askLogic





* Visibility: **protected**


### $_page

    protected mixed $_page = 1





* Visibility: **protected**


### $_ps

    protected mixed $_ps = 10





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


### __construct

    mixed Home\Controller\BaseRestController::__construct()





* Visibility: **public**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)




### questions

    mixed Home\Controller\QuestionRestController::questions()

获取提问列表

请求格式
```
 GET  /care/home/questions
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
   info      => '',//错误信息
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




### store

    mixed Home\Controller\QuestionRestController::question()

提问

请求格式
```
 POST  /care/home/question
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
result=>[
    'status'   => '', //错误代码
    'info'  => '', //错误信息
    'id'  => 1, //提问ID
]
```

* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseRestController::_initialize()

_initialize



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


