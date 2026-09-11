## 如何进入背包后台

### 有线连接

1、首先，将PC机IP设置成192.168.5.xxx

2、进入背包后台

```sh
$ ssh robot@192.168.5.20
```



## 如何使用无线网卡

### 无线连接（STA）

1、有线连接进入背包后台，连接无线热点

```sh
nmcli device wifi connect "wifi名" password "wifi密码"
```

2、拔掉网线，PC通过连接公共网络可找到背包

### 无线连接（AP）

1、有线连接进入背包后台，打开无线热点

```sh
$ sudo nmcli device wifi hotspot ifname wlP1p1s0 con-name MyHotspot ssid "wifi名" password "wifi密码" band bg channel 6
```

2、拔掉网线，PC开启即可无线连接到"wifi名"热点

3、进入背包后台（IP不变）

```sh
$ ssh robot@192.168.5.20
```



## 如何查看背包版本号

进入背包后台后查询

```sh
$ cat /etc/image-version
```



## 如何查看本体和背包的话题信息

进入背包后台后查询，执行以下命令可查询到所有ros2信息

```sh
$ ros2 topic list
```

> 如果要看本体信息，需要确保背包已于本体连接

