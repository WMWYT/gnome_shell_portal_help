# gnome_shell_portal_help

## 编译

``` bash
meson build
```

## 安装

最好先备份原来系统中的gnome-shell-portal-help，我的系统是Ubuntu 22.04.4 LTS x86_64，gnome-shell版本42.9，使用前请确保系统中安装有gio。

```bash
cd /usr/libexec
sudo cp gnome-shell-portal-help gnome-shell-portal-help-back
sudo rm gnome-shell-portal-help
sudo cp [program directory]/build/src/gnome-shell-portal-help ./
```

## 说明

这个项目只是按照gnome-shell工程中的gnome-shell-portal-help修改了一下，希望gnome团队可以修改一下gnome-shell-portal-help，让其支持使用系统中默认浏览器开启网络认证的页面，WebKit是不错，但使用Gjs构建的浏览器没有记住密码的功能。
