### Elasticsearch 记录


#### 单节点启动

启动一个单一的节点进行命令的测试和管理,当前版本 ES 版本6.2.2, Kibana 6.2.2 

Kibana自5版本后,包含了原有Sense插件的功能到Console.直接执行命令即可

```
cd single-node-env-bootup
docker-compose up
```

直接通过```http://localhost:5601/app/kibana#/dev_tools/console?_g=()```即可进入console对于es进行管理.


#### 多节点启动

请确保最大的**max_map_count**不要设置的太低如果太低,将启动不了es服务器,docker主机需要进行如下配置

```
vi /etc/sysctl.conf 
vm.max_map_count=655360

sysctl -p
```

再次进入cluster-nodes-env-bootup中启动```docker-compose up```