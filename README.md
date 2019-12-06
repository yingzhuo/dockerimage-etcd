# dockerimage-etcd

**警告**: ⚠️ 本项目并没有经过严格测试，不可用于生产环境。

### 单节点

```yaml
version: "3.7"

services:
  etcd:
    image: "registry.cn-shanghai.aliyuncs.com/yingzhuo/etcd2:v3.3.18"
    container_name: "etcd"
    restart: "always"
    ports:
    - "2379:2379"
    - "2380:2380"
    volumes:
    - "${PWD}/data/:/var/lib/etcd/"
    environment:
    - "ETCD_ADVERTISE_CLIENT_URLS=http://10.211.55.2:2379"
```
