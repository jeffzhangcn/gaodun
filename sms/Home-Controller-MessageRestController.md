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
  POST http://test.sms.base.gaodun.com/Home/MessageRest
   [
      phone => '18720085054', //多个手机号用,分隔
      app_id=> 'gd_course' //发送来源,
      msg => 发送的内容,
      channel_id => 3  发送渠道 默认3亿美 1阿里大鱼 2希奥 4益客 5发送猫
      type  => '0',//用于阿里大鱼发送,来选择不同模板与签名1为注册验证2为身份验证阿里大鱼需要传递签名以及
                   //短信模板ID，传入的模板必须是在阿里大鱼“管理中心-短信模板管理”中的可用模板。
                   //注册验证模板:验证码${code}，您正在注册成为${product}用户，感谢您的支持！
                   //身份验证模板:验证码${code}，您正在进行${product}身份验证，打死不要告诉别人哦！
                   //msg 参数为json数据:传参时需传入{"code":"1234","product":"高顿网校"};
      ip=>127.0.0.1  //客户端ip
      agent => '' // 客户端UA HTTP_USER_AGENT
   ]
 header [
   Accept: application/json
   App-Id-Key: gd_send_sms
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


