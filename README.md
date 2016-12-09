# WebBench

Webbench是一个在linux下使用的非常简单的网站压测工具。它使用fork()模拟多个客户端同时访问我们设定的URL，测试网站在压力下工作的性能，最多可以模拟3万个并发连接去测试网站的负载能力。

##使用：

	sudo make && make install
  
##命令行选项：




| 短参        | 长参数           | 作用   |
| ------------- |:-------------:| -----:|
|-f     |--force                |不需要等待服务器响应               | 
|-r     |--reload               |发送重新加载请求                   |
|-t     |--time <sec>           |运行多长时间，单位：秒"            |
    |-p     |--proxy <server:port>  |使用代理服务器来发送请求	    |
|-c     |--clients <n>          |创建多少个客户端，默认1个"         |
     |-9     |--http09               |使用 HTTP/0.9                      |
|-1     |--http10               |使用 HTTP/1.0 协议                 |
     |-2     |--http11               |使用 HTTP/1.1 协议                 |
|       |--get                  |使用 GET请求方法                   |
|       |--head                 |使用 HEAD请求方                    |
|       |--options              |使用 OPTIONS请求方法               |
|       |--trace                |使用 TRACE请求方法                 |
|-?/-h  |--help                 |打印帮助信息                       |
|-V     |--version              |显示版本号                         |


## 1、WebBench安装：

> wget http://www.ha97.com/code/webbench-1.5.tar.gz

> tar zxvf webbench-1.5.tar.gz

> cd webbench-1.5

> make

> make install

## 2、WebBench使用：
webbench -c 1000 -t 60 http://192.168.80.157/phpinfo.php

webbench -c 并发数 -t 运行测试时间 URL

> Apache测试实例结果：

> 当并发300时，<br/>
root [ ~ ]# webbench -c 300 -t 60 http://192.168.80.157/phpinfo.php
Webbench - Simple Web Benchmark 1.5
Copyright (c) Radim Kolar 1997-2004, GPL Open Source Software.

* Benchmarking: GET http://192.168.80.157/phpinfo.php
* 300 clients, running 60 sec.

* Speed=24525 pages/min, 20794612 bytes/sec.
* Requests: 24525 susceed, 0 failed.

* 每秒钟响应请求数：24525 pages/min，每秒钟传输数据量20794612 bytes/sec.
