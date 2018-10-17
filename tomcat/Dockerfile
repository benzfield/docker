FROM tomcat:7-jre8

# 添加服务的war包
RUN rm -rf /usr/local/tomcat/webapps/*

# 更新tomcat的server配置
COPY server.xml /usr/local/tomcat/conf/server.xml

# 支持sigar
COPY libsigar-amd64-linux.so /usr/local/lib

# 更新ldconfig的cache
RUN ldconfig 
