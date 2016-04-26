Home\Controller\CourseAssignController
===============

CourseAssignController




* Class name: CourseAssignController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)



Constants
----------


### DB_ERROR

    const DB_ERROR = 10001





### PARAM_ERROR

    const PARAM_ERROR = 10002





### ERROR

    const ERROR = 10003





Properties
----------


### $_type

    protected mixed $_type = array('', ' id desc ', ' id asc ')





* Visibility: **protected**


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


### post

    mixed Home\Controller\CourseAssignController::post()

派课

请求格式
```
  POST  /course/Home/CourseAssign
 header [
   Accept: application/json
   App-Id-Key: gd_course_assign
   App-Timestamp: 1
   App-Nonce: 1
   App-Signature: b561244fca99a87783fb3cbf29ce294e35607634
 ]

```
请求说明

```
request [
     student_id : 1694699    学生id
     course_id : 5   课程id
     appoint_type : 0正常  1延期
     invalid_time : 6    截止日期
     isprobation : 0试听 1正式
     source : 网校     来源
     admin_id : 1   后台派课管理员id 如果前台调用传0
     admin_name : admin   后台派课管理员名字 如果不是则不传

]

```



返回格式
```
[
    "status": 10003,
"info": "error",
"result": [
{
"1281": {
"status": 10001,
"info": {
"invalid_time": "截止日期错误！"
}
}
},
```

* Visibility: **public**




### getIndex

    mixed Home\Controller\CourseAssignController::getIndex()

派课查询

请求格式
```
  Get  /course/Home/CourseAssign
 header [
   Accept: application/json
   App-Id-Key: gd_course_assign
   App-Timestamp: 1
   App-Nonce: 1
   App-Signature: b561244fca99a87783fb3cbf29ce294e35607634
 ]

```
请求说明

```
request [
     student_id : 1694699,
     course_id : 5
     limit : 8,
     order : 1, // 1＝>id desc 2=>id asc

]

```


返回格式
```
[
    'status'   => '', //错误代码
    'info'  => '', //错误信息
    'result'  => [{
          "resource"=>[
          "id": "94174",
"student_id": "1694699",
"course_id": "450",
"ass_time": "1445940772",
"invalid_time": "1460649600",
"regdate": "1445940772",
"modifydate": "1445940772",
"isincview": "0",
"appoint_type": "1",
"task_model": null,
"examtime": null,
"type": "0",
"messagenumber": "0",
"isdel": "0",
"isprobation": "1",
"admin_id": "0",
"admin_name": "",
"subject_id": "130",
"project_id": "14",
"expires_time": "0",
"source": "0",
"is_big": "1348",
"colse_question": "0",
"customtime": "1,2,3,4,5,6,7",
"other": "",
"month": "0",
"big_project_id": null,
"kk_sign": "1",
"yq_date": "0"
             ]
          },{
....
          }
          ],
         "num"=>5
         ]
```

* Visibility: **public**




### delete

    mixed Home\Controller\CourseAssignController::delete($id)

派课删除

请求格式
```
  Delete  /course/Home/CourseAssign/1694699
 header [
   Accept: application/json
   App-Id-Key: gd_course_assign
   App-Timestamp: 1
   App-Nonce: 1
   App-Signature: b561244fca99a87783fb3cbf29ce294e35607634
 ]

```
请求说明

```
request [
     id : 99

]

```


返回格式
```
[
    'status'   => '', //错误代码
    'info'  => '', //错误信息
    'result'  => [
          '删除成功'
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


