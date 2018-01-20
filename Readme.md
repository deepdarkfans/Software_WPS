# WPS 安装方法

## libpng12

因为 wps 依赖于libpng12，Ubuntu 17.10 高于这个版本，所以如果是 17.10 就将这个包安装，如果是16.04可以不装，未来的新版本有可能就不存在这个依赖了（个人觉得这个算是bug）。

```shell
sudo dpkg -i libpng12-0_1.2.54-1ubuntu1_amd64.deb
```


## 安装 WPS

本镜像中已经包含了 wps 的安装包（因为官网有时会下载很慢，所以增加了安装包），暂时是最新的（2018-01-20 ），可以先去官网查看下，如果有最新的最好安装最新版本。

推荐使用 apt 安装的版本，有点太老了，而且还是 32 位的，还有各种问题，推荐去[官方](http://wps-community.org/downloads) 下载最新版本

```shell
wget http://kdl1.cache.wps.com/ksodl/download/linux/a21//wps-office_10.1.0.5707~a21_amd64.deb
sudo dpkg -i wps-office_10.1.0.5707_a21_amd64.deb
```

## WPS 依赖的字体

字体是从 Win7 中提取出来的，字体有点多，为了去兼容Windows下的WPS文档，就没有去除，全盘接收了。
为了提升传输的速度，将每一个字体都通过 gzip 压缩了，所以要先将 wps-office 中的字体文件解压缩之后再复制。

```shell
gzip -r -d wps-office/
sudo cp -r wps-office /usr/share/fonts/
```