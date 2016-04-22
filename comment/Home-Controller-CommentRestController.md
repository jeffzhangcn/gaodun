Home\Controller\CommentRestController
===============

CommentRestController




* Class name: CommentRestController
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


### getIndex

    mixed Home\Controller\CommentRestController::getIndex()

获取课程评论列表

请求格式
```
 GET  /comment/Home/CommentRest
 query [
     course_id  = 1   //课程Id
     student_id = 111 //学生id
     page       = 1   //页数
     limit      = 10; //每页数量
     order      = 'id desc' //排序条件

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
         comments => [
             'id'=>'1',
             'course_id'=>'280',
             'courseware_id'=>'0',
             'courseware_part_id'=>'0',
             'student_id'=>'4954',
             'content'=>null,
             'type'=>'5',
             'status'=>'0',
             'regdate'=>'1368359450',
             'source': null,
             'isdel'=>'0',
             'modifydate': null,
             'replycomment': null,
             'isreply'=>'0',
             'project_id'=>'0',
             'subject_id'=>'0',
             'admin_id'=>'0',
             'isrecommend'=>'0'，
                     ...
         ]
         "page" => "1", //当前页
         "limit" => 10, //每页数量
         "total" => "1927", //总数
         "pageNums" => 1927 //页数
    ]
]
```

* Visibility: **public**




### post

    mixed Home\Controller\CommentRestController::post($id)

添加评论接口

请求格式
```
 POST  /comment/Home/CommentRest/1111
 query [
     course_id  = 1   //课程Id
     courseware_id
     courseware_part_id
     student_id
     content      //内容
     project_id
     subject_id

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
        id = 1
    ]
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


