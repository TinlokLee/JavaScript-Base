# JavaScript-Base
###  JavaScript

1. 概述
    JavaScript 是一网络脚本语言，可插入 HTML 页面的编程代码
            
    应用于网页改进设计，验证表单，检测浏览器，创建cookies，点击事件（弹窗）等
    
2. 使用
    HTML 中的脚本必须位于 <script> 与 </script> 标签之间
    脚本可被放置在 HTML 页面的 <body> 和 <head> 部分中

    1）点击事件：
    <button type="button" onclick="alert('Welcome!')">提交</button>

    2）改变 HTML 内容（函数）
    <h1>首页 JavaScript</h1>
    <script>
        function foo(){
            x = document.getElementById('demo') // 查找元素
            x.innerHTML="Hello JavaScript"      // 改变内容
        }
    </script>
    <button type="button" onclick="foo()">提交</button>

    3）HTML DOM
    DOM（文档对象模型）是用以访问 HTML 元素的正式 W3C 标准

    4）改变 HTML 图像
    <script>
        function changeImage(){
            element=document.getElementById('myimage')
            if (element.src.match("bulbon")){
                element.src="/i/eg_bulboff.gif";
                }
            else{
                element.src="/i/eg_bulbon.gif";
                }
            }
    </script>
    <img id="myimage" onclick="changeImage()" src="/i/eg_bulboff.gif">
    <p>点击灯泡来点亮或熄灭这盏灯</p>

    5）改变 HTML 样式
    <script>
        function foo(){
            x=document.getElementById("demo") // 找到元素
            x.style.color="#ff0000";          // 改变字体颜色
            }
    </script>

    <button type="button" onclick="foo()">提交</button>

    6）验证用户输入
    <p>请输入用户名</p>
    <input id="demo" type="text">
    <script>
        function foo(){
            var x=document.getElementById("demo").value;
            if(x=="" || isNaN(x)){
                alert('用户名错误')
            }
        }
    </script>
    <button type="button" onclick="foo()">提交</button>
    // 必须使用双引号，注意空格和缩进，大小写


3. 外部的 JavaScript
    外部 JavaScript 文件的文件扩展名是 .js
    如需使用外部文件，请在 <script> 标签的 "src" 属性中设置该 .js 文件
    注意：外部脚本不能包含 <script> 标签
    <!DOCTYPE html>
    <html>
    <body>
    <script src="myScript.js"></script>
    </body>
    </html>

    如：
    <!DOCTYPE html>
    <html>
    <body>
    <h1>My Web Page</h1>
    <p id="demo">A Paragraph</p>
    <button type="button" onclick="myFunction()">点击这里</button>
    <p><b>注释：</b>myFunction 保存在名为 "myScript.js" 的外部文件中。</p>
    <script type="text/javascript" src="/js/myScript.js"></script>
    </body>
    </html>

4. JavaScript 代码块
    浏览器会在读取代码时，逐行顺序执行脚本代码
    而对于传统编程来说，会在执行前对所有代码进行编译

5. JavaScript 变量
    变量必须以字母开头
    变量名称对大小写敏感（y 和 Y 是不同的变量）
    局部 JavaScript 变量 
        使用var局部变量，只能在函数内部访问它
    全局 JavaScript 变量
        在函数外声明的变量是全局变量，网页上的所有脚本和函数都能访问它
    JavaScript 变量的生存期
        JavaScript 变量的生命期从它们被声明的时间开始
        局部变量会在函数运行以后被删除
        全局变量会在页面关闭后被删除

    向未声明的 JavaScript 变量来分配值
        该变量将被自动作为全局变量声明

6. JavaScript 数据类型
    字符串：存储字符（比如 "Bill Gates"）的变量
    数字：可以带小数点，也可以不带
    布尔：（逻辑）只能有两个值：true 或 false
    数组
    var cars=new Array("Audi","BMW","Volvo");
    var cars=["Audi","BMW","Volvo"];

7. JavaScript 对象
    对象由花括号分隔，在括号内
    对象的属性以名称和值对的形式 (name : value) 来定义，属性由逗号分隔
    var person={
        firstname : "Bill",
        lastname  : "Gates",
        id        :  5566
        };
    对象属性有两种寻址方式：
    name=person.lastname;
    name=person["lastname"];

    Undefined 和 Null
    Undefined 这个值表示变量不含有值。
    可以通过将变量的值设置为 null 来清空变量
    <!DOCTYPE html>
    <html>
    <body>

    <script>
        var person;
        var car="Volvo";
        document.write(person + "<br />");
        document.write(car + "<br />");
        var car=null
        document.write(car + "<br />");
    </script>

    </body>
    </html>

    声明新变量时，可以使用关键词 "new" 来声明其类型
    JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象

    属性和方法
    属性：是与对象相关的值
    方法：是能够在对象上执行的动作
    JavaScript 中的几乎所有事务都是对象：字符串、数字、数组、日期、函数等

    1）访问对象的属性
    语法： objectName.propertyName
    var message="Hello World!";
    var x=message.length;

    2）访问对象的方法
    语法： objectName.methodName()
    var message="Hello world!";
    var x=message.toUpperCase();

8. JavaScript 函数语法
    函数是由事件驱动或者当它被调用时执行的可重复使用的代码块
    函数就是包裹在花括号中的代码块，前面使用了关键词 function
    1）调用带参数的函数
        变量和参数必须以一致的顺序出现
        第一个变量就是第一个被传递的参数的给定的值
    <!DOCTYPE html>
    <html>
    <body>

    <p>点击这个按钮，来调用带参数的函数。</p>

    <button onclick="myFunction('Bill Gates','CEO')">点击这里</button>

    <script>
    function myFunction(name,job)
    {
    alert("Welcome " + name + ", the " + job);
    }
    </script>

    </body>
    </html>

    2）带有返回值的函数
    function myFunction(){
        var x=5;
        return x;
    }
    函数调用
    var myVar=myFunction();

    测试：计算两个数字的乘积，并返回结果
    <!DOCTYPE html>
    <html>
    <body>

    <p>本例调用的函数会执行一个计算，然后返回结果：</p>
    <p id="demo"></p>
    <script>
    function myFunction(a,b)
    {
    return a*b;
    }

    document.getElementById("demo").innerHTML=myFunction(4,3);
    </script>

    </body>
    </html>


9. JavaScript 运算符
    1）算术运算符: + - * % / ++累加  --递减
    2）赋值运算符： =  ==  +=  -=  *=  /=  %=

    字符串和数字加法运算
    <script type="text/javascript">
        x=5+5;
        document.write(x);
        document.write("<br />");
        x="5"+"5";
        document.write(x);
        document.write("<br />");
        x=5+"5";
        document.write(x);
        document.write("<br />");
        x="5"+5;
        document.write(x);
        document.write("<br />");
    </script>

    <h3>规则是：</h3>
    <p><strong>如果把数字与字符串相加，结果将成为字符串。</strong></p>

    3）比较和逻辑运算符
    比较：<  <=  >  >=  !=  === 
    逻辑：&&and   ||or    !not


    4）条件语句： if   else if   else
    if (time<10)
    {
    x="Good morning";
    }
    else if (time<20)
    {
    x="Good day";
    }
    else
    {
    x="Good evening";
    }

    5）switch 语句用于基于不同的条件来执行不同的动作
    <p>点击下面的按钮来显示今天是周几：</p>

    <button onclick="myFunction()">点击</button>

    <p id="demo"></p>

    <script>
    function myFunction()
    {
    var x;
    var d=new Date().getDay();
    switch (d)
    {
    case 0:
        x="Today it's Sunday";
        break;
    case 1:
        x="Today it's Monday";
        break;
    case 2:
        x="Today it's Tuesday";
        break;
    case 3:
        x="Today it's Wednesday";
        break;
    case 4:
        x="Today it's Thursday";
        break;
    case 5:
        x="Today it's Friday";
        break;
    case 6:
        x="Today it's Saturday";
        break;
    }
    document.getElementById("demo").innerHTML=x;
    }
    </script>

    6）default 关键词

    <script>
    function myFunction()
    {
    var x;
    var d=new Date().getDay();
    switch (d)
    {
    case 6:
        x="Today it's Saturday";
        break;
    case 0:
        x="Today it's Sunday";
        break;
    default:
        x="Looking forward to the Weekend";
    }
    document.getElementById("demo").innerHTML=x;
    }
    </script>

    7）For 循环
    for - 循环代码块一定的次数
    for/in - 循环遍历对象的属性
    while - 当指定的条件为 true 时循环指定的代码块
    do/while - 同样当指定的条件为 true 时循环指定的代码块

    <script>
    cars=["BMW","Volvo","Saab","Ford"];
    for (var i=0;i<cars.length;i++)
    {
    document.write(cars[i] + "<br>");
    }
    </script>

    for in 语句
    var person={fname:"John",lname:"Doe",age:25};

    for (x in person)
    {
    txt=txt + person[x];
    }

    do while 语句
    do
    {
    x=x + "The number is " + i + "<br>";
    i++;
    }
    while (i<5);

    break 语句用于跳出循环
    <p>点击按钮，测试带有 break 语句的循环。</p>
    <button onclick="myFunction()">点击</button>
    <p id="demo"></p>

    <script>
    function myFunction()
    {
    var x="",i=0;
    for (i=0;i<10;i++)
    {
    if (i==3)
        {
        break;
        }
    x=x + "The number is " + i + "<br>";
    }
    document.getElementById("demo").innerHTML=x;
    }
    </script>

    continue 语句中断循环中的迭代，如果出现了指定的条件
             然后继续循环中的下一个迭代

    for (i=0;i<=10;i++)
    {
    if (i==3) continue;
    x=x + "The number is " + i + "<br>";
    }



10. JavaScript 错误 
    - Throw、Try 和 Catch
    try     测试代码块的错误
    catch   处理错误
    throw   创建自定义错误

    try catch
    <!DOCTYPE html>
    <html>
    <head>
    <script>
    var txt="";
    function message()
    {
    try
    {
    adddlert("Welcome guest!");
    }
    catch(err)
    {
    txt="本页有一个错误。\n\n";
    txt+="错误描述：" + err.message + "\n\n";
    txt+="点击确定继续。\n\n";
    alert(txt);
    }
    }
    </script>
    </head>

    <body>
    <input type="button" value="查看消息" onclick="message()" />
    </body>

    </html>


    程序流设计
    检测输入变量的值，如果值是错误的，会抛出一个异常（错误）
    catch 会捕捉到这个错误，并显示一段自定义的错误消息
    <!DOCTYPE html>
    <html>
    <body>

    <script>
    function myFunction()
    {
    try
    { 
    var x=document.getElementById("demo").value;
    if(x=="")    throw "值为空";
    if(isNaN(x)) throw "不是数字";
    if(x>10)     throw "太大";
    if(x<5)      throw "太小";
    }
    catch(err)
    {
    var y=document.getElementById("mess");
    y.innerHTML="错误：" + err + "。";
    }
    }
    </script>

    <h1>JavaScript 程序</h1>
    <p>请输入 5 到 10 之间的数字：</p>
    <input id="demo" type="text">
    <button type="button" onclick="myFunction()">测试输入值</button>
    <p id="mess"></p>

    </body>
    </html>



11. JavaScript 表单验证 / 邮箱验证 
    <html>
    <head>
    <script type="text/javascript">


    // 表单验证
    function validate_required(field,alerttxt)
    {
    with (field)
    {
    if (value==null||value=="")
        {alert(alerttxt);return false}
    else {return true}
    }
    }

    // 邮箱验证
    function validate_email(field,alerttxt)
    {
    with (field)
    {
    apos=value.indexOf("@")
    dotpos=value.lastIndexOf(".")
    if (apos<1||dotpos-apos<2) 
    {alert(alerttxt);return false}
    else {return true}
    }
    }

    function validate_form(thisform)
    {
    with (thisform)
    {
    if (validate_required(email,"Email must be filled out!")==false)
        {email.focus();return false}

    else if (validate_email(email,"Not a valid e-mail address!")==false)
        {email.focus();return false}
    }
    }
    </script>
    </head>

    <body>
    <form action="submitpage.htm" onsubmit="return validate_form(this)" method="post">
    Email: <input type="text" name="email" size="30">
    <input type="submit" value="Submit"> 
    </form>
    </body>

    </html>


12. JavaScript HTML DOM
    通过 HTML DOM，可访问 JavaScript HTML 文档的所有元素
    当网页被加载时，浏览器会创建页面的 DOM

    通过编写 DOM ，来创建动态的 HTML
    JavaScript 能够改变页面中的所有 HTML 元素
               HTML 属性       CSS 样式
               对页面中的所有事件做出反应


    1）查找 HTML 元素
    通过id  标签名  类名
    通过id / 标签名查找 
    var x=document.getElementById("main");
    var y=x.getElementsByTagName("p");

    2）改变 HTML 内容
    修改 HTML 内容的最简单的方法时使用 innerHTML 属性
    document.getElementById(id).innerHTML=new HTML

    3）改变 HTML 属性
    document.getElementById(id).attribute=new value
    <img id="image" src="smiley.gif">
    <script>
    document.getElementById("image").src="landscape.jpg";
    </script>

    4）改变 HTML 样式
    document.getElementById(id).style.property=new style
    <p id="p1">Hello World!</p>
    <script>
    document.getElementById("p1").style.color="red";
    </script>

    元素显示或消失
    <p id="p1">文本</p>
    <input type="button" value="隐藏文本" onclick="document.getElementById('p1').style.visibility='hidden'" />
    <input type="button" value="显示文本" onclick="document.getElementById('p1').style.visibility='visible'" />


    5）JavaScript HTML DOM 事件
    HTML DOM 使 JavaScript 有能力对 HTML 事件做出反应
    HTML 事件的例子：
        当用户点击鼠标时
        当网页已加载时
        当图像已加载时
        当鼠标移动到元素上时
        当输入字段被改变时
        当提交 HTML 表单时
        当用户触发按键时

    5-1）当用户在 <h1> 元素上点击时，会改变其内容
    <h1 onclick="this.innerHTML='谢谢!'">请点击该文本</h1>

    5-2）从事件处理器调用一个函数
    <head>
    <script>
    function changetext(id)
    {
    id.innerHTML="谢谢!";
    }
    </script>
    </head>

    <body>
    <h1 onclick="changetext(this)">请点击该文本</h1>
    </body>

    5-3）HTML 事件属性
    如需向 HTML 元素分配事件，可以使用事件属性
    <button onclick="displayDate()">点击这里</button>

    使用 HTML DOM 来分配事件
    document.getElementById("myBtn").onclick=function(){displayDate()};

    5-4）onload 和 onunload 事件
    会在用户进入或离开页面时被触发，可用于处理 cookie
    <body onload="checkCookies()">

    5-5）onchange 事件
    常结合对输入字段的验证来使用
    如： 当用户改变输入字段的内容时，会调用 upperCase() 函数
    <input type="text" id="fname" onchange="upperCase()">

    5-6）onmouseover 和 onmouseout 事件
    用户的鼠标移至 HTML 元素上方或移出元素时触发函数
    <body>
    <div onmouseover="mOver(this)" onmouseout="mOut(this)" style="background-color:green;width:120px;height:20px;padding:40px;color:#ffffff;">把鼠标移到上面</div>
    <script>
    function mOver(obj)
    {
    obj.innerHTML="谢谢"
    }
    function mOut(obj)
    {
    obj.innerHTML="把鼠标移到上面"
    }
    </script>
    </body>


    5-7）onmousedown、onmouseup 以及 onclick 事件
    构成了鼠标点击事件的所有部分，顺序依次为：
    点击鼠标按钮 -- 释放鼠标按钮 -- 完成鼠标点击
    <div onmousedown="mDown(this)" onmouseup="mUp(this)" style="background-color:green;color:#ffffff;width:90px;height:20px;padding:40px;font-size:12px;">请点击这里</div>

    <script>
    function mDown(obj)
    {
    obj.style.backgroundColor="#1ec5e5";
    obj.innerHTML="请释放鼠标按钮"
    }

    function mUp(obj)
    {
    obj.style.backgroundColor="green";
    obj.innerHTML="请按下鼠标按钮"
    }
    </script>

    
    // 页面加载完成，显示提示框
    <!DOCTYPE html>
    <html>
    <head>

    <script>
    function mymessage()
    {
    alert("这段消息由 onload 事件触发");
    }
    </script>
    </head>

    <body onload="mymessage()">
    </body>

    </html>

    // 当指针移动到元素上方时，改变其颜色
    // 当指针移出文本后，会再次改变其颜色
    <h1 onmouseover="style.color='red'" onmouseout="style.color='black'">请把鼠标移到这段文本上</h1>


    6）HTML DOM 元素（节点）
    <div id="div1">
    <p id="p1">这是一个段落</p>
    <p id="p2">这是另一个段落</p>
    </div>

    <script>
    var para=document.createElement("p");
    var node=document.createTextNode("这是新段落。");
    para.appendChild(node);

    // 追加元素
    var element=document.getElementById("div1");
    element.appendChild(para);
    
    // 删除元素
    var parent=document.getElementById("div1");
    var child=document.getElementById("p1");
    parent.removeChild(child);
    </script>


13. JavaScript 对象
    JavaScript 中的所有事物都是对象：字符串、数值、数组、函数等
    此外，允许自定义对象（对象只是带有属性和方法的特殊数据类型）

    1）访问对象的属性
    objectName.propertyName

    2）访问对象的方法
    objectName.methodName()

    3）创建 JavaScript 对象
    person=new Object();
    person.firstname="Bill";
    person.lastname="Gates";
    person.age=56;
    person.eyecolor="blue";

    // 简写为
    person={firstname:"John",lastname:"Doe",age:50,eyecolor:"blue"};

    4）使用对象构造器
    function person(firstname,lastname,age,eyecolor)
    {
    this.firstname=firstname;
    this.lastname=lastname;
    this.age=age;
    this.eyecolor=eyecolor;
    }

    // 创建 JavaScript 对象实例
    var myFather=new person("Bill","Gates",56,"blue");
    var myMother=new person("Steve","Jobs",48,"green");

    // 添加属性方法
    person.firstname="Bill";
    person.lastname="Gates";
    x=person.firstname;

    this.changeName=changeName;
    function changeName(name)
    {
    this.lastname=name;
    // 测试
    myMother.changeName("Ballmer");


    5）JavaScript 类
    JavaScript 基于 prototype，而不是基于类的


    6）JavaScript Number 对象
    JavaScript 数字可以使用也可以不使用小数点来书写
               所有数字都存储为根为 10 的 64 位（8 比特），浮点数
    var y=123e5;    // 12300000
    var z=123e-5;   // 0.00123

    八进制和十六进制
    如果前缀为 0，则 JavaScript 会把数值常量解释为八进制数
    如果前缀为 0 和 "x"，则解释为十六进制数
    var y=0377;
    var z=0xFF; 

    数字属性和方法
    属性：
    MAX VALUE
    MIN VALUE
    NEGATIVE INFINITIVE
    POSITIVE INFINITIVE
    NaN
    prototype
    constructor

    方法：
    toExponential()
    toFixed()
    toPrecision()
    toString()
    valueOf()


    7）JavaScript Date（日期）对象
    返回当前日期和时间
    <script type="text/javascript">
    document.write(Date())

    // 设置具体的日期
    var d = new Date()
    d.setFullYear(1992,10,3)
    document.write(d)

    // 当日的日期（根据 UTC）转换为字符串
    document.write (d.toUTCString())

    // 使用 getDay() 和数组来显示星期，而不仅仅是数字
    var d=new Date()
    var weekday=new Array(7)
    weekday[0]="星期日"
    weekday[1]="星期一"
    weekday[2]="星期二"
    weekday[3]="星期三"
    weekday[4]="星期四"
    weekday[5]="星期五"
    weekday[6]="星期六"

    document.write("今天是" + weekday[d.getDay()])

    // 显示钟表
    <script type="text/javascript">
    function startTime()
    {
    var today=new Date()
    var h=today.getHours()
    var m=today.getMinutes()
    var s=today.getSeconds()
    // add a zero in front of numbers<10
    m=checkTime(m)
    s=checkTime(s)
    document.getElementById('txt').innerHTML=h+":"+m+":"+s
    t=setTimeout('startTime()',500)
    }

    function checkTime(i)
    {
    if (i<10) 
    {i="0" + i}
    return i
    }
    </script>
    </head>

    <body onload="startTime()">
    <div id="txt"></div>

    </script>


    8）JavaScript Array（数组）对象
    数组对象的作用是：使用单独的变量名来存储一系列的值
    <html>
    <body>

    <script type="text/javascript">
    // 创建数组
    var mycars = new Array()
    mycars[0] = "Saab"
    mycars[1] = "Volvo"
    mycars[2] = "BMW"

    for (i=0;i<mycars.length;i++)
    {
    document.write(mycars[i] + "<br />")
    }

    // 合并两个数组
    var arr = new Array(3)
    arr[0] = "George"
    arr[1] = "John"
    arr[2] = "Thomas"

    var arr2 = new Array(3)
    arr2[0] = "James"
    arr2[1] = "Adrew"
    arr2[2] = "Martin"

    document.write(arr.concat(arr2))


    // 数组排序
    document.write(arr + "<br />")
    document.write(arr.sort())
    // 数字数组排序
    document.write(arr.sort(sortNumber))

    </script>
    </body>
    </html>


    9）JavaScript Boolean（逻辑）对象
    Boolean（逻辑）对象用于将非逻辑值转换为逻辑值true 或者 false

    10）JavaScript Math（算数）对象
    Math（算数）对象的作用是：执行常见的算数任务
    <html>
    <body>

    <script type="text/javascript">
    // round() 四舍五入
    document.write(Math.round(0.60) + "<br />")
    document.write(Math.round(0.50) + "<br />")
    document.write(Math.round(0.49) + "<br />")
    document.write(Math.round(-4.40) + "<br />")
    document.write(Math.round(-4.60))

    // random() 返回 0 到 1 之间的随机数
    document.write(Math.random())

    // max() 和 min()

    </script>

    </body>
    </html>


    11）JavaScript RegExp 正则表达式对象
    RegExp 对象用于规定在文本中检索的内容
    定义 RegExp
    var patt1=new RegExp("e");

    RegExp 对象有 3 个方法：test()、exec() 以及 compile()
    test() 方法检索字符串中的指定值，返回值是 true 或 false
    document.write(patt1.test("The best things in life are free")); 

    exec() 方法检索字符串中的指定值，返回值是被找到的值
           如果没有发现匹配，则返回 nul
    document.write(patt1.exec("The best things in life are free")); 

    <script type="text/javascript">
    var patt1=new RegExp("e","g");
    do
    {
    result=patt1.exec("The best things in life are free");
    document.write(result);
    }
    while (result!=null) 
    </script>


    compile() 方法用于改变 RegExp
              既可以改变检索模式，也可以添加或删除第二个参数
    <html>
    <body>

    <script type="text/javascript">
    var patt1=new RegExp("e");
    document.write(patt1.test("The best things in life are free"));

    patt1.compile("d");

    document.write(patt1.test("The best things in life are free"));
    </script>

    </body>
    </html>
    


14. JavaScript Window - 浏览器对象模型
    浏览器对象模型 (BOM) 使 JavaScript 有能力与浏览器对话
    <!DOCTYPE html>
    <html>
    <body>

    <p id="demo"></p>

    <script>
    var w=window.innerWidth
    || document.documentElement.clientWidth
    || document.body.clientWidth;

    var h=window.innerHeight
    || document.documentElement.clientHeight
    || document.body.clientHeight;

    x=document.getElementById("demo");
    x.innerHTML="浏览器的内部窗口宽度：" + w + "，高度：" + h + "。"
    </script>

    </body>
    </html>


    其他 Window 方法
    window.open() -     打开新窗口
    window.close() -    关闭当前窗口
    window.moveTo() -   移动当前窗口
    window.resizeTo() - 调整当前窗口的尺寸


    1）window.screen   对象包含有关用户屏幕的信息
    2）window.location 对象用于获得当前页面的地址 (URL)
                       并把浏览器重定向到新的页面

    返回当前 URL 的路径名
    <script>
    document.write(location.pathname);
    </script>

    location.assign() 方法加载新的文档
    <html>
    <head>
    <script>
    function newDoc()
    {
    window.location.assign("http://www.baidu.com.cn")
    }
    </script>
    </head>
    <body>
    <input type="button" value="加载新文档" onclick="newDoc()">
    </body>
    </html>

    3）JavaScript Window History  对象包含浏览器的历史
    function goBack()
    {
    window.history.back()
    }
    function goForward()
    {
    window.history.forward()
    }

    4）JavaScript Window Navigator 对象包含有关访问者浏览器的信息

    5）JavaScript 消息框
    <html>
    <head>
    <script type="text/javascript">
    function disp_alert()
    {
    alert("我是警告框！！")
    }

    // 确认框
    function show_confirm()
    {
    var r=confirm("Press a button!");
    if (r==true)
    {
    alert("You pressed OK!");
    }
    else
    {
    alert("You pressed Cancel!");
    }
    }

    // 提示框
    function disp_prompt()
    {
    var name=prompt("请输入您的名字","Bill Gates")
    if (name!=null && name!="")
        {
        document.write("你好！" + name + " 忙吗？")
        }
    }

    </script>
    </head>
    <body>

    <input type="button" onclick="disp_alert()" value="显示警告框" />
    <input type="button" onclick="disp_prompt()" value="显示提示框" />

    </body>
    </html>


    6）JavaScript 计时
    通过使用 JavaScript，我们有能力做到在一个设定的时间间隔之后来执行代码
    而不是在函数被调用后立即执行。我们称之为计时事件
    <html>
    <head>
    <script type="text/javascript">
    function timedMsg()
    {
    var t=setTimeout("alert('5 秒！')",5000)
    }
    </script>
    </head>

    <body>
    <form>
    <input type="button" value="显示定时的警告框" onClick = "timedMsg()">
    </form>
    <p>请点击上面的按钮。警告框会在 5 秒后显示</p>
    </body>

    </html>    

    // 输入框显示出已经逝去的时间（2、4、6 秒）
    <html>
    <head>
    <script type="text/javascript">
    function timedText()
    {
    var t1=setTimeout("document.getElementById('txt').value='2 秒'",2000)
    var t2=setTimeout("document.getElementById('txt').value='4 秒'",4000)
    var t3=setTimeout("document.getElementById('txt').value='6 秒'",6000)
    }
    </script>
    </head>
    <body>
    <form>
    <input type="button" value="显示计时的文本" onClick="timedText()">
    <input type="text" id="txt">
    </form>

    <p>点击上面的按钮,输入框会显示出已经逝去的时间（2、4、6 秒）</p>
    </body>

    </html>

    // 无穷循环中计时事件 + 停止按钮
    <html>
    <head>
    <script type="text/javascript">
    var c=0
    var t
    function timedCount()
    {
    document.getElementById('txt').value=c
    c=c+1
    t=setTimeout("timedCount()",1000)
    }

    // 停止按钮
    function stopCount()
    {
    c=0;
    setTimeout("document.getElementById('txt').value=0",0);
    clearTimeout(t);
    }
    </script>
    </head>
    <body>
    <form>
    <input type="button" value="开始计时！" onClick="timedCount()">
    <input type="text" id="txt">
    </form>

    <p>请点击上面的按钮。输入框会从 0 开始一直进行计时。</p>
    </body>
    </html>


    实现一个钟表
    <html>
    <head>
    <script type="text/javascript">
    function startTime()
    {
    var today=new Date()
    var h=today.getHours()
    var m=today.getMinutes()
    var s=today.getSeconds()
   
    m=checkTime(m)
    s=checkTime(s)
    document.getElementById('txt').innerHTML=h+":"+m+":"+s
    t=setTimeout('startTime()',500)
    }
    function checkTime(i)
    {
    if (i<10) 
    {i="0" + i}
    return i
    }
    </script>
    </head>
    <body onload="startTime()">
    <div id="txt"></div>
    </body>
    </html>



15. JavaScript Cookies
    cookie 用来识别用户
    创建和存储 cookie
    <html>
    <head>
    <script type="text/javascript">
    // 获取cookie
    function getCookie(c_name)
    {
    if (document.cookie.length>0)
    {
    c_start=document.cookie.indexOf(c_name + "=")
    if (c_start!=-1)
        { 
        c_start=c_start + c_name.length+1 
        c_end=document.cookie.indexOf(";",c_start)
        if (c_end==-1) c_end=document.cookie.length
        return unescape(document.cookie.substring(c_start,c_end))
        } 
    }
    return ""
    }

    // 设置cookie 值和过期时间
    function setCookie(c_name,value,expiredays)
    {
    var exdate=new Date()
    exdate.setDate(exdate.getDate()+expiredays)
    document.cookie=c_name+ "=" +escape(value)+
    ((expiredays==null) ? "" : ";expires="+exdate.toGMTString())
    }

    // 检查cookie
    function checkCookie()
    {
    username=getCookie('username')
    if (username!=null && username!="")
    {alert('Welcome again '+username+'!')}
    else 
    {
    username=prompt('Please enter your name:',"")
    if (username!=null && username!="")
        {
        setCookie('username',username,365)
        }
    }
    }
    </script>
    </head>

    <body onLoad="checkCookie()">
    </body>
    </html>    

16. JavaScript 库
    JavaScript 库(框架) - jQuery、Prototype、MooTools
    提供针对常见 JavaScript 任务的函数，包括动画、DOM 操作以及 Ajax 处理

    jQuery
    jQuery 是目前最受欢迎的 JavaScript 框架
    它使用 CSS 选择器来访问和操作网页上的 HTML 元素（DOM 对象）
    jQuery 同时提供 companion UI（用户界面）和插件

    引用 jQuery
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
    </script>


    测试 jQuery
    处理窗口加载事件
    JavaScript 方式：
    function myFunction()
    {
    var obj=document.getElementById("h01");
    obj.innerHTML="Hello jQuery";
    }
    onload=myFunction;

    jQuery 方式：
    函数是 $() 函数，通过 CSS 选择器来选取元素
    function myFunction()
    {
    $("#h01").html("Hello jQuery");
    }
    $(document).ready(myFunction);

