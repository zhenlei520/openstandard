# 六大原则：

### 1. <a href="https://blog.csdn.net/qq_34482621/article/details/103595638" target ="_blank">单一职责原则（Single Reponsibility Principle，SRP）</a>

    一个类只负责一项职责。换种说法，就一个类而言，应该只有一个引起它变化的原因

### 2. <a href="https://blog.csdn.net/qq_34482621/article/details/103596486" target ="_blank">里氏替换原则（Liskov Substitution Principle，LSP）</a>

    所有使用基类的地方，都可以使用其子类来代替，而且行为不会有任何变化

### 3. <a href="https://blog.csdn.net/qq_34482621/article/details/103599552" target ="_blank">依赖倒置原则（Dependence Inversion Principle，DIP）</a>

    高层模块不应该依赖低层模块，两者都应该依赖其抽象，不要依赖细节（IOC是依赖反转的具体实现）

### 4. <a href="https://blog.csdn.net/qq_34482621/article/details/103611656" target ="_blank">接口隔离原则（Interface Segregation Principe，ISP）</a>

    类的依赖关系应建立在最小接口上，不要都塞在一起。即客户端不应该依赖它不需要的接口

    接口隔离原则就是要求只提供尽可能小的接口，需要高内聚，不需要的行为要隐藏起来

    接口尽量小，但是要有限度。对接口进行细化可以提高程序设计灵活性是不挣的事实，但是如果过小，则会造成接口数量过多，使设计复杂化。所以一定要适度。

    为依赖接口的类定制服务，只暴露给调用的类它需要的方法，它不需要的方法则隐藏起来。只有专注地为一个模块提供定制服务，才能建立最小的依赖关系。

    提高内聚，减少对外交互。使接口用最少的方法去完成最多的事情。

### 5. <a href="https://blog.csdn.net/qq_34482621/article/details/103613573" target ="_blank">迪米特法则（Law of Demeter，LOD）</a>

    又叫最少知道原则，一个对象应尽可能少的了解其它对象

### 6. <a href="https://blog.csdn.net/qq_34482621/article/details/103616713" target ="_blank">开闭原则（Open Closed Principle，OCP）</a>

    一个软件实体应当对扩展开放，对修改封闭

<a href="https://tianweili.github.io/2015/02/15/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E5%85%AD%E5%A4%A7%E5%8E%9F%E5%88%99-%E5%BC%80%E9%97%AD%E5%8E%9F%E5%88%99/" target="_blacnk">开闭原则 1</a>