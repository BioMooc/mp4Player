简易播放mp4的视频网站

目的: 方便录制的视频的保存和分享

使用方法

1. git clone 本站所有文件都放到一个文件夹下:
$ pwd
/home/wangjl/data/mp4Player

$ tree
.
├── 0.png
├── clip #不保存mp4文件
│   ├── clip_2020_10_15_11_37_48_7-Nolan.mp4
│   ├── clip_2020_10_15_15_31_26_933-Quake.mp4
│   ├── clip_2020_10_15_16_14_59_372-Sarah_Teichmann.mp4
│   ├── clip_2020_10_15_16_43_30_515-Sten_Linnarsson.mp4
│   ├── clip_2020_10_15_17_54_06_418-FuChou_Tang.mp4
│   └── 屏幕捕获_2020_10_15_16_09_24_462.png
├── index.html
├── jwplayer
│   ├── jwplayer.flash.swf
│   ├── jwplayer.html5.js
│   └── jwplayer.js
├── mp4Player2.html
└── mp4Player.html


2. 服务器配置 
都是静态资源，服务器使用 Ubuntu 下的 nginx

$ sudo vim /etc/nginx/conf.d/demo1.conf
server{
  listen 5000;
  server_name 192.168.2.120;
  location / {
    root /home/wangjl/data/mp4Player/;
    index index.html;
  }
}


$ sudo nginx -s reload 



3. 可以通过IP访问了
http://y.biomooc.com:5000/



本次会议的笔记记录位置: https://github.com/DawnEve/txtBlog/issues/10



ref:
mp4 屏幕视频录制使用 oCam: https://ocam.en.softonic.com/ 
播放器基于 jwplayer: https://www.jwplayer.com/
	https://www.jwplayer.com/developers/web-player-demos/adaptive-streaming/
界面参考 imooc.com
