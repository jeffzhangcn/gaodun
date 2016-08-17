Home\Controller\PaperController
===============






* Class name: PaperController
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

    \Home\Controller\json Home\Controller\PaperController::getIndex()

获取试卷列表

请求格式
```
GET /tiku/paper
```

请求参数
```
string combine // 条件查询组合，可用组合[se,sey](待续)
       说明：
       se:['subject_id','etype']
       sey:['subject_id','etype','year']
json   condition  //根据查询组合，给出对于组合参数
       说明：
       {"subject_id":28,"etype":1} => se
       {"subject_id":28,"etype":1,"year":2015} => sey
string field //获取字段：id,title,subject_id,etype,status,source,score,passscore,takes
string student_id //学生ID，如果传学生ID，将返回该学生答试卷信息，默认-1
string is_need_other_attribute //是否需要其他属性，试卷的最高分，答题人数，平均分
string is_need_page //是否需要分页，y需要，n不需要 (默认不需要)
string source 来源，如果是app的必传
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
            "id": "3434", // 试卷ID
            "title": "会计基础真题试卷一（2015真题）", // 试卷标题
            "subject_id": "28", // 科目ID
            "etype": "1", // 试卷类型：1、真题 2、模拟组考 3、小测 4、模拟机考 5、收费试卷 6、密卷-用于收费试卷 7、学前测试 8、必做题 9、学前路径测试
            "status": "0",// 试卷状态
            "source": "高顿网校", // 来源
            "score": "100", // 总分
            "passscore": "60", // 及格分
            "takes": "60", // 答题时间
            "pdid": "2950369", // 学生生成试卷ID
            "isexam": "0", // 学生答题状态：999：未开始，0：为答完，1：作答完成
            "student_score": "0", // 学生得分
            "student_regdate": "1463648074", // 学生试卷生成时间
            "student_modifydate": "1463648074", // 学生交卷试卷
            "num": "4", // 做卷子学员数
            "average": 7, // 平均分
            "highest_score": "20" // 最高分
        }
    ]
}
```

* Visibility: **public**




### post

    \Home\Controller\json Home\Controller\PaperController::post()

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

    array Home\Controller\PaperController::get(string $name)

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

    \Home\Controller\json Home\Controller\PaperController::put($name)

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

    \Home\Controller\json Home\Controller\PaperController::delete()

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


