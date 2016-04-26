Home\Controller\SyllabusKnowledgeRestController
===============

SyllabusKnowledgeRestController




* Class name: SyllabusKnowledgeRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


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


### get

    mixed Home\Controller\SyllabusKnowledgeRestController::get($name)

获取大纲详情

请求格式
```
  GET  /course/Home/SyllabusKnowledgeRest/11
 header [
   Accept: application/json
   App-Id-Key: gd_course_epiphany
   App-Timestamp:  1460697000
   App-Nonce: 3Rg5UE3OxO
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
[
    'err_no'   => '', //错误代码
    'err_msg'  => '', //错误信息
    'resut'  => {
       "id": "2562",
       "kid": "0",
       "project_id": "5",
       "subject_id": "28",
       "title": "账务处理程序",
       "sid": "",
       "pid": "0",
       "regdate": "1457524776",
       "modifydate": "1457524776",
       "isdel": "0",
       "difficulty": "",
       "score": "",
       "question_num": "0",
       "testrate": "",
       "level": "0",
       "question_type": null
       }
     ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



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


