Home\Controller\CommentRestController
===============

CommentRestController




* Class name: CommentRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


### $allowMethod

    protected string $allowMethod = array('get', 'post', 'put')

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


### get_index

    mixed Home\Controller\CommentRestController::get_index()

获取评论列表

请求格式
```
  GET  /Home/CommentRest
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
         'err_no'   => '', //错误代码
         'err_msg'  => '', //错误信息
         'resut'  => [
           num=>10,
           comments=>[
               [
                 id'          => "1", //评论ID
                 title'       => "1212121", 评论标题
                 comment'     => "212121", //评论内容
                 user_id'     => "0",      //发表评论者
                 create_time' => "0",      //评论时间
                 update_time' => "0"       // 修改时间
               ],
             ]
            ]
]
     ]
```

* Visibility: **public**




### post

    mixed Home\Controller\CommentRestController::post()

发表评论

请求格式
```
  POST /Home/CommentRest
   [
      title => 'lalalala',
      comment  => 'lalalala',
   ]
 header [
   Accept: application/json
 ]
```
返回格式
```
     [
         'status'   => '', //错误代码
         'info'  => '', //错误信息
         'result'  => 1, // 评论ID
     ]
```

* Visibility: **public**




### get

    mixed Home\Controller\CommentRestController::get($name)

获取评论详情

请求格式
```
  GET  /Home/CommentRest/11
 header [
   Accept: application/json
 ]
```
返回格式
```
     [
         'err_no'   => '', //错误代码
         'err_msg'  => '', //错误信息
         'resut'  => [
             id'          => "1", //评论ID
             title'       => "1212121", 评论标题
             comment'     => "212121", //评论内容
             user_id'     => "0",      //发表评论者
             create_time' => "0",      //评论时间
             update_time' => "0"       // 修改时间
             }
]
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


