# Chapter 1: Introduction (引言)

THIS book is designed to help you make effective use of the Java programming language and its fundamental libraries: java.lang, java.util, and java.io, and subpackages such as java.util.concurrent and java.util.function. Other libraries are discussed from time to time.

本书旨在帮助你有效地使用 Java 编程语言及其基础库：`java.lang`、`java.util` 和 `java.io`，以及子包如 `java.util.concurrent` 和 `java.util.function`。偶尔也会讨论其他一些库。

This book consists of ninety items, each of which conveys one rule. The rules capture practices generally held to be beneficial by the best and most experienced programmers. The items are loosely grouped into eleven chapters, each covering one broad aspect of software design. The book is not intended to be read from cover to cover: each item stands on its own, more or less. The items are heavily cross-referenced so you can easily plot your own course through the book.

本书由90个条目组成，每个条目传达了一条规则。这些规则总结了经验最丰富的优秀程序员普遍认为有益的实践。这些条目松散地分为11章，每章涵盖软件设计的一个广泛方面。本书并非打算从头读到尾：每个条目基本上都是独立的。条目之间有大量交叉引用，因此你可以轻松地自行规划阅读路径。

Many new features were added to the platform since the last edition of this book was published. Most of the items in this book use these features in some way. This table shows you where to go for primary coverage of key features:

自本书上一版出版以来，平台新增了许多新特性。本书大多数条目都以某种方式使用了这些特性。下表显示了关键特性的主要讲解位置：

| Feature | Items | Release |
|--------|--------|---------|
| Lambdas | Items 42–44 | Java 8    |
| Streams | Items 45–48 | Java 8    |
| Optionals | Item 55 | Java 8    |
| Default methods in interfaces | Item 21 | Java 8  |
| try-with-resources | Item 9 | Java 7  |
| @SafeVarargs | Item 32 | Java 7  |
| Modules | Item 15 | Java 9  |

Most items are illustrated with program examples. A key feature of this book is that it contains code examples illustrating many design patterns and idioms. Where appropriate, they are cross-referenced to the standard reference work in this area [Gamma95].

本书多数条目配有程序示例。一个显著特点是，书中包含了展示许多设计模式和惯用法的代码示例。适当的地方，它们会与该领域标准参考著作[Gamma95]进行交叉引用。

Many items contain one or more program examples illustrating some practice to be avoided. Such examples, sometimes known as antipatterns, are clearly labeled with a comment such as **// Never do this!**. In each case, the item explains why the example is bad and suggests an alternative approach.

许多条目包含一个或多个程序示例说明应避免的某些做法。这样的例子有时被称为反模式，它们会明确地标记为 **// Never do this!**。在每种情况下，条目都会解释为什么这个例子不好，并提出替代方法。

This book is not for beginners: it assumes that you are already comfortable with Java. If you are not, consider one of the many fine introductory texts, such as Peter Sestoft’s Java Precisely [Sestoft16]. While Effective Java is designed to be accessible to anyone with a working knowledge of the language, it should provide food for thought even for advanced programmers.

本书不是为初学者准备的：它假设你已经对 Java 非常熟悉。如果你不是，请考虑阅读众多优秀的入门书籍之一，例如 Peter Sestoft 的《Java Precisely》[Sestoft16]。虽然《Effective Java》旨在任何具备工作级语言知识的人都能理解，但它也应该为高级程序员提供思考的空间。

Most of the rules in this book derive from a few fundamental principles. Clarity and simplicity are of paramount importance. The user of a component should never be surprised by its behavior. Components should be as small as possible but no smaller. (As used in this book, the term component refers to any reusable software element, from an individual method to a complex framework consisting of multiple packages.) Code should be reused rather than copied. The dependencies between components should be kept to a minimum. Errors should be detected as soon as possible after they are made, ideally at compile time.

本书中大多数规则源自几个基本原理。清晰性和简洁性最为重要。组件的使用者永远不应对其行为感到意外。组件应该尽可能小，但不能更小。（在本书中，“组件”这个词指的是任何可重用的软件元素，从单个方法到由多个包组成的复杂框架。）代码应该被复用而不是复制。组件之间的依赖关系应保持最少。错误应在产生后尽快被检测到，理想情况下是在编译时。

While the rules in this book do not apply 100 percent of the time, they do characterize best programming practices in the great majority of cases. You should not slavishly follow these rules, but violate them only occasionally and with good reason. Learning the art of programming, like most other disciplines, consists of first learning the rules and then learning when to break them.

尽管本书中的规则并非在所有情况下都100%适用，但它们确实代表了大多数情况下的最佳编程实践。你不应盲目遵循这些规则，而只能偶尔且有充分理由地打破它们。学习编程艺术，像大多数其他学科一样，首先是学习规则，然后是学习何时可以打破它们。

For the most part, this book is not about performance. It is about writing programs that are clear, correct, usable, robust, flexible, and maintainable. If you can do that, it’s usually a relatively simple matter to get the performance you need (Item 67). Some items do discuss performance concerns, and a few of these items provide performance numbers. These numbers, which are introduced with the phrase "On my machine," should be regarded as approximate at best.

总的来说，本书不关注性能。它关注的是编写清晰、正确、可用、健壮、灵活和易于维护的程序。如果你能做到这一点，通常相对容易获得所需的性能（条目67）。有些条目确实讨论了性能问题，其中一些条目提供了性能数据。这些数据在引入时会使用“在我的机器上”这一短语，应将其视为近似值。

For what it’s worth, my machine is an aging homebuilt 3.5GHz quad-core Intel Core i7-4770K with 16 gigabytes of DDR3-1866 CL9 RAM, running Azul’s Zulu 9.0.0.15 release of OpenJDK, atop Microsoft Windows 7 Professional SP1
(64-bit).

顺便说一下，我的机器是一台老旧的家用3.5GHz四核Intel Core i7-4770K，配备16GB DDR3-1866 CL9内存，运行Azul Systems的Zulu 9.0.0.15版本OpenJDK，在Microsoft Windows 7 Professional SP1 (64位)之上。

When discussing features of the Java programming language and its libraries, it is sometimes necessary to refer to specific releases. For convenience, this book uses nicknames in preference to official release names. This table shows the mapping between release names and nicknames: 

在讨论Java编程语言及其库的功能时，有时需要引用特定的发布版本。为了方便起见，本书优先使用昵称而非官方发布名称。下表展示了发布名称与昵称之间的映射关系：

| Official Release Name                              | Nickname   |
|----------------------------------------------------|------------|
| JDK 1.0.x                                          | Java 1.0   |
| JDK 1.1.x                                          | Java 1.1   |
| Java 2 Platform, Standard Edition, v1.2            | Java 2     |
| Java 2 Platform, Standard Edition, v1.3            | Java 3     |
| Java 2 Platform, Standard Edition, v1.4            | Java 4     |
| Java 2 Platform, Standard Edition, v5.0            | Java 5     |
| Java Platform, Standard Edition 6                  | Java 6     |
| Java Platform, Standard Edition 7                  | Java 7     |
| Java Platform, Standard Edition 8                  | Java 8     |
| Java Platform, Standard Edition 9                  | Java 9     |

The examples are reasonably complete, but favor readability over completeness. They freely use classes from packages java.util and java.io. In order to compile examples, you may have to add one or more import declarations, or other such boilerplate. The book’s website, `http://joshbloch.com/effectivejava`, contains an expanded version of each example, which you can compile and run.

书中的示例相当完整，但更注重可读性。它们自由地使用来自`java.util`和`java.io`包的类。为了编译示例，你可能需要添加一个或多个导入声明或其他类似的样板代码。本书的网站`http://joshbloch.com/effectivejava`, 包含了每个示例的扩展版本，你可以编译并运行它们。

For the most part, this book uses technical terms as they are defined in The Java Language Specification, Java SE 8 Edition [JLS]. A few terms deserve special mention. The language supports four kinds of types: interfaces (including annotations), classes (including enums), arrays, and primitives. The first three are known as reference types. Class instances and arrays are objects; primitive values are not. A class’s members consist of its fields, methods, member classes, and member interfaces. A method’s signature consists of its name and the types of its formal parameters; the signature does not include the method’s return type.

总的来说，本书使用的技术术语与《Java Language Specification, Java SE 8 Edition》[JLS]中定义的一致。有几个术语值得特别提及。该语言支持四种类型的类型：接口（包括注解）、类（包括枚举）、数组和基本类型。前三种被称为引用类型。类实例和数组是对象；基本值不是。一个类的成员包括它的字段、方法、成员类和成员接口。一个方法的签名由其名称及其形式参数的类型组成；签名不包括方法的返回类型。

This book uses a few terms differently from The Java Language Specification. Unlike The Java Language Specification, this book uses inheritance as a synonym for subclassing. Instead of using the term inheritance for interfaces, this book simply states that a class implements an interface or that one interface extends another. To describe the access level that applies when none is specified, this book uses the traditional package-private instead of the technically correct package access [JLS, 6.6.1].

本书也使用了一些与《Java Language Specification》不同的术语。 例如，本书用术语"继承"(inheritance)作为"子类化"(subclassing)的同义词。本书不再使用“接口继承” 这种说法，而是简单地说，一个类实现(implement)了一个接口，或者一个接口扩展(extend)了另一个接口。为了描述“在没有指定访问级别的情况下所使用的访问级别”，本书使用了传统的描述性术语"包级私有"(package-private)，而不是技术性术语"包级访问"(package access)级别[JLS, 6.6.1]。

This book uses a few technical terms that are not defined in The Java Language Specification. The term exported API, or simply API, refers to the classes, interfaces, constructors, members, and serialized forms by which a programmer accesses a class, interface, or package. (The term API, which is short for application programming interface, is used in preference to the otherwise preferable term interface to avoid confusion with the language construct of that name.) A programmer who writes a program that uses an API is referred to as a user of the API. A class whose implementation uses an API is a client of the API.

本书还使用了一些在《Java Language Specification》中未定义的技术术语。导出的API（exported API），或简称为API，是指程序员访问类、接口或包所使用的类、接口、构造函数、成员和序列化形式。（术语API是Application Programming Interface的缩写，为了避免与同名的语言构造混淆，本书优先使用该术语而非更合适的interface。）编写使用某个API的程序的程序员被称为该API的用户。实现使用某个API的类是该API的客户端。

Classes, interfaces, constructors, members, and serialized forms are collectively known as API elements. An exported API consists of the API elements that are accessible outside of the package that defines the API. These are the API elements that any client can use and the author of the API commits to support. Not coincidentally, they are also the elements for which the Javadoc utility generates documentation in its default mode of operation. Loosely speaking, the exported API of a package consists of the public and protected members and constructors of every public class or interface in the package.

类、接口、构造函数、成员和序列化形式统称为API元素。导出的API包括可以从定义该API的包外部访问的API元素。这些是任何客户端都可以使用的API元素，也是API作者承诺支持的元素。不出所料，它们也是Javadoc工具在其默认操作模式下生成文档的元素。粗略地说，一个包的导出API由该包中每个公共类或接口的公共和受保护的成员及构造函数组成。

In Java 9, a module system was added to the platform. If a library makes use of the module system, its exported API is the union of the exported APIs of all the packages exported by the library’s module declaration.

在Java 9中，平台增加了模块系统。如果一个库使用了模块系统，那么它的导出API就是该库模块声明所导出的所有包的导出API的并集。
