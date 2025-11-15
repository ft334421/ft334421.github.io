[视频教程](https://www.bilibili.com/video/BV1CYkXBfE77?t=1.8)
```
sudo -i

mkdir /home/ft334421

chown -R ft334421:1001 /home/ft334421

上述中的“ft334421”替换为自己的飞牛管理员账号名

apt updateapt 

apt install cinnamon

dpkg-reconfigure locales

apt install ibus-libpinyin

cd /tmp

wget https://gitee.com/spark-store-project/spark-store/releases/download/4.5.2/spark-store_4.5.2-2_amd64.deb

wget http://share.geekxw.top/spark-store_4.5.2-2_amd64.deb

apt install ./spark-store_*_amd64.deb

```
如何设置Debian图形启动或命令行界面启动？
By :[ Will](https://www.cmdschool.org/archives/author/dgadmin) 2023-08-31 Category : [Debian-Like](https://www.cmdschool.org/archives/category/operating-systems/debian-ubuntu)

Debian-Like
1 前言
一个问题，一篇文章，一出故事。
笔者经常默认图形界面启动或默认命令行启动的设置命令，于是整理处理，以便查询。

2 最佳实践
**2.1 查询当前的启动模式**
`systemctl get-default`
**2.2 设置为默认命令行界面启动**
`systemctl set-default runlevel3.target`
或者，你也可以使用如下等价命令，

`systemctl set-default multi-user.target`
或者，你也可以使用如下等价命令，

```
rm /etc/systemd/system/default.target
ln -s /usr/lib/systemd/system/multi-user.target /etc/systemd/system/default.target
```
**2.3 设置为默认图形界面启动**
`systemctl set-default runlevel5.target`
或者，你也可以使用如下等价命令，

`systemctl set-default graphical.target`
或者，你也可以使用如下等价命令，

```
rm /etc/systemd/system/default.target
ln -s /usr/lib/systemd/system/graphical.target /etc/systemd/system/default.target
```

