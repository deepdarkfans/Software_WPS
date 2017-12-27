# WPS 安装方法

## libpng12

因为 wps 依赖于libpng12，Ubuntu 17.10 高于这个版本，所以如果是 17.10 就将这个包安装，如果是16.04可以不装，未来的新版本有可能就不存在这个依赖了（个人觉得这个算是bug）。

```shell
sudo dpkg -i libpng12-0_1.2.54-1ubuntu1_amd64.deb
```

## WPS 依赖的字体

```shell
sudo unzip wps_symbol_fonts.zip -d /usr/share/fonts/wps-office
```

## 安装 WPS

#### apt 安装

在线安装的是 9.1，不过基本也够用了

```shell
sudo apt install wps-office
```

#### 官方下载最新版本

也可以去 [官方](http://wps-community.org/downloads) 下载最新版本

```shell
wget http://kdl1.cache.wps.com/ksodl/download/linux/a21//wps-office_10.1.0.5707~a21_amd64.deb
sudo dpkg -i wps-office_10.1.0.5707_a21_amd64.deb
```