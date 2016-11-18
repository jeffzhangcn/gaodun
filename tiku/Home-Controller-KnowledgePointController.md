Home\Controller\KnowledgePointController
===============






* Class name: KnowledgePointController
* Namespace: Home\Controller
* Parent class: [Home\Controller\CommonController](Home-Controller-CommonController.md)





Properties
----------


### $requestArray

    private mixed $requestArray = array()





* Visibility: **private**


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


### $_isDec

    protected mixed $_isDec = true





* Visibility: **protected**


Methods
-------


### getIndex

    \Home\Controller\json Home\Controller\KnowledgePointController::getIndex()

获取知识点信息

请求参数
```
string combine 查询条件组，可选【inIds】待续
json condition 条件数据
   说明：inIds:['in'=>'id']
string source 来源，如果是app的必传
string field 需要字段 默认：project_id,subject_id,title,difficulty,definition,testrate
```

请求格式
```
  GET  /tiku/KnowledgePoint
```
返回格式
```
     [
         "status"   => '返回码',
         "info"  => '提示信息',
         "result": [
             {
     "project_id": "项目ID",
"subject_id": "科目ID",
"title": "知识点名称",
"difficulty": "难度",
"definition": "定义",
"testrate": "考率" //（1、必考，2、常考，3、不怎么考，4、不考）
             }
         ]
     ]
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\KnowledgePointController::post()

插入纠错

请求格式
```
  POST  /tiku/PaperRewrong
```

请求参数
```
int item_id    纠错的题目ID
int error_type      纠错类型
                  1, // 错别字
                  2, // 答案有误
                  3, // 排版错误
                  4, // 图片模糊
                  5, // 答案有异议
                  6 // 其他错误
string student_id       学生id，未登录请求为-1
string error_string  纠错内容
string source  来源。pc为web,必填

返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',

     ]
```
提示码说明
```
[
     '请求成功' => 00000000,
     '无题目信息' => '11013101'
]
```
请求参数
```
```

* Visibility: **public**




### get

    array Home\Controller\KnowledgePointController::get(string $name)

获取一张用户试卷

请求格式
```
  GET  /tiku/paperData/1
```
返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [

            ]
     ]
```

* Visibility: **public**


#### Arguments
* $name **string** - &lt;p&gt;用户试卷ID&lt;/p&gt;



### put

    \Home\Controller\json Home\Controller\KnowledgePointController::put($name)

更新用户试卷

请求格式
```
  PUT  /tiku/paperData
```
返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [

            ]
     ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### delete

    \Home\Controller\json Home\Controller\KnowledgePointController::delete()

删除用户试卷

请求格式
```
  DELETE  /tiku/paperData
```
返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [

            ]
     ]
```

* Visibility: **public**




### getKPIdByFid

    \Home\Controller\json Home\Controller\KnowledgePointController::getKPIdByFid()

通过fid(题目ID)获取知识点id

请求格式
```
  GET  /tiku/KnowledgePoint
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result': {
             "fid(题目)id": [
                  "知识点id",
                ],
             ]
           }
     ]
```

* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseController::_initialize()

_initialize



* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)




### handleParameters

    mixed Home\Controller\CommonController::handleParameters()

处理参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### getParam

    mixed Home\Controller\CommonController::getParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### getFormParam

    mixed Home\Controller\CommonController::getFormParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### getAllParam

    mixed Home\Controller\CommonController::getAllParam()





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### getListCommonParam

    mixed Home\Controller\CommonController::getListCommonParam()

获取列表共有参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### delDirAndFile

    mixed Home\Controller\CommonController::delDirAndFile($dirName, $root)





* Visibility: **public**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $dirName **mixed**
* $root **mixed**



### __call

    mixed Home\Controller\BaseController::__call($method, $args)





* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $method **mixed**
* $args **mixed**



### display

    void Home\Controller\BaseController::display(string $templateFile, string $charset, string $contentType, string $content, string $prefix)

模板显示 调用内置的模板引擎显示方法，



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $templateFile **string** - &lt;p&gt;指定要调用的模板文件
默认为空 由系统自动定位模板文件&lt;/p&gt;
* $charset **string** - &lt;p&gt;输出编码&lt;/p&gt;
* $contentType **string** - &lt;p&gt;输出类型&lt;/p&gt;
* $content **string** - &lt;p&gt;输出内容&lt;/p&gt;
* $prefix **string** - &lt;p&gt;模板缓存前缀&lt;/p&gt;



### responseSuccess

    mixed Home\Controller\BaseController::responseSuccess($result)

请求成功响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $result **mixed**



### response

    mixed Home\Controller\BaseController::response($data, $type, $code)

响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $data **mixed**
* $type **mixed**
* $code **mixed**



### appException

    mixed Home\Controller\BaseController::appException(mixed $e)

appException



* Visibility: **public**
* This method is **static**.
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $e **mixed**



### halt

    mixed Home\Controller\BaseController::halt($error)





* Visibility: **public**
* This method is **static**.
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $error **mixed**



### _empty

    mixed Home\Controller\BaseController::_empty(String $name)





* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $name **String**


