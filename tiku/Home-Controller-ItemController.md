Home\Controller\ItemController
===============






* Class name: ItemController
* Namespace: Home\Controller
* Parent class: Home\Controller\CommonController







Methods
-------


### getIndex

    mixed Home\Controller\ItemController::getIndex()

获取题目列表

请求格式
```
  GET  /tiku/item
```
返回格式
```php
     [
          'status'   => '提示码',
          'info'  => '提示信息',
          'resut'  => [

     ]
```

* Visibility: **public**




### post

    array Home\Controller\ItemController::post()

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
          'status'   => '', //提示码
          'info'  => '', //提示信息
          'resut'  => [

     ]
```
错误码说明
```
[
     '请求成功' => 11000000,
     '参数错误'=> 11000002,
     '数据错误' => 11013001,
     '试卷无权限' => 11013002,
     '生成试卷失败' => 11013003,
     '生成试卷失败' => 11013004,
]
```

* Visibility: **public**




### get

    array Home\Controller\ItemController::get(string $name)

获取一道题目

请求格式
```
  GET  /tiku/item/21105
```
请求参数
```
  string field // 获取参数
  int is_need_all // 是否需要子题目,或者父题目信息
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
                  },
            ]
     ]
```
返回码说明
```
 [
     '请求成功' => '11000000'
     '错误的题目ID' => '11013101',

 ]
```

* Visibility: **public**


#### Arguments
* $name **string** - &lt;p&gt;题目ID&lt;/p&gt;



### put

    mixed Home\Controller\ItemController::put($name)

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
         'status'   => '', //提示码
         'info'  => '', //提示信息
         'resut'  => [

            ]
     ]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### delete

    mixed Home\Controller\ItemController::delete()

删除题目

请求格式
```
  DELETE  /tiku/item
```
返回格式
```
     [
         'status'   => '', //提示码
         'info'  => '', //提示信息
         'resut'  => [

            ]
     ]
```

* Visibility: **public**



