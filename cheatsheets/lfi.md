## LFI 本地文件包含

**过滤器绕过**

```
../\
```

```
..\/
```

```
/..
```

```
\/..
```

```
/%5c..
```

***FFmpeg本地文件泄露**

这个 [script](https://github.com/neex/ffmpeg-avi-m3u-xbin/blob/master/gen_xbin_avi.py) by @neex 能用来在FFmpeg发现本地文件，参考[HLS playlists](https://ffmpeg.org/ffmpeg-formats.html#hls-2).

_复现步骤_

1. 下载@neex脚本
2. 用你测试的参数执行脚本: `python3 gen_xbin_avi.py file:///etc/hostname bugbounty.avi`
3. 将生成的AVI文件上传到目标站点(例如在“视频上传页面”内)
4. 目标可能在服务器端处理包含FFmpeg的恶意HLS。
5. 通过目标站点播放上传的AVI。如果成功，您想要的文件将在视频中公开。

存在其他脚本，它们可能生成不同的HLS格式，或者导致以不同的方式公开所需的文件。

**Blogs**
* http://pastie.org/840199
* http://websec.wordpress.com/2010/02/22/exploiting-php-file-inclusion-overview/
* http://www.notsosecure.com/folder2/2010/08/20/lfi-code-exec-remote-root/?utm_source=twitterfeed&utm_medium=twitter
* http://labs.neohapsis.com/2008/07/21/local-file-inclusion-%E2%80%93-tricks-of-the-trade/
* http://www.digininja.org/blog/when_all_you_can_do_is_read.php
