###JSON
**JSON:** JavaScript Object Notation（JavaScript 对象标记法）。
**JSON 是一种存储和交换数据的语法**
#### 发送数据
>
    var myObj={name:'Bill Gates'}
    var myJSON=JSON.stringify(myObj);

#### 接收数据
>
    var myJSON = '{ "name":"Bill Gates",  "age":62, "city":"Seattle" }';
    var myObj =  JSON.parse(myJSON);

#### 存储数据
>
    myObj = { name:"Bill Gates",  age:62, city:"Seattle" };
    myJSON =  JSON.stringify(myObj);
    localStorage.setItem("testJSON", myJSON);
    //JSON化本地存储

>
    text = localStorage.getItem("testJSON");
    obj =  JSON.parse(text);
    document.getElementById("demo").innerHTML = obj.name;

#### JSON XML
- XML 必须使用 XML 解析器进行解析。而 JSON 可通过标准的 JavaScript 函数进行解析。

#### 注意事项
**JSON有效数据类型**
- 字符串
- 数字
- 对象
- **数组**
- 布尔值
- **NUll**

**以下值为无效的**
- 函数
- 日期
- undefined

#### JSON.parse()
- JSON 的常规用途是同 web 服务器进行数据传输。
**在从 web 服务器接收数据时，数据永远是字符串。**
**通过 JSON.parse() 解析数据，这些数据会成为 JavaScript 对象。**


#### JSON响应

>
    var xhttp=new XMLHttpRequest();

    xhttp.onreadystatechange=function(){
        if(this.readyState==4&&this.state)
        {
            myObj==JSON.parse(this.responseText);
        }
    }

**对于衍生自数组的JSON使用JSON.parse()返回js数组**

#### JSON发送
JSON的常规用途是同web服务器进行数据交换
JSON.stringify() 将JSON数据字符串化
**JSON对像嵌套对象**
**JSON对象中有数组**
>
    {
    "name":"Bill Gates",
    "age":62,
    "cars":[ "Porsche", "BMW", "Volvo" ]
    }
**JSON 对象中的嵌套数组**
>
    myObj =  {
   "name":"Bill Gates",
   "age":62,
   "cars": [
	  { "name":"Porsche",  "models":[ "911", "Taycan" ] },
	  { "name":"BMW", "models":[ "M5", "M3", "X5" ] },
	  { "name":"Volvo", "models":[ "XC60", "V60" ] }
        ]
    }