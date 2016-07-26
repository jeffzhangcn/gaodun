Home\Controller\PaperModulePathStudentController
===============






* Class name: PaperModulePathStudentController
* Namespace: Home\Controller
* Parent class: Home\Controller\CommonController







Methods
-------


### get

    \Home\Controller\json Home\Controller\PaperModulePathStudentController::get($name)

获取必须做模块

请求格式
```
  GET  /tiku/paperModulePathStudent
```

请求参数
```
 int student_id      学生ID
 int subject_id      科目ID
 string source       APP来源,默认为'web'
 string field        查询的字段名,默认为id,student_id,project_id,subject_id,category_module_path
                     可以查询的有id,student_id,project_id,subject_id,category_module_path
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "id": "索引ID ",
             "student_id": "学生ID",
             "project_id": "项目ID",
             "subject_id": "科目ID",
             "category_module_path": "模块ID", // 字符串，以逗号分隔
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '没有数据' => 11013403,
]
```

* Visibility: **public**


#### Arguments
* $name **mixed**



### post

    \Home\Controller\json Home\Controller\PaperModulePathStudentController::post()

添加学生必做模块

请求格式
```
  GET  /tiku/paperModulePathStudent
```

请求参数
```
 int student_id      学生ID
 int project_id      项目ID
 int subject_id      科目ID
 string category_module_path  必须做的模块ID
 string source       APP来源,默认为'web'
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "id": "新添加的ID",
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '插入模块数据发生错误' => 11013404,
]
```

* Visibility: **public**




### put

    \Home\Controller\json Home\Controller\PaperModulePathStudentController::put($name)

修改学生必做模块

请求格式
```
  GET  /tiku/paperModulePathStudent
```

请求参数
```
 int student_id      学生ID
 int subject_id      科目ID
 string category_module_path  必须做的模块ID
 string source       APP来源,默认为'web'
```

返回格式
```
     [
         'status'   => '提示码',
         'info'  => '提示信息',
         'result' => [
             "flag": "1",
         ]
     ]
```

返回码说明
```
[
     '请求成功' => 00000000,
     '参数错误'=> 11000005,
     '更新模块数据发生错误' => 11013405,
]
```

* Visibility: **public**


#### Arguments
* $name **mixed**


