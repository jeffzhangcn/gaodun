## 功能
> 结合自适应学习推出一门ACCA新课程，即根据学生的学习情况推荐相关的学习资源

## 性能

## 软件与硬件
> 采用lnmp架构，代码部署到阿里云ECS上

## 设计思路

* 为了方便静态资源部署到cdn上，动静态代码分开部署
* 为了提高开发效率 前后端分离开发，后端支持查看json格式数据 方便和前端联调
* 99%的代码采用PHP编写，编码规范采用PHP官方推荐标准PSR2
* PHP 模块间依赖采用composer进行管理
* 为了避免浏览器缓存和传输静态资源过大，浪费不必要的带宽， 静态资源压缩和版本使用gulp
* 对http服务调用采用guzzlehttp组件，同时对该组件进行封装，和改造适合高顿自己模式

## 系统架构
   
## 主要流程

>> 课程首页 -> 章节结构 (-> 跳级测试)? -> 章节复习 (-> 知识点学习)? -> 章节复习-> 章节测试-> 提分盒子

>> 我的习题 

>> 我的笔记

## 代码结构
   
#### 前端代码结构
###### 模板 
   
   > 路径 gaodun.com/template/epipahny
   
   > 结构

   ```
    .
    ├── build
    │   ├── Answer
    │   ├── Chapter
    │   ├── Comment
    │   ├── Course
    │   ├── Error
    │   ├── Game
    │   ├── Layout
    │   ├── Note
    │   ├── PaperItem
    │   └── Section
    └── src
        ├── Answer
        ├── Chapter
        ├── Comment
        ├── Course
        ├── Error
        ├── Game
        ├── Layout
        ├── Note
        ├── PaperItem
        └── Section

  ```
  
###### 静态资源 
 
   > 路径  gaodun.com/static/web/{epiphany,vendor} 其中vendor是第三方代码路径、epiphany是自己开发代码路径
 
   > 结构
 
   * epiphany目录结构
 
     ```
     .
    ├── build
    │   ├── css
    │   ├── images
    │   └── js
    ├── config.json
    ├── gulpfile.js
    ├── publish.json
    └── src
        ├── css
        ├── images
        └── js

     ```
   * vendor 目录结构
     
    ```
         ├── css
         └── js
         
     ```
#### 后端代码结构
     > 路径 gaodun.com/e.gaodun.com

     > 结构
       ```
       .
        ├── Application
        │   ├── Common
        │   │   ├── Common
        │   │   ├── Conf
        │   │   └── Tpl
        │   ├── Home
        │   │   ├── Behavior
        │   │   ├── Common
        │   │   ├── Conf
        │   │   ├── Controller
        │   │   ├── Logic
        │   │   ├── Model
        │   │   └── Widget
        │   └── Runtime
        ├── ChangeLog.md
        ├── composer.json
        ├── config.inc.php
        ├── crossdomain.xml
        ├── index.php
        ├── README.md
        └── vendor
   ```
 

## 数据库设计

> 使用epiphany 数据库

## 调用接口

   
