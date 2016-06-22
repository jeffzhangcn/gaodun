Home\Controller\MessageRestController
===============






* Class name: MessageRestController
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


### post

    mixed Home\Controller\MessageRestController::post()

发送短信

请求格式
```
  POST /sms/Home/MessageRest
   [
      phone => '18720085054', //多个手机号用,分隔
      app_id=> 'gd_course' //发送来源,
      msg => 发送的内容,
      channel = > 0  发送渠道 默认为亿美
      type  => '1',
      ip=>127.0.0.1  //客户端ip
      agent => '' // 客户端UA HTTP_USER_AGENT
   ]
 header [
   Accept: application/json
   App-Id-Key: gd_demo_abcdef
   App-Timestamp: 212121
   App-Nonce: eewewew
   App-Signature: babc722817e366cf62f883e2b61532505c674920a
 ]
```
返回格式
```
     [
         'status'   => '', //错误代码
         'info'  => '', //错误信息
         'result'  => 1, // å
     ]
```

* Visibility: **public**




### getIndex

    mixed Home\Controller\MessageRestController::getIndex()





* Visibility: **public**




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


