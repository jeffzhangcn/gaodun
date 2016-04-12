Home\Controller\CommentController
===============

CommentController




* Class name: CommentController
* Namespace: Home\Controller
* Parent class: [Home\Controller\BaseController](Home-Controller-BaseController.md)







Methods
-------


### index

    mixed Home\Controller\CommentController::index()

index



* Visibility: **public**




### create

    mixed Home\Controller\CommentController::create()

create



* Visibility: **public**




### edit

    mixed Home\Controller\CommentController::edit()

edit



* Visibility: **public**




### store

    mixed Home\Controller\CommentController::store()

store



* Visibility: **public**




### detail

    mixed Home\Controller\CommentController::detail()

detail



* Visibility: **public**




### _initialize

    mixed Home\Controller\BaseController::_initialize()





* Visibility: **public**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)




### display

    void Home\Controller\BaseController::display(string $templateFile, string $charset, string $contentType, string $content, string $prefix)

模板显示 调用内置的模板引擎显示方法，



* Visibility: **protected**
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


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
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $e **mixed**



### halt

    mixed Home\Controller\BaseController::halt($error)





* Visibility: **public**
* This method is **static**.
* This method is defined by [Home\Controller\BaseController](Home-Controller-BaseController.md)


#### Arguments
* $error **mixed**


