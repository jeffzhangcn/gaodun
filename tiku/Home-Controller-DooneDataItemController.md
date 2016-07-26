Home\Controller\DooneDataItemController
===============






* Class name: DooneDataItemController
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

    \Home\Controller\json Home\Controller\DooneDataItemController::getIndex()

获取已做题目列表

请求格式
```
GET /tiku/paper
```

请求参数
```
string combine // 条件查询组合，可用组合[sii](待续)
       说明：
       sii:['subject_id','icid','is_done']
json   condition  //根据查询组合，给出对于组合参数
       说明：
       {"student_id":1695081,"icid":2760,"is_done":1} => sii
string field //获取字段：id,student_id,project_id,subject_id,icid,itempid,item_id,item_type,userAnswer,userScore,done_num,right_num,error_num,item_sort,istrue,is_done,attribute
string source 来源，如果是app的必传

以下待续：
int page //页数
int offset //偏移量
string order // 排序 默认：sortid
string group //分组 (待续)
```

返回格式
```
{
    'status'   => '返回码',
    'info'  => '提示信息',
    'result': [
         {
             "id": "id",
             "student_id": "学生ID",
             "project_id": "项目ID",
             "subject_id": "科目ID",
             "icid": "知识点ID",
             "itempid": "题目父ID",
             "item_id": "题目ID",
             "item_type": "题目类型",
             "useranswer": "用户答案",
             "userscore": "得分",
             "done_num": "答题次数",
             "right_num": "正确次数",
             "error_num": "错误次数",
             "item_sort": "题目排序",
             "istrue": "是否正确", 0未做，1正确，2错误，4不判断
             "is_done": "是否做过",
             "attribute": "经典题为1"
         },
    ]
}
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\DooneDataItemController::post()

插入试卷

请求格式
```
  POST  /tiku/paper
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

    array Home\Controller\DooneDataItemController::get(string $name)

获取一张试卷

请求格式
```
  GET  /tiku/paper/1
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

    \Home\Controller\json Home\Controller\DooneDataItemController::put($name)

更新试卷

请求格式
```
  PUT  /tiku/paper
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

    \Home\Controller\json Home\Controller\DooneDataItemController::delete()

删除试卷

请求格式
```
  DELETE  /tiku/paper
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




### getUserDoNumByIcids

    \Home\Controller\json Home\Controller\DooneDataItemController::getUserDoNumByIcids()

得到用户一题题做某些知识点下的做题数量

请求格式
```
  GET  /tiku/DooneDataItem/getUserDoNumByIcids
```

请求参数
```
json icids  知识点ID [2760,2769]
string student_id  学生ID
int icids_is_subjectId  icids参数是否为科目ID，默认0，如果是有传project_id参数
int project_id  科目ID
string allow_status //拿知识点状态为0，1，2，3，4，5,默认为0,2,3,4,5 =》说明：0免费启用、1禁用、2购买任意课程启用、3购买指定课程启用、4同时购买多门指定课程启用、5与上级权限一致
boolean is_high_error //是否拿高频错题。默认false.|boolean
string source 来源，如果是app的必传
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'resut'  => [
                 "2760": "8", // 请求的知识点ID ：该知识点点下做题数量
            ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误' => 11000001
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


