# 开发基本原则

### 1. 业务至上，客户至上

    开发是为业务服务，以业务为中心、客户为中心思考问题
    
    最大的忌讳是不顾及客户需求陷入技术思维是调整产品

    遇到客户反馈问题时，首先对客户表示抱歉，并请求获得客户的理解，之后抓紧时间调整解决问题。

    不要轻易索要客户的账户密码等私密信息，客户的数据是客户的私有财产，操作时要慎之又慎

### 2. 任务按时按质量完成。
    
    任务必须按时按质量完成且不能对原有项目的稳定性造成影响。

### 3. 当遇到性能跟工作时间成反比的情况下，优先选择性能。

    如果当你遇到一件难题，需要你消耗自己更多的时间去完成，但是做成后会对性能有很大程度的提升，

    那么热爱技术、优秀的你应该去尝试优化性能，本着对自己、对客户负责任的态度去优化它（如果与

    开发周期产生冲突时可以放置到第二轮进行优化，但一定要去优化下去），我们相信优秀的你不可能

    愿意放任这样低性能的产品给客户去使用。

### 4. 项目中应该以更少的性能消耗、最快的速度将结果返回给调用方或者客户。

    开发中尽量避免循环式调用查询数据库，或者循环式调用查询缓存等，尽量减少网络带宽消耗，在缓存
    
    与内部请求需要二选一时，优先使用缓存。

### 5. 在项目中不要太过于相信你的调用方。

    如果你的接口需要有权限才能访问，一定要对接口进行鉴权，不要觉得你的调用方一定是安全可靠的。

    在项目中，对所有空异常的数据提前做好验证，在程序上必须要保证安全可靠

