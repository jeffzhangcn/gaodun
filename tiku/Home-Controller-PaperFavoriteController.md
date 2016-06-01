Home\Controller\PaperFavoriteController
===============






* Class name: PaperFavoriteController
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

    mixed Home\Controller\PaperFavoriteController::getIndex()

获取题目收藏列表

请求格式
```
  GET  /tiku/paperFavorite
```

```
请求参数
```
 string combine // 条件查询组合，可用组合[sps](待续)
     说明：
         sps:['student_id','project_id','subject_id'] // 不支持分页，is_need_page为0
 json condition //根据查询组合，给出对于组合参数
     说明：
         sps:{"student_id":1,"project_id":1,"subject_id":1}
 string is_need_page //是否需要分页，0需要，1不需要 (默认不需要)
 int page //页数
 int offset //偏移量
 string order // 排序 (待续)
 string group //分组 (待续)
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "item_id": "1,2" // sps
         ]

     ]
```

* Visibility: **public**




### post

    array Home\Controller\PaperFavoriteController::post()

插入用户题目收藏

请求格式
```
  POST  /tiku/paperFavorite
```

返回格式
```php
     [
          'status'   => '提示码',
          'info'  => '提示信息'
     ]

```
错误码说明
```
[
     '请求成功' => 00000000,
     '批量收藏题目失败,无数据' => 11013102,
     '收藏失败'=> 11013103
]

```
请求参数
```
 int item_id          题目ID
 string source        来源
 int paper_id        试卷ID
 int student_id    学生ID
 int project_id    项目ID
 int subject_id    科目ID
 string pattern 一个或者多个  枚举：one|mult
 json mult_data 批量收藏或者取消 暂时未支持
      [
         {"item_id":"99340","paper_id":2112,"type":"2","project_id":"5","subject_id":"29"}
      ]

```

* Visibility: **public**




### get

    array Home\Controller\PaperFavoriteController::get(string $name)

获取一题目收藏

请求格式
```
  GET  /tiku/paperFavorite/1
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
* $name **string** - &lt;p&gt;用户题目收藏ID&lt;/p&gt;



### put

    mixed Home\Controller\PaperFavoriteController::put($name)

更新用户题目收藏

请求格式
```
  PUT  /tiku/paperFavorite
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

    mixed Home\Controller\PaperFavoriteController::delete()

取消用户题目收藏

请求格式
```
  DELETE  /tiku/paperFavorite
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息'
     ]
```

错误码说明
```
[
     '请求成功' => 00000000,
     '未收藏,无法取消' => 11013104,
     '取消收藏失败'=> 11013105
]
```

请求参数
```
 int     item_id          题目ID
 int     paper_id         试卷ID
 int     student_id       学生ID
 int     project_id       项目ID
 int     subject_id       科目ID
 string  source           来源
 string  pattern          一个或者多个  枚举：one|mult
 json mult_data 批量收藏或者取消 暂时未支持
      [
         {"item_id":"99340","paper_id":2112,"type":"2","project_id":"5","subject_id":"29"}
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



### _getFormParam

    mixed Home\Controller\CommonController::_getFormParam($name, $default)





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)


#### Arguments
* $name **mixed**
* $default **mixed**



### getAllParam

    mixed Home\Controller\CommonController::getAllParam()





* Visibility: **protected**
* This method is defined by [Home\Controller\CommonController](Home-Controller-CommonController.md)




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


