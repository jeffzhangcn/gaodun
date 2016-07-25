Home\Controller\CategoryModuleController
===============






* Class name: CategoryModuleController
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

    \Home\Controller\json Home\Controller\CategoryModuleController::getIndex()

获取前端组卷模块列表

请求格式
```
  GET  /tiku/CategoryModule
```

请求参数
```
string combine // 条件查询组合，可用组合[subjectId](待续)
       说明：
       subjectId:['subject_id']
json   condition  //根据查询组合，给出对于组合参数
       说明：
       {"subject_id":28} => subjectId
string source 来源，如果是app的必传
string whereshow 显示在哪 [1,2] // 1是pc，2是app，默认1
string order 排序 desc和asc 默认desc
string source 来源，如果是app的必传
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result': [
             {
                 "title": "模块名称",
                 "project_id": "项目ID",
                 "subject_id": "科目ID",
                 "icid": "知识点ID",
                 "sortid": "排序",
                 "isshowpc": "是否显示在PC端", // 1显示
                 "isshowapp": "是否显示在APP端" // 1显示
             }
         ]

     ]
```

* 提示码说明
```
[
     '请求成功' => 00000000,
]
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\CategoryModuleController::post()

插入用户试卷

请求格式
```
  POST  /tiku/paperData
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
```
提示码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000002,
     '数据错误' => 11013001,
     '试卷无权限' => 11013002,
     '生成试卷失败' => 11013003,
     '生成试卷失败' => 11013004,
]
```
请求参数
```
```

* Visibility: **public**




### get

    array Home\Controller\CategoryModuleController::get(string $name)

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

    \Home\Controller\json Home\Controller\CategoryModuleController::put($name)

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

    \Home\Controller\json Home\Controller\CategoryModuleController::delete()

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


