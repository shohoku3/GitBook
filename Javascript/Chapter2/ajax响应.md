### AJAX 响应

#### 响应时用的属性
- readyState 属性存留 XMLHttpRequest 的状态。
- onreadystatechange 属性定义当 readyState 发生变化时执行的函数。
- status 属性和 statusText 属性存有 XMLHttpRequest 对象的状态。

>
    function loadDoc(){
        var xhttp=new XMLHttpRequest();
        xhttp.onreadystatechange=function(){
            if(this.readystate==4&&this.status==200)
            {
                动作
            }
        }
    }

#### 使用回调函数
