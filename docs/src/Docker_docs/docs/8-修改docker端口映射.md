# 给已存在的docker容器修改端口映射

## 1. 修改配置文件

1. systemctl stop docker                                                         // 停止docker服务

2. find / -name hostconfig.json                                                 // 罗列出所有容器的配置文件

3. cd /docker/containers/hb3clkejfijfaofhdklfadjslj123123k43   // 进入指定容器的目录

4. vim hostconfig.json                                                               // 编辑容器的配置文件

5. 找到“PortBindings”字段，如下所示：
   
   ```
   "PortBindings":{
    "80/tcp": [{ //容器内端口
    "HostIp": "",
    "HostPort": "82" //宿主机端口
    }]
   }
   修改对应端口号
   ```

6. vim config.v2.json

7. 修改ExportPorts

8. systemctl daemon-reload

9. systemctl start docker

## 通过主机的iptables

- **添加端口映射**
  
  ```
  a, 获取容器ip  
      docker inspect $container_name | grep IPAddress
  b. 添加转发规则  
      iptables -t nat -A DOCKER -p tcp --dport $host_port -j DNAT --to-destination $docker_ip:$docker_port  
  ```

```
- **删除端口映射规则**
```

```

```
