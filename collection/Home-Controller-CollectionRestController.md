Home\Controller\CollectionRestController
===============

收藏接口
Class CollectionRestController




* Class name: CollectionRestController
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


### __construct

    mixed Home\Controller\CollectionRestController::__construct()





* Visibility: **public**




### getIndex

    mixed Home\Controller\CollectionRestController::getIndex()

获取收藏信息列表

请求格式
```
GET  /collection/Home/CollectionRest
query[
     student_id = 666
     course_id = 11;
     type = 1;
     page    = 1   //页数
     limit   = 10; //每页数量
     order   = 0   // 0:id desc  1:id asc
]
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
    status   => 0,//错误代码
    info     => '',//错误信息
    result   =>[
         collections => [
             "id": "66",
             "course_id" => "22",
             "student_id" => "10",
             "regdate" => "1461554378",
             "isdel" => "0",
             "type" => "1",
             "source" => "0"
         ]
         "page" => "1", //当前页
         "limit" => 10, //每页数量
         "total" => "3", //总数
         "pageNums" => 1 //页数
    ]
]
```

* Visibility: **public**




### post

    mixed Home\Controller\CollectionRestController::post()

添加收藏

请求格式
```
 POST  /collection/Home/CollectionRest
 query [
     course_id  = 1   //课程Id
     student_id = 111 //学生id
     type       = 0未收藏 1 已收藏
     source     = 0; //web 默认为0

 ]
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
    status   => 0,//错误代码
    info     => '',//错误信息
    result   => [
         id = 1;
     ]
 ]
```

* Visibility: **public**




### delete

    mixed Home\Controller\CollectionRestController::delete($id)

取消收藏

请求格式
```
 delete  /collection/Home/CollectionRest/1
 query [

 ]
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
    status   => 0,//错误代码
    info     => '',//错误信息
    result   => []
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


