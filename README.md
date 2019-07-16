eureka-server 注册中心 demo 整理  
eureka整理点：  
         1、集群  
         2、单点  
         3、控制面板权限控制  



# 解决Eureka Server不剔除已关停的节点的问题  
server端配置： 
eureka:  
    server:  
        # 设为false，关闭自我保护主要  
        enable-self-preservation: false  
        # 清理间隔（单位毫秒，默认是60*1000）  
        eviction-interval-timer-in-ms: 4000  
client配置：    
eureka:   
    client:  
      #开启健康检查（需要spring-boot-starter-actuator依赖）
      healthcheck:  
        enabled: true  
    instance:  
        lease-renewal-interval-in-seconds: 10  
        lease-expiration-duration-in-seconds: 30  
