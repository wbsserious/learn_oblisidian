1. miniconda（版本控制）
	注意。如果可以，conda的环境配置相关的内容不要装在系统盘中
2. mihomo（翻墙使用）
	1. 下载：https://github.com/MetaCubeX/mihomo windows中下载通过final shell推到linux系统中
	2. 配置连接：
		wget -O ~/.config/mihomo/config.yaml "你的Clash订阅链接"
		具体使用方式：
	```linux
	终端1
	mihomo -d ~/.config/mihomo
	终端2
	export http_proxy=http://127.0.0.1:7890
	export https_proxy=http://127.0.0.1:7890
	curl -I https://www.google.com
	```
3. tailscale（稳定IP端口）
4. git（拉取相应的模型和库）
5. docker 
	！！安装docker时将docker目录调整到挂载盘目录！！
