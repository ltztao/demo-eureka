eureka-server 注册中心 demo 整理  
eureka整理点：  
&emsp;&emsp;&emsp;1、集群   
&emsp;&emsp;&emsp;2、单点    
&emsp;&emsp;&emsp;3、控制面板权限控制    



# 解决Eureka Server不剔除已关停的节点的问题  
server端配置：  
eureka:  
&emsp;&emsp;server:  
&emsp;&emsp;&emsp;# 设为false，关闭自我保护主要  
&emsp;&emsp;&emsp;enable-self-preservation: false  
&emsp;&emsp;&emsp;# 清理间隔（单位毫秒，默认是60*1000）  
&emsp;&emsp;&emsp;eviction-interval-timer-in-ms: 4000  
client配置：    
eureka:   
&emsp;&emsp;client:  
&emsp;&emsp;&emsp;#开启健康检查（需要spring-boot-starter-actuator依赖）  
&emsp;&emsp;&emsp;healthcheck:  
&emsp;&emsp;&emsp;&emsp; enabled: true  
&emsp;&emsp;instance:  
&emsp;&emsp;&emsp;lease-renewal-interval-in-seconds: 10  
&emsp;&emsp;&emsp;lease-expiration-duration-in-seconds: 30  
