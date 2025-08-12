README.md
=========

add-swap-5gb
------------

一键给 Ubuntu 服务器添加 **5 GiB** swapfile 的脚本，零依赖、可复制粘贴即用。

### 功能
- 自动创建 5 GiB 的 `/swapfile`  
- 设置权限、格式化、立即启用  
- 写入 `/etc/fstab`，重启后仍然有效  
- 重复执行会自动检测并退出，防止误操作  

### 快速开始
```bash
# 下载脚本
curl -O https://raw.githubusercontent.com/XTBANNY/add-swap-5gb/main/add-swap-5g.sh

# 赋予执行权限
sudo chmod +x add-swap-5g.sh

# 运行（必须使用 root）
sudo ./add-swap-5g.sh
```

### 一键脚本
```bash
# 下载脚本
bash <(curl -fsSL https://raw.githubusercontent.com/XTBANNY/add-swap-5gb/main/add-swap-5g.sh)



### 验证结果
```bash
swapon --show
free -h
```

### 卸载 / 恢复
如果你不再需要该 swapfile：
```bash
sudo swapoff /swapfile
sudo rm /swapfile
sudo sed -i '\|^/swapfile|d' /etc/fstab
```

### 兼容性
- Ubuntu 18.04 / 20.04 / 22.04 / 24.04  
- Debian 10+（未严格测试，理论上通用）  

### 许可证
MIT © XTBANNY
