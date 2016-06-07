Gaodun\Request\ExceptionCode
===============

ExceptionCode 异常处理类




* Class name: ExceptionCode
* Namespace: Gaodun\Request





Properties
----------


### $_allConstant

    private array $_allConstant = array('NoThisConst' => 285212673, 'MustRequired' => 285212674, 'MustInstanceof' => 285212675, 'MinGTMax' => 285212676, 'MinGTValue' => 285212677, 'MaxLTValue' => 285212678, 'NotBetween' => 285212679, 'RegexNotMatch' => 285212680, 'NoFunctionCallback' => 285212681, 'ThePathNoCallback' => 285212688, 'ThisNoCallback' => 285212689, 'MissRange' => 285212690, 'RangeEmpty' => 285212691, 'NoUploadFile' => 285212692, 'UploadFileError' => 285212693, 'FileExtError' => 285212694, 'NotSafeParam' => 285212695, 'NeedCoverButYouNot' => 285212696, 'JsonNotMatch' => 285212697)

$_allConstant 定义的异常常量参数code



* Visibility: **private**
* This property is **static**.


### $_allConstantMessage

    private array $_allConstantMessage = array('NoThisConst' => '常量不存在', 'MustRequired' => '参数为必填', 'MustInstanceof' => '必须继承方法', 'MinGTMax' => '最小值大于最大值', 'MinGTValue' => '最小值大于验证值', 'MaxLTValue' => '最大值小于验证值', 'NotBetween' => '超出给定范围', 'RegexNotMatch' => '正则不匹配', 'NoFunctionCallback' => '没有设置参数callback', 'ThePathNoCallback' => '提供的地址没有找到方法', 'ThisNoCallback' => '当前类中没有没有找到方法', 'MissRange' => '缺少range参数', 'RangeEmpty' => 'enum中range参数为空', 'NoUploadFile' => '没有上传文件', 'UploadFileError' => '上传文件失败', 'FileExtError' => '错误的文件后缀', 'NotSafeParam' => '此参数为不安全，未验证参数', 'NeedCoverButYouNot' => '需要覆盖rules方法，你没有', 'JsonNotMatch' => '格式不对，不是json格式')

$_allConstantMessage 中文解释



* Visibility: **private**
* This property is **static**.


Methods
-------


### getConstant

    integer Gaodun\Request\ExceptionCode::getConstant(string $key)

获取错误码的常量值



* Visibility: **public**
* This method is **static**.


#### Arguments
* $key **string** - &lt;p&gt;错误码英文名&lt;/p&gt;



### getMessage

    string Gaodun\Request\ExceptionCode::getMessage(string $key)

获取错误码的中文解释



* Visibility: **public**
* This method is **static**.


#### Arguments
* $key **string** - &lt;p&gt;错误码英文名&lt;/p&gt;


