# 解码格式
Vorbis 比特流是以三个数据包头开始的。这些头数据包按顺序依次是：

- The identification header、
- The comment header
- 设置数据包

这些都与解码 Vorbis 音频文件密切相关的。
## 包头
每个数据包都是以同样的十六进制头结构开始的：
```
'v'  'o'  'r'  'b'  'i'  's' 
0x76 0x6f 0x72 0x62 0x69 0x73
```
