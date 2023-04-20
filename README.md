# openwrt_auto_cf

OpenWRT中自动优选CloudFlare IP的脚本，包含PassWall和shadowsocksR Plus

首先ssh进openwrt中

可以用uci命令查看配置项
```bash
uci show shadowsocksr
```
or
```bash
uci show passwall
```

下载脚本
```bash
wget https://raw.githubusercontent.com/chris-ss/openwrt_auto_cf/main/ssrp.sh
```
or
```bash
wget https://raw.githubusercontent.com/chris-ss/openwrt_auto_cf/main/passwall.sh
```

给脚本权限并执行测速都能正常运行
```bash
chmod +x ssrp.sh && bash ssrp.sh
```

检测正常后添加到openwrt后台-系统-计划任务
```bash
0 4 * * 3,6 bash /root/ssrp.sh > /dev/null
```
注意/root/ssrp.sh为实际你存放脚本的路径。
0 4 * * 3,6的意思是在每周三、周六的凌晨4点会自动运行一次。
