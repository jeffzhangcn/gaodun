Home\Controller\SeriesByCourseController
===============

SeriesByCourseController
课程id获取系列id




* Class name: SeriesByCourseController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


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


Methods
-------


### get

    mixed|void Home\Controller\SeriesByCourseController::get(integer $courseId)

课程id获取系列列表

请求格式
```
  POST  /course/Home/SeriesByCourse/785
 header [
   Accept: application/json
   App-Id-Key: gd_course_assign
   App-Timestamp: 1
   App-Nonce: 1
   App-Signature: b561244fca99a87783fb3cbf29ce294e35607634
 ]

```

返回格式
```
{
     "status": 0,
     "info": "",
     "result": [
         {
             "id": "1041",
             "sname": "初级会计实务",
             "course_id": "785",
             "sortid": "1",
             "picture": null,
             "show": "1"
         },
         {
             "id": "1076",
             . . . . .
         }
     ]
}
```

* Visibility: **public**


#### Arguments
* $courseId **integer**



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


