Home\Controller\WareResourceRestController
===============

WareResourceRestController




* Class name: WareResourceRestController
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

    mixed Home\Controller\WareResourceRestController::get_index()

获取课件对应资源

请求格式
```
  GET  /course/Home/WareResourceRest/?ware_id=xxx
 header [
   Accept: application/json
   App-Id-Key: gd_course_ephipany
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
       "resource": [
           {
               "id": "86638",
               "course_id": "0",
               "courseware_id": "0",
               "name": "",
               "partpath3": "",
               "partpath": "\t",
               "partpath_new": "",
               "series_id": "0",
               "type": "1",
               "exercise_id": null,
               "sortid": "0",
               "timekey": "0",
               "desc": "",
               "listentest": "0",
               "isanswer": "0",
               "itemoption": "",
               "is_complete": "1",
               "is_enable": "0",
               "status": "0",
               "info": "",
               "upload_username": null,
               "check_username": null,
               "upload_admin_id": null,
               "check_admin_id": null,
               "regdate": "1460440279",
               "checktime": null,
               "modifydate": "1460440279",
               "isdel": "0",
               "duration": "1",
               "gl_live_id": "",
               "kid": null
           },
           {
               "id": "86639",
               "course_id": "0",
               "courseware_id": "0",
               "name": "资源1",
               "partpath3": "",
               "partpath": "\thttp://test.v.gaodun.com/admin.php?a=index&amp;m=Index",
               "partpath_new": "http://test.v.gaodun.com/admin.php?a=index&amp;m=Index",
               "series_id": "0",
               "type": "1",
               "exercise_id": null,
               "sortid": "0",
               "timekey": "0",
               "desc": "http://test.v.gaodun.com/admin.php?a=index&amp;m=Index",
               "listentest": "0",
               "isanswer": "0",
               "itemoption": "",
               "is_complete": "1",
               "is_enable": "0",
               "status": "0",
               "info": "",
               "upload_username": null,
               "check_username": null,
               "upload_admin_id": null,
               "check_admin_id": null,
               "regdate": "1460441427",
               "checktime": null,
               "modifydate": "1460441427",
               "isdel": "0",
               "duration": "1",
               "gl_live_id": "12",
               "kid": null
           }
       ],
       "num": 5
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


