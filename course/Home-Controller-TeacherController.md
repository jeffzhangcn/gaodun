Home\Controller\TeacherController
===============

TeacherController




* Class name: TeacherController
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

    mixed Home\Controller\TeacherController::get(mixed $id)

老师信息

请求格式

```
 GET  /course/Home/Teacher/1
 header [
   Accept: application/json
   App-Id-Key: gd_teacher
   App-Timestamp: 1
   App-Nonce: 1
   App-Signature: b561244fca99a87783fb3cbf29ce294e35607634
 ]

```



返回格式

```
 "status": 0,
 "info": "",
 "result": [
  '5':{
      "id": "5",
      "user_email": "zhoufei@gaodun.com",
      "name": "周老师",
      "sex": "2",
      "brithday": "0",
      "address": "",
      "phone": "",
      "school": "",
      "qq": "",
      "project_id": "9",
      "subject_id": "",
      "desc": "10年证券行业资产管理业务经验，5年证券从业资格培训经验，《证券市场基础知识--“知识源”》主编，授课基本功底扎实，授课细致，重难点娓娓道来，授课一次性通过率达95%以上。",
      "photo": "Teacher/2013/09/03/4f8dac2bd3465.jpg",
      "video": "",
      "sortid": "42",
      "group_id": "1",
      "iscomment": "1",
      "member_id": "30",
      "isdel": "0",
      "titles": ""
  }
]

```

* Visibility: **public**


#### Arguments
* $id **mixed**



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


