# docker 配置相关

Docker的默认配置文件位于 `/etc/docker/daemon.json`

```
当前配置
{
    "builder": {
    "gc": {
      "defaultKeepStorage": "20GB",
      "enabled": true
    }
  },
  "default-runtime": "nvidia",
  "experimental": false,
  "max-concurrent-downloads": 1,
  "max-download-attempts": 10,
  "registry-mirrors": [
    "https://docker-proxy.741001.xyz","https://registry.docker-cn.com"
  ],
"runtimes": {
        "nvidia": {
            "args": [],
            "path": "nvidia-container-runtime"
        }
    }
}
```

[ 深入探索 Docker ：高阶操作与配置设置](https://blog.csdn.net/stromboli/article/details/142553089))
