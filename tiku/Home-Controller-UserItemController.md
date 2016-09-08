Home\Controller\UserItemController
===============

用户相关题目




* Class name: UserItemController
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


### post

    \Home\Controller\json Home\Controller\UserItemController::post()

判断用户答题是否正确

请求格式
```
  PUT  /tiku/userItem
```

请求参数
```
 int student_id 学生ID
 int project_id 项目ID
 int subject_id 科目ID
 string source       来源
 json ualist {"337182":"1","91704":"1","89870":"A"},题目ID为键，用户答案值,
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'resut'  => [
                  "89870": 1,
                     // 题目id：是否正确 (0:未做，1:正确，2:错误，3:半对，4:填空不判断)
                  "91704": 2,
                  "337182": 1
            ]
     ]
```

* Visibility: **public**




### getIndex

    \Home\Controller\json Home\Controller\UserItemController::getIndex()

判断用户答题是否正确

请求格式
```
  PUT  /tiku/userItem
```

请求参数
```
 int student_id 学生ID
 int project_id 项目ID
 int subject_id 科目ID
 string items 题目id，用逗号分割
 string source       来源
 string need_attr 需要的其他属性 可选favorite,notenum,knowledge_point_tag
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'resut'  => [
                  'favoriteList'=>[
                     "38182" // 该项目科目下收藏的题目id
                  ],
                  "noteNumList": [
                     "题目ID":"笔记数量"
                  ],
                  "knowledgePointList":{
                     "370458": {
                          {
                              "fid": "题目id",
                              "knowledge_id": "知识点id",
                              "title": "名称",
                              "definition": '定义'
                          }
                     ]
                  }
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


