ApiAction
===============

* RequestVar 变量格式化类

针对设定的规则进行对应的模块中的变量进行格式化操作

- 1、根据字段与预定义变量对应关系，获取变量值
- 2、对变量进行类型转换
- 3、进行有效性判断过滤
- 4、按业务需求进行格式化
接口


* Class name: ApiAction
* Namespace: 
* Parent class: Action







Methods
-------


### __construct

    mixed ApiAction::__construct()





* Visibility: **public**




### oneToMany

    \json ApiAction::oneToMany()

获取列表页数据
```
请求格式
```
  GET  /api/list/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

]
提示码说明
```
[
     '返回成功' => 105 ,
]
```
请求参数说明
```
string date 	<all：全部 week：本周 nextWeek：下周 other：下下周以后>  							必填参数
 int    page  	<页码：不填默认为1>										   							不为必填参数
int    sid 	 	<学生id（*重要：我的预约列表此参数为必传）>				   							不为必填参数
int    istype 	<一对多必填istype = 1； 一对一必填istype = 2； （*重要：我的预约列表不传此参数）>	不为必填参数
```


返回参数说明
无参数则返回null
```
 int    id            	  直播ID
 string title         	  学生ID
 int    starttime     	  一对多开始时间（一对一无此字段）
 int    endtime      	  一对多结束时间（一对一无此字段）
 int    project_id   	  项目id
 int    subject_id    	  科目id
 int    course_id     	  课程ID
 int    teacher_id    	  老师ID
 string teachername        老师名称
 string teacher_identity   老师身份
 int    regdate            添加直播时间
 int    nownum         	  已预约人数
 int    capacity           预约总人数
 int    count              数据总数
 string pic      		  封面图
 int    status    		  预约状态：1已预约；0未预约（*重要：一对一无此参数值）
 int    type    			  区分直播：1一对一直播；0一对多直播
 string teacher_pic        老师封面
 int    oneid    		  一对一时间段id（一对多无此字段）
 int    oneStarttime       一对一开始时间段（一对多无此字段）
```

* Visibility: **public**




### timesArray

    \json ApiAction::timesArray()

一对一小班课时间段
```
请求格式
```
  GET  /api/time/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

]
提示码说明
```
[
     '返回成功' => 105 ,
]
```
请求参数说明
```
 int    liveid  	直播ID	  必填参数
```


返回参数说明
无参数则返回null
```
 int    live_id            直播ID
 int    starttime     	  开始时间
 int    endtime      	  结束时间
```

* Visibility: **public**




### questionarie

    \json ApiAction::questionarie()

预约弹框

请求格式
```
  GET  /api/ques/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
提示码说明
```
[
     '返回成功' => 105 ,
     '返回失败' => 120 ,
     '重复提交' => 111 ,
]
```
请求参数说明
```
 int    		sid  		学生ID	  		必填参数
 int    		liveid  	直播ID	  		必填参数
 string(100) title  		咨询主题	  	必填参数
 string(500) describe  	问题描述	  	必填参数
 int    		timeid  	一对一时间段id	必填参数
```

* Visibility: **public**




### teacherDetial

    \json ApiAction::teacherDetial()

老师介绍

请求格式
```
  GET  /api/teach/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
提示码说明
```
[
     '返回成功' => 105 ,
]
```
请求参数说明
```
 int    teacherID  	老师ID	  必填参数
```


返回参数说明
无参数则返回null
```
 int    	  id        老师ID
 string    name     	名称
 string    titles    职称
 string    tag      	标签
 string    desc      描述
 string    photo     图片路径
```

* Visibility: **public**




### addLive

    \json ApiAction::addLive()

开始预约

签名算法
————————
密码：cfaplan
时间戳：10位数字前8位
示例：
$pass = 'cfaplan';
$timestamp = substr(time(),0,8);
$signature = md5($pass.$timestamp.$sid.$id);
____________________________________________

请求格式
```
  GET  /api/add/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
提示码说明
```
[
     '返回成功' 						 => 105 ,
     '已存在' 						 => 100 ,
     '未登录' 						 => 104 ,
     '预约次数已达上限结束时间' 		 => 113 ,
     '超出人数限制' 					 => 112 ,
     '验证码错误' 					 => 110 ,
     '一对一预约时当前时间段已被预约' => 117 ,
     '一对一预约时未选择时间段' 		 => 116 ,
]
```
请求参数说明
```
 int     sid  		学生ID	  															必填参数
 int     id  		直播ID	  															必填参数
 int     onenums  	一对一当前用户可预约的上限次数（*重要：一对一直播时此参数为必传）	不为必填参数
 int     manynums  	一对多当前用户可预约的上限次数（*重要：一对多直播时此参数为必传）	不为必填参数
 int     timeid  	一对一时间段id（*重要：一对一直播时此参数必传）	  					不为必填参数
 string  sign  		签名验证码	  														必填参数
```

* Visibility: **public**




### delLive

    \json ApiAction::delLive()

取消预约

签名算法
————————
密码：cfaplan
时间戳：10位数字前8位
示例：
$pass = 'cfaplan';
$timestamp = substr(time(),0,8);
$signature = md5($pass.$timestamp.$sid.$id);
____________________________________________

请求格式
```
  GET  /api/del/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
提示码说明
```
[
     '返回成功' 						 => 105 ,
     '未登录' 						 => 104 ,
     '验证码错误' 					 => 110 ,
     '一对一预约时未选择时间段' 		 => 116 ,
]
```
请求参数说明
```
 int     sid  		学生ID	  															必填参数
 int     id  		直播ID	  															必填参数
 int     type  		type = 1（*重要：一对一直播时此参数必传）							不为必填参数
 int     timeid  	一对一时间段id（*重要：一对一直播时此参数必传）	  					不为必填参数
 string  sign  		签名验证码	  														必填参数
```

* Visibility: **public**




### messageList

    \json ApiAction::messageList()

消息列表

请求格式
```
  GET  /api/message/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

     ]
提示码说明
```
[
     '返回成功' 			=> 105 ,
]
```
请求参数说明
```
 int    		time  	上一次请求的时间	必填参数
 int    		sid  	学生id	  			必填参数
```

返回参数说明
无参数则返回null
```
 int    id             直播ID
 string title     	  直播名称
 int    starttime      直播开始时间
 int    isdel      	  直播是否删除
 int    type      	  一对一：1  一对多：0
 int    student_id     学生id
 int    oneStarttime   一对一被删除开始时间段
 int    110      	  一对多直播删除
 int    111      	  一对一整个直播删除
 int    112      	  一对一某个时间段删除
 int    113      	  当天直播通知：一对多
 int    114      	  当天直播通知：一对一
 int    100      	  发布通知
```

* Visibility: **public**




### getGdliveWhitelist

    \json ApiAction::getGdliveWhitelist()

小班课直播购买后，预约记录添加至白名单
```
请求格式
```
  GET  /api/white/
```
返回格式
```php
     [
          'status'   => '返回码',
          'info'  => '提示信息',
          'resut'  => []

]
提示码说明
```
[
     '返回成功' 			=> 100 ,
     '返回失败' 			=> 101 ,
     '预约人数已满' 		=> 102 ,
]
```
请求参数说明
```
 int    		liveid  直播ID		必填参数
 int    		sid  	学生ID	    必填参数
```

* Visibility: **public**



