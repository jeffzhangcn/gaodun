Home\Controller\CourseSyllabusRestController
===============

CourseSyllabusRestController




* Class name: CourseSyllabusRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


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


### get_index

    mixed Home\Controller\CourseSyllabusRestController::get_index()

获取课程大纲

请求格式
```
  GET  /course/Home/CourseSyllabusRest/course_id=11&level=2
 header [
   Accept: application/json
   App-Id-Key: gd_demo_abcdef
   App-Timestamp: 212121
   App-Nonce: eewewew
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
    'err_no'   => '', //错误代码
    'err_msg'  => '', //错误信息
    'resut'  => [
       syllabus:[
         {
          "id": "1290",
          "kid": "0",
          "project_id": "14",
          "subject_id": "130",
          "title": "资产",
          "sid": "",
          "pid": "0",
          "regdate": "1457524311",
          "modifydate": "1457524311",
          "isdel": "0",
          "difficulty": "",
          "score": "",
          "question_num": "0",
          "testrate": "",
          "level": "0"
       },
       ......
       {
          "id": "1709",
          "kid": "0",
          "project_id": "29",
          "subject_id": "132",
          "title": "总论",
          "sid": "3",
          "pid": "0",
          "regdate": "1457524475",
          "modifydate": "1457524475",
          "isdel": "0",
          "difficulty": "",
          "score": "",
          "question_num": "0",
          "testrate": "",
          "level": "0"
       }
        ]
          ]
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


