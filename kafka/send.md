## 生产者发送消息的方式
1.发送并忘记(fire-and-forget)
2.同步发送
3.异步发送

### 发送并忘记(fire-and-forget)
把消息发送给服务器，但并不关心它是否正常到达，大多数情况下，消息会正常到达，因为kafka是高可用的，
而且生产者会自动尝试重发，不过使用这种方式有时会丢失一些数据

### 同步发送
同步发送消息，会返回一个Futrue对象，调用get()方法进行等待，就可以知道是否发送成功

### 异步发送
调用send接口发送，并指定一个回调函数，服务器在返回响应时调用该函数