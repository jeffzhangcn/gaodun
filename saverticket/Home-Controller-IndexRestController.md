Home\Controller\IndexRestController
===============






* Class name: IndexRestController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)





Properties
----------


### $ticketlogic

    public mixed $ticketlogic





* Visibility: **public**


### $requestArray

    public mixed $requestArray





* Visibility: **public**


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


### __construct

    mixed Home\Controller\BaseRestController::__construct()





* Visibility: **public**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)




### obtainByAid

    mixed Home\Controller\IndexRestController::obtainByAid()

按活动领取所有优惠券

请求格式

Post /saverticket/home/obtainbyAid

参数 [
     aid:1//活动id
     sid:1//学生id
]

返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息
     result    => [
         {
             bid:1
             pic:""
             starttime:2016年9月27日
             endtime:2016年9月28日
         },{...}
     ]
]

* Visibility: **public**




### getByAid

    mixed Home\Controller\IndexRestController::getByAid()

按活动获取活动下优惠券批次信息

请求格式

Post /saverticket/home/getbyAid

参数 [
     aid:1//活动id

]

返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息
     result    => [
         {
             "id": "1",
             "batchname": "红包1",
             "activityid": "1",
             "pic": "/Uploads/Saverticket/2016/09/06/57ce6b403456b.png",
             "usescope": "0",
             "yhlimit": "0.00",
             "yhmoney": "30.00",
             "passday": "7",
             "ruletext": "使用规则1"
         },{...}
     ]
]

* Visibility: **public**




### obtainByBid

    mixed Home\Controller\IndexRestController::obtainByBid()

按批次领取优惠券

请求格式

Post /saverticket/home/obtainbyBid

参数 [
     aid:1//活动id
     sid:1//学生id
]

返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息
     result    => [
             bid:1
             pic:""
             starttime:2016年9月27日
             endtime:2016年9月28日
     ]
]

* Visibility: **public**




### checkCompute

    mixed Home\Controller\IndexRestController::checkCompute()

检查并计算优惠券使用情况

请求格式

Post /saverticket/home/checkcompute

参数 [
    code:Y0ijsj//优惠券code
    cid:1//课程id

]


返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息
     result    => [
             yhmoney:1//优惠金额
     ]
]

* Visibility: **public**




### freezeTicket

    mixed Home\Controller\IndexRestController::freezeTicket()

冻结优惠券

请求格式

Post /saverticket/home/freeze

参数 [
    code:1sfjk//优惠券码
    oid:1//订单id
    sid:1//学生id
    paymoney:100
    deduction:5
]


返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息

]

* Visibility: **public**




### useTicket

    mixed Home\Controller\IndexRestController::useTicket()

使用冻结的优惠券

请求格式

Post /saverticket/home/use

参数 [
    oid:1//订单id
]


返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息

]

* Visibility: **public**




### unfreezeTicket

    mixed Home\Controller\IndexRestController::unfreezeTicket()

解冻优惠券

请求格式

Post /saverticket/home/unfreeze

参数 [
    oid:1//订单id 整数可以逗号隔开
]


返回格式

[
     status    => 0,//错误代码
     info      => '',//错误信息

]

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



### handleParameters

    mixed Home\Controller\BaseRestController::handleParameters()

处理参数



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseRestController](Home-Controller-BaseRestController.md)



