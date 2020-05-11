# 命名规范如下：

&ensp;&ensp;&ensp;&ensp;命名基本原则：
    
    1）. 看词识意（写出人能读懂的代码），命名要有意义，无需对命名本身进行注释，尽量少用匈牙利命名法。
    2）. 对于类的成员变量，多用this关键字，增强代码可读性，例如：

        public class Person
        {
            protected string _name;
            public virtual string SayHello()
            {
                return string.Format(“你好，我叫{0}”, this._name);
            }
        }

    3）. 对于基类的成员变量，多用base关键字，增强代码可读性，例如：

        public class Student : Person
        {
            public override string SayHello()
            {
                return string.Format(“你好，我叫{0}，我是一名学生”, base._name);
            }
        }

&ensp;&ensp;&ensp;&ensp;目前项目中大多采用两种命名规则：

    1）. Camel命名法（骆驼峰命名法：第一个单词以小写字母开始；第二个单词的首字母大写）
    2）. Pascal命名法（帕斯卡命名法：由二个或二个以上单词连结在一起，每个单词首字母大写）

### 1. 命名空间采用Pascal命名法，基本规则为“项目名.技术模块名.业务模块名…”，最末级命名空间单词应为名词复数形式，例如：

    namespace DYCloud.Domain.Supplier { }

    namespace DYCloud.Domain.Supplier.Entities { }

    namespace DYCloud.Repository.Supplier.Commands { }

### 2. 类命名采用Pascal命名法，并且对应英文单词的名词单数形式，例如：

    public class Person { }
    
    public struct Point { }

    public enum HttpMethod { }

### 3. 接口采用I + Pascal命名法

    public interface IEnumerable { }
    
    public interface IDisposable { }
    
    public interface IRepository { }
    
    public interface IService { }

### 4. 字段、属性与方法规范

    1. 私有实例字段采用_ + Camel命名法。

        private readonly string _userName;
        
        private readonly string _password;

    2. 私有静态字段采用_ + Camel命名法。

        private static string _staticField;

        private static string _staticField;

    3. 公有实例字段采用Pascal命名法

        public string PublicField;
        
        public readonly string PublicField;

    4. 公有静态字段采用Pascal命名法    

        public static string PublicStaticField;

        public static readonly string PublicStaticField;

    5. 常量字段采用Pascal命名法

        public const string DefaltWord = "Hello World";

        internal const string DefaltWord = "Hello World";

        protected const string DefaltWord = "Hello World";

        private const string DefaltWord = "Hello World";

    6. 属性与方法采用Pascal命名法

        public string InstanceProperty { get;private set; }

        public static string StaticProperty { get; private set; }

        public void DoSomething() { }

### 5. 方法参数、局部变量与局部常量规范

    1. 方法参数采用Camel命名法

        public bool Login(string userName, string password) { }

    2. 局部变量采用Camel命名法

        public void DoSomething()
        {
            string localVariable = "Hello World";
            Console.WriteLine(localVariable);
            Console.ReadKey();
        }

    3. 局部常量采用Camel命名法

        public void DoSomething()
        {
            const string localConstant = "Hello World";
            Console.WriteLine(localConstant);
            Console.ReadKey();
        }

### 6. 泛型参数规范

    1. 泛型参数采用T + Pascal命名法

        public interface IRepository<TEntity> { }
        
        public class Transform<TEntity, TDTO> { }

### 7. 注释规范

    1. 类（接口）与类（接口）的成员（字段、属性与方法）必须包含文档注释

    2. 类的文档注释应至少包含类的中文名称含义。

    3. 字段与属性的文档注释至少包含字段与属性的中文名称含义。

    4. 方法的文档注释需要包含方法的中文名称含义，方法参数与返回值的中文名称含义以及方法可能会抛出的异常信息。
