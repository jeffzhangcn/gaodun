Home\Controller\PaperModulePathController
===============






* Class name: PaperModulePathController
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

    \Home\Controller\json Home\Controller\PaperModulePathController::getIndex()

获取必须做模块列表

请求格式
```
  GET  /tiku/paperModulePath
```

请求参数
```
 int paper_id        试卷ID
 string is_need_page 是否需要分页，'y'为需要,'n'为不需要
 int page            第几页，默认为1
 int offset          每页记录条数，默认为10，最大为25条
 string order        例如：'id desc'
 string source       APP来源,默认为'web'
 string field        查询的字段名,默认为id,paper_id,answer,category_module,subject_id,project_id
                     可以查询的有id,paper_id,answer,category_module,subject_id,project_id
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "id": "必须做模块ID ",
             "paper_id": "试卷ID",
             "answer": "答案", // 字符串，以逗号分隔
             "category_module": "必须做模块ID", // 字符串，以逗号分隔
             "subject_id": "科目ID",
             "project_id": "项目ID"
         ]

     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '没有数据' => 11013501,
     '没有更多数据' => 11013502,
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


