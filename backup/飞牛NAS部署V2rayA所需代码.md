Notion文档著名：InfiCheesy无限芝士

视频教程地址：https://www.youtube.com/watch?v=QCGU4S3tSu0

IP:2017进入
```
version: '3.8'             # docker-compose 文件语法版本

services:
  v2raya:                  # 服务名字（随便起）
    image: mzz2017/v2raya  # 镜像名，来自 docker hub
    restart: always        # 自动重启策略，容器挂了会重新拉起
    container_name: v2raya # 容器名字，等价于 `--name v2raya`
    
    network_mode: host     # 使用宿主机网络（端口直接绑定到宿主机）
    privileged: true       # 提升权限，方便操作 iptables 等

    cap_add:               # 增加额外能力（比 privileged 更细粒度）
      - NET_ADMIN          # 网络管理权限
      - SYS_MODULE         # 加载内核模块权限
    volumes:
      - ./etc:/etc/v2raya  # 把当前目录下的 ./etc 映射到容器里的 /etc/v2raya
                           # 用来存放 v2raya 的配置文件，重启不会丢
```