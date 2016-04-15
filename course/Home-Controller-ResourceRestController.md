Home\Controller\ResourceRestController
===============

ResourceRestController




* Class name: ResourceRestController
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


### get

    mixed Home\Controller\ResourceRestController::get($name)

获取资源详情

请求格式
```
  GET  /course/Home/ResourceRest/11
 header [
   Accept: application/json
   App-Id-Key: gd_course_epiphany
   App-Timestamp:  1460697000
   App-Nonce: 3Rg5UE3OxO
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
    'err_no'   => '', //错误代码
    'err_msg'  => '', //错误信息
    'resut'  => {
       "id": "35",
       "course_id": "10",
       "courseware_id": "18",
       "name": "Theoverallfunctionandpurposeoftaxationinamoderneconomy",
       "partpath3": "<scriptsrc=\"http: //union.bokecc.com/player?vid=369DDABC424DA272&siteid=29639E609A1142B0&autoStart=false&width=720&height=405&playerid=2025478528BA86BE&playertype=1\"type=\"text/javascript\"></script>",
       "partpath": "<scriptsrc=\"http: //p.bokecc.com/player?vid=369DDABC424DA272&siteid=29639E609A1142B0&autoStart=false&width=100%&height=100%&playerid=2025478528BA86BE&playertype=1\"type=\"text/javascript\"></script>",
       "partpath_new": null,
       "series_id": "0",
       "type": "1",
       "exercise_id": null,
       "sortid": "0",
       "timekey": "0",
       "desc": "",
       "listentest": "1",
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
       "regdate": null,
       "checktime": null,
       "modifydate": null,
       "isdel": "0",
       "duration": "1",
       "gl_live_id": null,
       "kid": null
       }
     ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



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


