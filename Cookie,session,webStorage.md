---
title: Cookie,Session,webStorage
---





# Cookie

`Cookie`是一种机制，它可以弥补HTTP协议无状态的不足。在`session`出现前，基本上所有的网站都`cookie`来跟踪对话

`HTTP`头部有两个专门负责设置以及`cookie`的，分别是`Set_Cookie`和`Cookie`,当服务器返回给客户端一个http响应时，如果头部包含`Set-Cookie`这个头部时，客户端会建立一个`cookie`，并在后续的http请求中自动发送这个`cookie`，直到这个`cookie`过期。如果`cookie`的生存时间是整个会话期间的话，那个浏览器会将`cookie`保存在内存中，浏览器关闭时就会自动清除这个`cookie`。如果设置了过期时间，浏览器会将`cookie`保存在硬盘里，关闭后再打开仍然有效直到超过预设时间，下一次打开浏览器访问对应的网站，这个`cookie`就会自动再次发送到服务器。一个`cookie`的设置和发送分为四个过程：

- 客户端发送一个http请求到服务器
- 服务器发送一个http响应到客户端，头部包含`Set-Cookie`
- 客户端发送一个http请求到服务器端，其中头部包含`Cookie`
- 服务器发送一个http响应到客户端

`cookie`具有不可跨域名性

# Session

`Session`是服务器端使用的一种记录客户端状态的机制。客户端浏览器访问服务器时，服务器把客户端信息以某种形式记录在服务器上。这就是`Session`。客户端浏览器再次访问时只需要从该`Session`中查找该客户的状态就可以了

## Session的生命周期

`Session`生成后，只要用户继续访问，服务器就会更新Session的最后访问时间，并维护该Session。用户每访问服务器一次，无论是否读写Session，服务器都认为该用户的Session活跃了一次。

## Session的有效期

为防止内存溢出，服务器会把长时间内没有活跃的Session从内存删除。这个时间就是Session的超时时间。如果超过了超时时间没访问过服务器，Session就自动失效了。

# webStorage

`webstorage`是本地存储，存储在客户端，包括`localStorage`和`sessionStorage`。

`localStorage`生命周期是永久

`sessionStorage`仅在当前会话下有效，关闭页面或浏览器后被清除。

`localStorage`和`sessionStorage`使用时大致相同：

```js
	localStorage.setItem("key","value");         //以“key”为名称存储一个值“value”
    localStorage.getItem("key");                 //获取名称为“key”的值
    localStorage.removeItem("key");              //删除名称为“key”的信息。
    localStorage.clear();                        //清空localStorage中所有信息
```

## 作用域不同

不同浏览器无法共享`localStorage`或`sessionStorage`中的信息。相同浏览器的不同页面之间可以共享`localStorage`，但是不同页面或标签间无法共享`sessionStorage`的信息。