HAR Viewer汉化版
================
* 汉化者：zhujianfeng, 新浪微博@fdjianfeng
* http://www.zhujianfeng.info
* 只汉化了瀑布图部分的菜单和tooltip等信息
* 修复了原版在IE8及更早版本下不能使用事件触发方式直接显示瀑布图的bug
* 增加了使用requiresjs直接向外暴露接口的功能
* 增加了无刷新reload功能
* 增加调用时传入参数，使用jsonp等方式跨域载入json文件
* 增加调用时使用列表方式一次载入多个json文件的功能
* 修复在页面中有svg对象情况下，鼠标在svg对象上移动时浏览器疯狂报错的bug
* 调用可以使用如下方式

```javascript
$("#content").bind("onViewerPreInit", function(event){  
        // Get application object  
        var viewer = event.target.repObject;  
        viewer.removeTab("Home");  
        viewer.removeTab("DOM");  
        viewer.removeTab("About");  
        viewer.removeTab("Schema");  
        // Hide the tab bar  
        viewer.showTabBar(false);  
        // Remove toolbar buttons  
        var preview = viewer.getTab("Preview");  
        preview.toolbar.removeButton("download");  
        preview.toolbar.removeButton("clear");  
});  
require(["harViewer"],function(Interface){  
        Interface.render(["z.har","s.har"]);  
        $("#reload").click(function(){  
            Interface.reload(["http://www.someurl.com/g.har"],{jsonp:true});  
        });  
});  

```

HAR Viewer
==========

* Author: Jan Odvarko, odvarko@gmail.com,
* http://www.softwareishard.com/
* Home page: http://www.janodvarko.cz/har/viewer
* Issue list: http://code.google.com/p/harviewer/issues/list
* Project home: http://code.google.com/p/harviewer/

Components
----------
* Application Components:
* RequireJS: http://requirejs.org/
* jQuery: http://jquery.com/
* jQuery JSON plugin: Jim Dalton (jim.dalton@furrybrains.com), based on http://www.JSON.org/json2.js
* Domplate + Domplate based templates: http://getfirebug.com
* Excanvas: http://code.google.com/p/explorercanvas/
* Downloadify: http://github.com/dcneiner/Downloadify/
* SWFObject 2.0: http://code.google.com/p/swfobject/
* Code Syntax Highlighter: http://www.dreamprojections.com/syntaxhighlighter/
* JSON Query: https://github.com/JasonSmith/jsonquery, http://www.sitepen.com/blog/2008/07/16/jsonquery-data-querying-beyond-jsonpath/

Build Tools
-----------
* js-build-tools: http://code.google.com/p/js-build-tools/
* js-min (ant task): http://code.google.com/p/jsmin-ant-task/
* jsdoc-toolkit: code.google.com/p/jsdoc-toolkit/
* jsdoc-toolkit-ant-task: http://code.google.com/p/jsdoc-toolkit-ant-task/
* shrink-safe: http://shrinksafe.dojotoolkit.org/
* Rhino: http://www.mozilla.org/rhino/

Testing
-------
* Selenium: http://seleniumhq.org/
* PHPUnit: http://www.phpunit.de/

Development
-----------
* To start the build, go to the webapp/scripts directory and execute the following command:

`..\..\requirejs\build\build.bat app.build.js`

