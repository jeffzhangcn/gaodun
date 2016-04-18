Home\Controller\NoteRestController
===============

QuestionController




* Class name: NoteRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


### $_noteLogic

    protected mixed $_noteLogic





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




### notes 

    mixed Home\Controller\NoteRestController::notes()

获取笔记列表

请求格式
```
 GET  /care/home/notes
 query [
      course_id=1//课程id
     course_ware_id=2//课件id
     courseware_part_id=3//课件段id
     student_id=89//学生id
     type=1//类型
     order='id desc'//order规则
     ps=10//每页数量
     page=1//页码
   ]
   get参数均选填
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
          'id' => '10891',
           'course_id' => '785',
           'course_ware_id' => '11177',
           'courseware_part_id' => '58287',
           'student_id' => '12002',
           'content' => 'rfewrewrew',
           'status' => '0',
           'regdate' => '1460714640',
           'isdel' => '0',
           'label_id' => '0',
           'isself' => '0',
           'type' => '1',
           'subject_id' => '48',
           'project_id' => '14',
           'video_time' => '64',
           'modifydate' => NULL,
           'pdid' => '0',
           'source' => '0',
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




### note

    mixed Home\Controller\NoteRestController::note()

写笔记

请求格式
```
 POST  /care/home/note
 form-param [
      course_id=1//课程id
     course_ware_id=2//课件id
     courseware_part_id=3//课件段id
     project_id=4
     subject_id=5
     isself=1
     student_id=89//学生id
     type=1//类型
     content='tsetss'//内容
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
result=>[
    'status'   => '', //错误代码
    'info'  => '', //错误信息
    'id'  => 1, //提问ID
]
```

* Visibility: **public**




### test

    mixed Home\Controller\NoteRestController::test()





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


