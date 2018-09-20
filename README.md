
<h1 align="center"> 免责声明 </h1>


<p align="center">
只面向海外华人用户且仅供科研学习之用，切勿用于其他用途(你用于其他用途我拦不住a =.=||)
<br>
中国居民请自觉关闭本项目并24小时之内删掉与本项目相关的一切内容，否则出现一切问题，项目作者概不负责
（我为什么要对你负责a 再说我也不想让你用于其他用途）
</p>
<hr>



# v2ray 部署在 openshift starter
openshift: 内存设置为256M，每 project 可配置 4 Pods。



Docker 镜像搜索：2822590253/osv2y       OR         doudoubing/cundang 2选1都能用
（fork于wangyi2005/v2ray修改前）

环境变量： CONFIG_JSON（配置）、后面这个填（

{
  "log": {
    "loglevel": "warning"
  },
  "inbound": {
    "protocol": "vmess",
    "port": 8080,
    "settings": {
      "clients": [
        {
          "id": "uuid随机生成网址：https://www.uuidgenerator.net/",
          "alterId": 64,
          "security": "aes-128-cfb OR aes-128-gcm OR chacha20-poly1305 3选1，不用自己手打了，舒服吧"
        }
      ]
    },
    "streamSettings": {
      "network": "ws"
    }
  },
  "inboundDetour": [],
  "outbound": {
    "protocol": "freedom",
   "settings": {}
  }
}

）


用notepad++将上述变量中 \r\n 替换为\\n，变成一行，导入容器。
(帮你们省去这一步骤了)

客户端： android Actinium、windows v2ray 可用同一个服务端。
（我用的安卓v2rayNG，下载网址：https://github.com/2dust/v2rayNG/releases
文件名：app-arm64-v8a-release.apk）

大佬豆豆兵tech的youtube频道，我就是Fork一下，描述改一下，再Docker一下：https://www.youtube.com/channel/UClceV39J1Z_9D4_mHkBZrMg

