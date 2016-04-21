Home\Controller\CourseAssignController
===============

CourseAssignController




* Class name: CourseAssignController
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


### post

    mixed Home\Controller\CourseAssignController::post()

派课

请求格式
```
  POST  /course/Home/CourseAssign
 header [
   Accept: application/json
   App-Id-Key: gd_course_assign
   App-Timestamp: 212121
   App-Nonce: notice
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]

```
请求说明
<table>

```
request [
     student_id : 学生id
     course_id : 课程id
     appoint_type : 0正常  1延期
     invalid_time : 截止日期
     isprobation : 0试听 1正式
     source : 来源
     admin_name : 后台派课管理员名字 如果不是则不传

]

```

</table>


返回格式
```
[
    'err_no'   => '', //错误代码
    'err_msg'  => '', //错误信息
    'resut'  => [
       assign:[
         {
          "id": "1290"
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


