# Juntaran.me

博客源码，由 hexo 生成，使用 yilia 主题  
搭建于 138.128.206.71 ，使用 nginx 作为服务器  

```
    hexo g
    hexo s -p 5000
```

使用 hexo 生成博客后，需要修改 index.html  

在 92 行 `</div>` 后添加以下代码，该代码为 gostats 的访问计数器  

```html
<div class="social">
    <!-- GoStats Simple HTML Based Code -->
        <a target="_blank" title="Juntaran.me's hit"
            href="http://Juntaran.me"><img alt="web site traffic statistics"
            src="//www.gostats.org/0.png?a=100493712&ct=4&ci=82" style="border-width:0" />
        </a>
    <!-- End GoStats Simple HTML Based Code -->
</div>
```

之后上传至 Github 后，登录 138.128.206.71 服务器  

```bash
    cd $NGINX/html
    ./update.sh
```

该脚本下载 Github 最新源码并解压覆盖源文件  


综合以上脚本代码：

```bash
#!/bin/bash

##########################################
#   Author: Juntaran
#   Email: Jacinthmail@gmail.com
#   Date: Thu 20 Jul 2017 02:23:04 PM EDT
##########################################

set -o errexit    # 如果有命令运行失败让脚本退出执行
set -o nounset    # 若有用未设置的变量即让脚本退出执行

#if [[ "$EUID" -ne 0 ]]; then    # check root
#    echo 'Root Required' 
#    exit 1
#fi

rm -rf *.zip
rm -rf public/

wget -O Juntaran.me.zip https://codeload.github.com/Juntaran/Juntaran.github.io/zip/master
unzip Juntaran.me.zip
mv Juntaran.github.io-master/ public/

```


* [Juntaran.me](http://Juntaran.me)