# 异常处理原则如下：

### 1. 永远不要直接抛出Exception异常

    使用具体异常类或自定义异常类，避免抛出Exception异常。每个异常代表的意义不同，一概使用同一个异常类会给上层捕获异常造成不必要的困难

### 2. 异常要携带足够多的信息

    if (!this._userQueryRepository.Any(user => user.Id == userId))
    {
        throw new NullReferenceException();													      ×
        throw new NullReferenceException(string.Format("Id为\"{0}\"的用户不存在！", userId));		√
    }
### 3. 只能处理可以处理的异常

    底层抛出的异常，上层如果无法处理，那么可以选择不处理（不加try/catch）或重新抛出（加try/catch后再throw）
    
    切忌捕获了异常却什么都不做，这样会给程序带来无法预料的严重问题

### 4. 尽量使用.NET自带的异常类，必要时才自定义异常

    SystemException 其他用户可处理的异常的基本类

    ArgumentException 方法的参数是非法的

    ArgumentNullException 一个空参数传递给方法，该方法不能接受该参数

    ArgumentOutOfRangeException 参数值超出范围

    ArithmeticException 出现算术上溢或者下溢

    ArrayTypeMismatchException 试图在数组中存储错误类型的对象

    BadImageFormatException 图形的格式错误

    DivideByZeroException 除零异常

    DllNotFoundException 找不到引用的DLL

    FormatException 参数格式错误

    IndexOutOfRangeException 数组索引超出范围

    InvalidcastException 使用无效的类

    InvalidOperationException 方法的调用时间错误

    MethodAccessException 试图访问思友或者受保护的方法

    MissingMemberException 访问一个无效版本的DLL

    NotFiniteNumberException 对象不是一个有效的成员

    NotSupportedException 调用的方法在类中没有实现

    NullReferenceException 试图使用一个未分配的引用

    OutOfMemoryException 内存空间不够

    PlatformNotSupportedException 平台不支持某个特定属性时抛出该错误

    StackOverflowException 堆栈溢出

### 5. 服务层异常必须抛出FaultException、FaultException<T>或其子类

    服务层涉及远程调用，普通的异常类无法将异常消息传递给远程客户端，所以必须抛出FaultException、FaultException<T>或其子类
    
    服务层自定义异常亦必须要继承自FaultException或FaultException<T>，一般用于WCF的远程调用抛出

### 6. 不要试图返回特殊的数字或字符串代替异常

    public int CreateProject(string projectName)
    {
        if (string.IsNullOrWhiteSpace(projectName))
        {
            throw new ArgumentNullException("projectName", @"项目名称不可为空！");		√
            return -1;																  ×
        }
    }
