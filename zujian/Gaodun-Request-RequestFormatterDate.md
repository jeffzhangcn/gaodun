Gaodun\Request\RequestFormatterDate
===============

RequestFormatterDate 格式化日期

- 提供基本的公共功能，便于子类重用


* Class name: RequestFormatterDate
* Namespace: Gaodun\Request
* Parent class: [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)
* This class implements: [Gaodun\Request\RequestFormatter](Gaodun-Request-RequestFormatter.md)






Methods
-------


### parse

    \Gaodun\Request\格式化的值 Gaodun\Request\RequestFormatter::parse(mixed $value, mixed $rule)

parse 要格式化的方法



* Visibility: **public**
* This method is defined by [Gaodun\Request\RequestFormatter](Gaodun-Request-RequestFormatter.md)


#### Arguments
* $value **mixed** - &lt;p&gt;值&lt;/p&gt;
* $rule **mixed** - &lt;p&gt;规则&lt;/p&gt;



### filterByRange

    mixed Gaodun\Request\RequestFormatterBase::filterByRange(mixed $value, mixed $rule)

根据min，max范围进行控制，
执行三个方法，
1.判断规则
2.检测最小
3.检测最大



* Visibility: **protected**
* This method is defined by [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)


#### Arguments
* $value **mixed** - &lt;p&gt;值&lt;/p&gt;
* $rule **mixed** - &lt;p&gt;规则&lt;/p&gt;



### filterRangeMinLessThanOrEqualsMax

    mixed Gaodun\Request\RequestFormatterBase::filterRangeMinLessThanOrEqualsMax($rule)





* Visibility: **protected**
* This method is defined by [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)


#### Arguments
* $rule **mixed**



### filterRangeCheckMin

    mixed Gaodun\Request\RequestFormatterBase::filterRangeCheckMin($value, $rule)





* Visibility: **protected**
* This method is defined by [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)


#### Arguments
* $value **mixed**
* $rule **mixed**



### filterRangeCheckMax

    mixed Gaodun\Request\RequestFormatterBase::filterRangeCheckMax($value, $rule)





* Visibility: **protected**
* This method is defined by [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)


#### Arguments
* $value **mixed**
* $rule **mixed**



### formatEnumValue

    mixed Gaodun\Request\RequestFormatterBase::formatEnumValue(string $value, array $rule)

格式化枚举类型



* Visibility: **protected**
* This method is defined by [Gaodun\Request\RequestFormatterBase](Gaodun-Request-RequestFormatterBase.md)


#### Arguments
* $value **string** - &lt;p&gt;变量值&lt;/p&gt;
* $rule **array** - &lt;p&gt;array(&#039;name&#039; =&gt; &#039;&#039;, &#039;type&#039; =&gt; &#039;enum&#039;, &#039;default&#039; =&gt; &#039;&#039;, &#039;range&#039; =&gt; array(...))&lt;/p&gt;


