FROM java:8
ENV MYPATH /home/zcq/docker-compose
WORKDIR $MYPATH
# 将本目录下的jar包和application.yml复制到容器/home/zcq/docker-compose目录下
ADD *.jar ./docker-compose-app.jar
ADD *.yml ./application.yml
# 容器启动运行jar包
ENTRYPOINT ["java", "-jar", "./docker-compose-app.jar"]