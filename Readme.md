File Structure:
    docker-compose
        - app  
          -  Dockerfile    <!-- 构建Springboot服务的docker镜像  -->
          -  application.yml    <!-- Springboot配置文件,在生成镜像时放置在jar包同目录,覆盖jar包内配置，主要用于配置mysql和redis  -->
          -  redis-mysql-0.0.1-SNAPSHOT.jar    <!-- Springboot服务jar包  -->
        - grafana
          - conf    <!-- grafana初始化时的配置文件,位于镜像内/usr/share/grafana/conf,此文件在初始化grafana时不能被修改  -->
          - grafana    <!-- grafana的配置文件目录,通过容器卷覆盖镜像内的/etc/grafana实现自定义配置grafana  -->
            - provisioning    <!-- 初试化配置  -->
              - dashboards
                - sample.yml    <!-- grafana启动时加载dashboard  -->
              - datasources 
                - sample.yml    <!-- grafana启动时加载数据源  -->
            - grafana.ini    <!-- grafana用户的配置文件,覆盖defaul.ini  -->
        - docker-compose.yml     <!-- docker-compose配置文件  -->