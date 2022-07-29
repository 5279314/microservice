# 修改参数
1. 将ip全部修改为域名的形式,根域名为od.com 数据库（mysql.od.com）
2. 数据库导入更新，不需要创库即可直接导入sql文件
3. 修改了数据库用户：shoping 密码：123456

    ```shell
create user 'shoping'@'%' identified by '123456';
grant select,update,insert on tb_product.* to 'shoping'@'%';
grant select,update,insert on tb_order.* to 'shoping'@'%'; 
grant select,update,insert on tb_stock.* to 'shoping'@'%'; 
```

# 创建镜像

## 安装编译环境所需软件maven

```shell
wget -O /etc/yum.repos.d/CentOS-Base.repo https://mirrors.aliyun.com/repo/Centos-7.repo
sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentOS-Base.repo
wget -O /etc/yum.repos.d/epel.repo http://mirrors.aliyun.com/repo/epel-7.repo
yum -y install maven
```

## 进入k8s目录中

```shell
cd cd simple-microservice/k8s/
sh docker_build.sh
```

# 查看镜像

登录harbor.od.com中查看

```shell
kubectl apply -f .
```

# 相关域名解释
镜像仓库地址 http://harbor.od.com
eureka域名 http://eureka.od.com
前端节点 http://portal.od.com
后端节点 http://gateway.od.com
数据库 mysql.od.com
