Home\Controller\ItemController
===============






* Class name: ItemController
* Namespace: Home\Controller
* Parent class: [Home\Controller\CommonController](Home-Controller-CommonController.md)





Properties
----------


### $_requestArray

    private mixed $_requestArray = array()





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

    \Home\Controller\json Home\Controller\ItemController::getIndex()

获取题目列表

请求格式
```
  GET  /tiku/item
```
请求参数
```
  string field // 获取参数 允许的参数为：'title','option','partnum','icid','type','analysis','pid','rightnum','wrongnum','finishnum','favoritenum','isvideo','videoa','flag','rank'
  int is_need_all // 是否需要子题目,或者父题目信息即relation_item数组内容:0(不需要) 1(需要)
  string combine // 条件查询组合，可用组合[inIds](待续)
     说明：
         inIds:['in'=>'id','isdel']
  json condition //根据查询组合，给出对于组合参数
     说明：
         inIds:{"id":"17102,16617","isdel":"0"}
  string is_need_page //是否需要分页，0需要，1不需要 (默认不需要)
  int page //页数
  int offset //偏移量
  string order // 排序 (待续)
  string group //分组 (待续)
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [
             {
                 "请求内容分两种":"request_item/relation_item(请求题目/关联题目)",
                 "request_item": {
                      "title": "题目题干",
                      "option": "选项",
                      "partnum": "",
                      "icid": "知识点",
                      "type": "题目类型",
                      "analysis": "解析",
                      "pid": "上级题目号(综合题子题中有值)",
                      "rightnum": "正确数",
                      "wrongnum": "错误数",
                      "finishnum": "完成数",
                      "favoritenum": "收藏数",
                      "isvideo": "是否有视频",
                      "videoa": "视频连接",
                      "flag": "",
                      "item_id": "题目ID号"
                      "rank": "题目难度" // 1 2 3 => 难 中 易
                  },
             }
            ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
]
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\ItemController::post()

插入题目

请求格式
```
  POST  /tiku/item
```

请求参数
```

```

返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => [

     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
]
```

* Visibility: **public**




### get

    \Home\Controller\json Home\Controller\ItemController::get(string $name)

获取一道题目

请求格式
```
  GET  /tiku/item/21105
```

请求参数
```
  string field // 获取参数 允许的参数为：'title','option','partnum','icid','type','analysis','pid','rightnum','wrongnum','finishnum','favoritenum','isvideo','videoa','flag','rank'
  int is_need_all // 是否需要子题目,或者父题目信息即relation_item数组内容:0(不需要) 1(需要)
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [
                 "请求内容分两种":"request_item/relation_item(请求题目/关联题目)",
                 "request_item": {
                      "title": "题目题干",
                      "option": "选项",
                      "partnum": "",
                      "icid": "知识点",
                      "type": "题目类型",
                      "analysis": "解析",
                      "pid": "上级题目号(综合题子题中有值)",
                      "rightnum": "正确数",
                      "wrongnum": "错误数",
                      "finishnum": "完成数",
                      "favoritenum": "收藏数",
                      "isvideo": "是否有视频",
                      "videoa": "视频连接",
                      "flag": "",
                      "item_id": "题目ID号"
                      "rank": "题目难度" // 1 2 3 => 难 中 易
                  },
            ]
     ]
```

返回码说明
```
 [
     '请求成功' => '00000000'
     '错误的题目ID' => '11013101',

 ]
```

* Visibility: **public**


#### Arguments
* $name **string** - &lt;p&gt;题目ID&lt;/p&gt;



### put

    \Home\Controller\json Home\Controller\ItemController::put($name)

更新题目

请求格式
```
  PUT  /tiku/item/2949602
```

请求参数
```

```
返回格式

```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'resut'  => [

            ]
     ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### delete

    \Home\Controller\json Home\Controller\ItemController::delete()

删除题目

请求格式

```
  DELETE  /tiku/item
```

返回格式
```
     [
         'status'   => '提示码',
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




### _handleParameters

    mixed Home\Controller\CommonController::_handleParameters()

处理参数



* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




### _getParam

    mixed Home\Controller\CommonController::_getParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### _getListCommonParam

    mixed Home\Controller\CommonController::_getListCommonParam()

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



### _responseSuccess

    mixed Home\Controller\BaseController::_responseSuccess($result)

请求成功响应



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $result **mixed**



### _response

    mixed Home\Controller\BaseController::_response($data, $type, $code)

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


