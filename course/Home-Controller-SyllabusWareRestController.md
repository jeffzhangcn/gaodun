Home\Controller\SyllabusWareRestController
===============

SyllabusWareRestController




* Class name: SyllabusWareRestController
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


### getIndex

    mixed Home\Controller\SyllabusWareRestController::getIndex()

获取大纲课件

请求格式
```
  GET  /course/Home/SyllabusWareRest/?syllabus_id=xx&course_id=xxx
 header [
   Accept: application/json
   App-Id-Key: gd_syllabus_ephipany
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
    'resut'  => {
     "courseware": [
         {
             "id": "58",
             "name": "A2 Stakeholders in business organisations",
             "summary": "",
             "ppt": "",
             "ppturl": "",
             "ppt2": "",
             "ppt2url": "",
             "paper": "0",
             "uploadtime": "1335608753",
             "keypoint_ids": "",
             "sortid_bak": "12",
             "task_id": null,
             "status": "0",
             "type": "0",
             "difficulty": "1",
             "major": "1",
             "duration": "1",
             "listentest": "0",
             "modifydate": "1460102314",
             "study_time": "0",
         }
     ],
     "num": 1
   }
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


