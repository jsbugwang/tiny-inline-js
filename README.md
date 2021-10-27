# tiny-inline-js
非常小的类 jQuery 的内联 JS 工具库，适合嵌入式简单业务逻辑

## JavaScript Micro-Templating

[`JavaScript Micro-Templating`](https://johnresig.com/blog/javascript-micro-templating/) 是 `jQuery` 作者 **John Resig** 2008 年的作品。
用在数字公司的一些对性能要求极高的嵌入式页面。

最大特点是小：

* 有效代码 **21** 行
* Uglify 后 **498** 个字符。

代码拷贝在本项目的 `lib/micro-template.js` 文件。

其语法有点是灵活，缺点是可读性较差，语法3条：

* 用正常的方式书写html
* 用<% %>嵌套JavaScript语句
* 用<%= %>嵌套JavaScript 变量值

如：

```
<script type="text/html" id="item_tmpl">
  <div id="<%=id%>" class="<%=(i % 2 == 1 ? " even" : "")%>">
    <div class="grid_1 alpha right">
      <img class="righted" src="<%=profile_image_url%>"/>
    </div>
    <div class="grid_6 omega contents">
      <p><b><a href="/<%=from_user%>"><%=from_user%></a>:</b> <%=text%></p>
    </div>
  </div>
</script>
```

另外推荐 [ART-TEMPLATE](https://aui.github.io/art-template/zh-cn/) ，支持友好的调试，支持编译阶段（预编译成JS）优化，性能较高，只是 GZip 后还有6K。