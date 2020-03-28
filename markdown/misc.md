# Misc
安全杂项


## 二级分类
- Recon
- Encoding
- <span class="fragment highlight-blue">**Forensic**</span>
- Stego
- ...


## Recon
信息收集

- 搜索引擎
- Google Hacking
- 社会工程学
- 网站/域名/IP


## Encoding
编码分析

- Morse
- Base64
- 电子信息相关
    - Manchester
- Web相关
    - URL编码
    - Unicode
    - HTML实体


- 生活相关：
    - 条形码
    - 二维码
- 古典密码
    - 单表替换
    - 多表替换
    - ...



## Stego
隐写分析

- 末尾藏文件
    - 010editor
    - winhex
    - `file`
    - `strings`
    - binwalk
    - foremost


### 图片隐写
- Meta
- 像素RGB
- LSB
- PNG
    - `89 50 4E 47`
    - IHDR CRC爆破长/宽
    - alpha
- JPG
    - `FF D8`
    - exif


- GIF
    - `GIF89a`
    - 帧分离（空间隐写）
    - 时间隐写
- 双图隐写
    - 运算
    - 盲水印


### 压缩包隐写
- 弱密码爆破 ARCHPR
- 伪加密
- ZIP
    - CRC32爆破
- RAR
    - WinRAR


### 音视频隐写
- MP3
    - MP3Stego
- 波形/频谱
    - Audacity/Cool edit
- LSB
    - Silenteye


## Forensic
电子取证


### 磁盘/内存取证
- 磁盘分区格式
    - FAT12/16/32
    - NTFS
    - EXT2/3/4
- 加密磁盘
- VMDK
- 内存dump文件
    - Volatility


### 流量分析
- Wireshark
- <span class="fragment highlight-blue">**计算机网络**</span>
- 过滤器
- 协议/IP/端口/字符串
- 数据提取
    - tshark