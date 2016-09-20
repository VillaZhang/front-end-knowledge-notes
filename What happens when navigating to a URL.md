## What happens when navigating to a URL
1）把URL分割成几个部分：协议、网络地址、资源路径。其中网络地址指示该连接网络上哪一台计算机，可以是域名或者IP地址，可以包括端口号；协议是从该计算机获取资源的方式，常见的是HTTP、FTP，不同协议有不同的通讯内容格式；资源路径指示从服务器上获取哪一项资源。
例如：http://www.guokr.com/question/554991/
协议部分：http
网络地址：www.guokr.com
资源路径：/question/554991/

2）如果地址不是一个IP地址，通过DNS（域名系统）将该地址解析成IP地址。IP地址对应着网络上一台计算机，DNS服务器本身也有IP，你的网络设置包含DNS服务器的IP。
例如：www.guokr.com 不是一个IP，向DNS询问请求www.guokr.com 对应的IP，获得IP： 111.13.57.142。这个过程里，你的电脑直接询问的DNS服务器可能没有www.guokr.com 对应的IP，就会向它的上级服务器询问，上级服务器同样可能没有，就依此一层层向上找，最高可达根节点，找到或者全部找不到为止。

3）如果地址不包含端口号，根据协议的默认端口号确定一个。端口号之于计算机就像窗口号之于银行，一家银行有多个窗口，每个窗口都有个号码，不同窗口可以负责不同的服务。端口只是一个逻辑概念，和计算机硬件没有关系。
例如：www.guokr.com 不包含端口号，http协议默认端口号是80。如果你输入的url是http://www.guokr.com:8080/ ，那表示不使用默认的端口号，而使用指定的端口号8080。

4）向2和3确定的IP和端口号发起网络连接。
例如：向111.13.57.142的80端口发起连接

5）根据http协议要求，组织一个请求的数据包，里面包含大量请求信息，包括请求的资源路径、你的身份
例如：用自然语言来表达这个数据包，大概就是：请求 /question/554991/ ，我的身份是xxxxxxx。

6）服务器响应请求，将数据返回给浏览器。数据可能是根据HTML协议组织的网页，里面包含页面的布局、文字。数据也可能是图片、脚本程序等。现在你可以用浏览器的“查看源代码”功能，感受一下服务器返回的是什么东东。如果资源路径指示的资源不存在，服务器就会返回著名的404错误。

7）如果（6）返回的是一个页面，根据页面里一些外链的URL，例如图片的地址，按照（1）－（6）再次获取。

8）开始根据资源的类型，将资源组织成屏幕上显示的图像，这个过程叫渲染，网页渲染是浏览器最复杂、最核心的功能。

9）将渲染好的页面图像显示出来，并开始响应用户的操作。