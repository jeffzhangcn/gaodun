Home\Controller\BaseController
===============






* Class name: BaseController
* Namespace: Home\Controller
* Parent class: Think\Controller







Methods
-------


### _initialize

    mixed Home\Controller\BaseController::_initialize()





* Visibility: **public**




### display

    void Home\Controller\BaseController::display(string $templateFile, string $charset, string $contentType, string $content, string $prefix)

模板显示 调用内置的模板引擎显示方法，



* Visibility: **protected**


#### Arguments
* $templateFile **string** - &lt;p&gt;指定要调用的模板文件
默认为空 由系统自动定位模板文件&lt;/p&gt;
* $charset **string** - &lt;p&gt;输出编码&lt;/p&gt;
* $contentType **string** - &lt;p&gt;输出类型&lt;/p&gt;
* $content **string** - &lt;p&gt;输出内容&lt;/p&gt;
* $prefix **string** - &lt;p&gt;模板缓存前缀&lt;/p&gt;



### appException

    mixed Home\Controller\BaseController::appException(mixed $e)

appException



* Visibility: **public**
* This method is **static**.


#### Arguments
* $e **mixed**



### halt

    mixed Home\Controller\BaseController::halt($error)





* Visibility: **public**
* This method is **static**.


#### Arguments
* $error **mixed**


