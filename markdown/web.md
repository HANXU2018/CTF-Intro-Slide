# Web
网络安全


## 常见知识点
- SQL注入
- XSS
- CSRF
- RCE
- 文件包含
- SSRF
- SSTI
- 文件上传


- 条件竞争
- 反序列化
- XXE
- 水平/垂直越权
- 任意用户密码重置
- 敏感信息泄露
- 代码审计


## 常用工具
- 各种语言IDE
- 浏览器开发者工具
- Kali Linux
- Burpsuite
- sqlmap
- Hackbar
- Hashcat
- 各种扫描器
- 蚁剑
- Seay


## 例子：注入大类
用户输入被作为代码执行


### SQL注入
```sql
select blabla from users where username='$username' and passwd='$password'
```

令`$username="aaaa' or 1=1--"`：

```sql
select blabla from users where username='aaaa' or 1=1--' and passwd='$password'
```

- 有回显：`union select`
- 无回显
    - `order by`
    - 报错注入：`extractvalue`/`updatexml`
- 无报错
    - 布尔盲注：`substr`/`mid`/`ascii`
    - 时间盲注：`if`/`for`/`sleep`/`benchmark`

    
- 绕过技术
    - 十六进制编码
    - `regexp`
    - 大小写
    - 双写
    - `concat`级联
    - 宽字节注入
    - 无列名注入
    - ...


### XSS
- 反射型
- 存储型
- DOM型


#### 反射型
后端：
```php
<?php 
// Is there any input? 
if( array_key_exists( "name", $_GET ) && $_GET[ 'name' ] != NULL ) { 
    // Feedback for end user 
    echo '<pre>Hello ' . $_GET[ 'name' ] . '</pre>'; 
} 
?>
```

访问：
```
http://localhost:8080/index.php?name=<script>alert(1);</script>
```


#### 存储型
```php
<?php
  if( isset( $_POST[ 'btnSign' ] ) ) {
    // Get input
    $message = trim( $_POST[ 'mtxMessage' ] );
    $name    = trim( $_POST[ 'txtName' ] );
    // Sanitize message input
    $message = stripslashes( $message );
    $message = mysql_real_escape_string( $message );
    // Sanitize name input
    $name = mysql_real_escape_string( $name );
    // Update database
    $query  = "INSERT INTO guestbook ( comment, name ) VALUES ( '$message', '$name' );";
    $result = mysql_query( $query ) or die( '<pre>' . mysql_error() . '</pre>' );
    //mysql_close(); }
?>
```


#### DOM型
```html
<html>
  <head>
    <title>DOM-XSS test</title>
  </head>
  <body>
    <script>
      var a=document.URL;
      document.write(a.substring(a.indexOf("a=")+2,a.length));
    </script>
  </body>
</html>
```

访问：
```
http://localhost:8080/xss.html?a=<script>alert(1);</script>
```


### 类似攻击
还有RCE、SSTI、XXE等原理类似。

- RCE：远程命令执行，实际上通常是由于服务端代码注入
- SSTI：服务端模板注入
- XXE：XML外部实体注入
- 防御思路：不信任任何用户输入


## 涉及语言
- PHP
    - Laravel
    - Thinkphp
    - ...
- Java
    - Spring
    - Tomcat
- <span class="fragment highlight-blue">**Python**</span>
    - Django
    - Flask
    - Tornado


- <span class="fragment highlight-blue">**Node.js**</span>
- Perl
- Ruby
- Golang


## 漏洞利用
- 编程语言漏洞
- 框架漏洞
- 数据库漏洞
- CMS漏洞
- 关注：CVE/CNVD等

