### AJAX- XMLHttpRequest 对象
XMLHttpRequest 对象用于同幕后服务器交换数据。这意味着可以更新网页的部分，而不需要重新加载整个页面。

#### 创建
>
    var = new XMLHttpReques();

**主流浏览器**均支持

#### 跨域访问
出于安全原因，现代浏览器不允许跨域访问。
这意味着尝试加载的网页和 XML 文件都必须位于相同服务器上。

#### AJAX向服务器发送请求
如需向服务器发送请求，我们使用 XMLHttpRequest 对象的 open() 和 send() 方法：

> 
    open(method.url,async)

>
    send(String)

#### GET POST
GET更加快捷，可用于多数情况
以下情况推荐使用Post
- 更新服务器
- 向服务器发送大量数据
- 发送用户输入

#### GET
>
    xhttp.open('GET','url',true);

#### POST
如需像 HTML 表单那样 POST 数据，请通过 setRequestHeader() 添加一个 HTTP 头部。请在 send() 方法中规定您需要发送的数据：
>
    xhttp.open("POST", "ajax_test.asp", true);
    xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
    xhttp.send("fname=Bill&lname=Gates");