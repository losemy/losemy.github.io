



### 负载均衡


### 扩展Filter


### 异步调用异常处理
>> 通过回调机制处理

#### 异步调用问题处理

1. 异常处理
2. RpcContext处理，即怎么传递上下文

### 客户端2.7.1 dubbo-admin 2.7.3 问题 
metadata 路径发生改变

服务提供者生成 meatadata路径
2.7.1 是 /dubbo/metadata/com.github.losemy.simple.facade.UserFacade/provider/simple/service.data
2.7.3 是 /dubbo/metadata/com.github.losemy.simple.facade.UserFacade/provider/simple

### dubbo层次划分
- service层，接口层，主要提供给服务提供者和消费者俩实现
- config层，配置层，主要是对dubbo进行各种配置
- proxy层，代理层，接口服务透明化，生成服务的客户端stub和服务端skeleton
- registry层，服务注册层，负责服务的注册与发现
- cluster层，集群层，封装多个服务提供者的路由以及负载均衡，将多个实例组合成一个服务
- monitor层，监控层，对rpc接口的调用次数，以及调用时间进行监控
- protocol层，远程调用层，封装rpc调用
- exchange层，信息交换层，封装请求响应模式，同步转异步
- transport层，网络传输层，抽象mina和netty为统一接口
- serialize层，数据序列化层，网络传输需要
- 

### dubbo负载均衡
- Random LoadBalance（基于权重的随机均衡机制）
- RoundRobin LoadBalance（不推荐，基于权重的轮询负载均衡机制）
- LeastActive LoadBalance（最少活跃度）
- ConsistentHash LoadBalance（一致性hash，相同参数的请求总是发到同一提供者）