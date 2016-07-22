Home\Controller\ItemCategoryController
===============






* Class name: ItemCategoryController
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

    \Home\Controller\json Home\Controller\ItemCategoryController::getIndex()

获取知识点列表

请求格式
```
  GET  /tiku/ItemCategory
```

请求参数
```
string project_id //项目ID
string subject_id //科目ID
string picid //
string type //类型：枚举【'all','one','another'】 all是全部,one是拿一层的与picid连用,another是根据传的picid知识点下的所有层知识点
int allow_status //拿知识点状态为0，1，2，3，4，5,默认为0,2,3,4,5 =》说明：0免费启用、1禁用、2购买任意课程启用、3购买指定课程启用、4同时购买多门指定课程启用、5与上级权限一致
int is_high_error //是否拿高频错题。默认false.|boolean
```

返回格式
```
     [
         'status'   => '返回码',
         'info'  => '提示信息',
         'result' => [
             {
                 "icid": "知识点ID",
                 "title": "知识点名称",
                 "pid": "父知识点ID",
                 "path": "路径", // _0_2760
                 "level": "层级",
                 "num": "题目数量",
                 "status": "状态", // 与请求参数allow_status一致
                 "ishigherror": "是否为高频错题", // 与请求参数is_high_error一致
                 "openhigherror": "是否开启高频错题做题",
                 "exam_rate": "考试比例",
                 "childlist": [ // 子知识点，数据结构与以上一致
                     {
                         "icid": "知识点ID",
                         "title": "知识点名称",
                         "pid": "父知识点ID",
                         "path": "路径", // _0_2760
                         "level": "层级",
                         "num": "题目数量",
                         "status": "状态", // 与请求参数allow_status一致
                         "ishigherror": "是否为高频错题", // 与请求参数is_high_error一致
                         "openhigherror": "是否开启高频错题做题",
                         "exam_rate": "考试比例",
                         "childlist": [ // 无限级分类
                                 ]
                             }
                         ]
                     }
                 ]
            }
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 0x11013301
]
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\ItemCategoryController::post()

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
 string $type_flag    point 根据知识点创建，paper根据试卷id创建
 int $student_id      学生ID
 string $source       来源
 ---------by 【paper】--------------
 int $paper_id        试卷ID（母卷）
 ---------by 【point】--------------
 string $etype        试卷类型1智能，2知识点，3真题，4组卷
 string $projectId    项目id
 string $subjectId    科目id
 string $icids        知识点集合
 string $num          选题总数
 string $type         0新题目，1已做题目
 string $items_type   0随机，1单选，2多选，3判断题，4简答题，5综合
 string $rank         难易度
 string $mark         标识存储过程的执行（与效率有关）
 string $pid          试卷id
 string $from         来源  1favorite，2error
 string $source       APP来源
 string $sessionId    sessionId
 string $liveType     0正常生成题目， 1实时解析
```

* Visibility: **public**




### get

    array Home\Controller\ItemCategoryController::get(string $name)

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

    \Home\Controller\json Home\Controller\ItemCategoryController::put($name)

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

    \Home\Controller\json Home\Controller\ItemCategoryController::delete()

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


