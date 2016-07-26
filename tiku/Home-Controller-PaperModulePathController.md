Home\Controller\PaperModulePathController
===============






* Class name: PaperModulePathController
* Namespace: Home\Controller
* Parent class: Home\Controller\CommonController







Methods
-------


### getIndex

    \Home\Controller\json Home\Controller\PaperModulePathController::getIndex()

获取必须做模块列表

请求格式
```
  GET  /tiku/paperModulePath
```

请求参数
```
 int paper_id        试卷ID
 string is_need_page 是否需要分页，'y'为需要,'n'为不需要
 int page            第几页，默认为1
 int offset          每页记录条数，默认为10，最大为25条
 string order        例如：'id desc'
 string source       APP来源,默认为'web'
 string field        查询的字段名,默认为id,paper_id,answer,category_module,subject_id,project_id
                     可以查询的有id,paper_id,answer,category_module,subject_id,project_id
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "id": "必须做模块ID ",
             "paper_id": "试卷ID",
             "answer": "答案", // 字符串，以逗号分隔
             "category_module": "必须做模块ID", // 字符串，以逗号分隔
             "subject_id": "科目ID",
             "project_id": "项目ID"
         ]

     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '没有数据' => 11013401,
     '没有更多数据' => 11013402,
]
```

* Visibility: **public**



