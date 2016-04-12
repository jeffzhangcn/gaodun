Home\Controller\CourseRestController
===============

CourseRestController




* Class name: CourseRestController
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


### get

    mixed Home\Controller\CourseRestController::get($name)

获取课程详情

请求格式
```
  GET  /course/Home/CourseRest/11
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
          "id": "123",
          "name": "中级职称《中级会计实务》面授实景课",
          "crmname": "BJ006026",
          "crmprice": "0",
          "remark": "",
          "desc": "",
          "content": "",
          "starttime": "1338005652",
          "endtime": "1406736000",
          "price": "1000.00",
          "offerprice": "200.00",
          "offerprice_2": "0.00",
          "givepoints": "0",
          "project_id": "29",
          "subject_id": "49",
          "teacher_id": "38",
          "assitant_id": "12",
          "type_id": "1",
          "similarcourse": "",
          "video": "<script src='http://union.bokecc.com/player?vid=428FD23757D9057A9C33DC5901307461&siteid=29639E609A1142B0&autoStart=true&width=100%&height=100%&playerid=2025478528BA86BE&playertype=1' type='text/javascript'></script>\r\n",
          "freevideo": "<script src='http://union.bokecc.com/player?vid=428FD23757D9057A9C33DC5901307461&siteid=29639E609A1142B0&autoStart=true&width=100%&height=100%&playerid=2025478528BA86BE&playertype=1' type='text/javascript'></script>\r\n",
          "thumb": "Course/2013/08/22/519b1477548e3.png",
          "target": "",
          "crowd": "适合每周有固定量的学习时间，喜欢面授授课方式。",
          "playtimes": "0",
          "saleamount": "0",
          "attention": "0",
          "sortid": "999",
          "isissue": "2",
          "iscomment": "0",
          "isdel": "0",
          "istasks": "0",
          "isask": "0",
          "ismicro": "0",
          "isbig": "0",
          "courses": "",
          "courses_checked": "0",
          "classes": "60",
          "isaudition": "0",
          "cycle": "12",
          "warecount": "0",
          "incnum": "0",
          "incupdate": "0",
          "rating": "100",
          "studentsnum": "4540",
          "newguide": "<div id=\"xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd\">\r\n</div>",
          "courseinfo": "<div id=\"xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd\">\r\n</div>",
          "tasklook": "<div id=\"xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd\">\r\n</div>",
          "cd_thumb": null,
          "close_date": "-28800",
          "bbs_class": null,
          "show": "0",
          "chatflg": "0",
          "task_notice": "<div id=\"xunlei_com_thunder_helper_plugin_d462f475-c18e-46be-bd10-327458d045bd\">\r\n</div>",
          "task_describe": "",
          "isopen": "0",
          "expiration_date": "0",
          "appoint_type": "0",
          "is_expiration": "1",
          "isenableyh": "1",
          "isusedetail": "0",
          "sibigshowsmall": "0",
          "isrelationcpe": "0",
          "recommendcourse": "",
          "update_big_courses": "",
          "signup_url": "",
          "gradequery_url": "",
          "isupdatepacket": "0",
          "app_thumb": "Course/2013/08/22/app_519b1477548e3.png",
          "app_price": "800.00",
          "isapp": "0",
          "word_thumb": "",
          "isagreement": "0",
          "isenablecz": "1",
          "isagreeement": "0",
          "course_rel": "0",
          "is_ios_view": "0",
          "is_ios_buy": "0",
          "is_post": "0",
          "type_textbook": "0",
          "accounting_id": "0",
          "care_answer_time": "0"
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


