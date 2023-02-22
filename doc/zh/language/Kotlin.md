# kotlin 1.7

[//]: # (title: 关键词和运算符)

## 硬关键词

以下标记始终被解释为关键字，不能用作标识符：

 * `as`
     - 被用作[类型转换](typecasts.md#unsafe-cast-operator)。
     - 指定一个[导入的别名](packages.md#imports)。
 * `as?` 被用作[安全的类型转换](typecasts.md#safe-nullable-cast-operator)。
 * `break` [终止循环的执行](returns.md)。
 * `class` 声明一个[类](classes.md)。
 * `continue` [进行循环的下轮](returns.md)。
 * `do` 开始一个[do/while 循环](control-flow.md#while-loops) (带有后置条件的循环)。
 * `else` 当条件为false时，定义 [if 表达式](control-flow.md#if-expression)的分支。
 * `false` 指定[布尔类型](booleans.md)的'false'值。
 * `for` [for 循环](control-flow.md#for-loops)的开头。
 * `fun` 声明一个[方法](functions.md)。
 * `if` 开始一个[if 表达式](control-flow.md#if-expression)。
 * `in`
     - 指定在[for 循环]中迭代的对象(control-flow.md#for-loops)。
     - 用作中缀运算符以检查值是否属于 [范围](ranges.md),
       一个集合，或另一个[定义“包含”方法](operator-overloading.md#in-operator)的实体。
     - 出于同样的目的，用在[when 表达式](control-flow.md#when-expression)。
     - 标记一个类型参数为 [逆变的（contravariant）](generics.md#declaration-site-variance)。
 * `!in`
     - 用作运算符以检查值不属于[范围](ranges.md),
       一个集合，或另一个[定义“包含”方法](operator-overloading.md#in-operator)。
     - 出于同样目的，用在[when 表达式](control-flow.md#when-expression)。
 * `interface` 声明一个[接口](interfaces.md).
 * `is`
     - 检查[一个值具有某种类型](typecasts.md#is-and-is-operators)。
     - 出于同样目的，用在[when 表达式](control-flow.md#when-expression)。
 * `!is`
     - 检查[一个值不具有某种类型](typecasts.md#is-and-is-operators)。
     - 出于同样目，用在[when 表达式](control-flow.md#when-expression)。
 * `null` 是一个常量，表示不指向任何对象的对象引用。
 * `object` 同时声明 [一个类和它的实例](object-declarations.md)。
 * `package` 指定[当前文件所在的包](packages.md)。
 * `return` [从最近的封闭函数或匿名函数返回](returns.md)。
 * `super`
     - [指方法或属性的超类实现](inheritance.md#calling-the-superclass-implementation)。
     - [从辅助构造函数调用超类构造函数](classes.md#inheritance)。
 * `this`
     - 指[当前接收者](this-expressions.md)。
     - [从辅助构造函数调用同一类的另一个构造函数](classes.md#constructors)。
 * `throw` [抛出一个异常](exceptions.md)。
 * `true` 指定[布尔类型](booleans.md)的'true'值。
 * `try` [开始一个异常处理块](exceptions.md)。
 * `typealias` 声明一个[类型别名](type-aliases.md)。
 * `typeof` 保留供将来使用。
 * `val` 声明一个只读[属性](properties.md)或者[本地变量](basic-syntax.md#variables)。
 * `var` 声明一个可变[属性](properties.md)或者[本地变量](basic-syntax.md#variables)。
 * `when` 开始一个[when 表达式](control-flow.md#when-expression) (执行其中一个分支)。
 * `while` 开始一个[while 循环](control-flow.md#while-loops) (带前置条件的循环)。

## 软关键词

以下标记在它们适用的上下文中充当关键字，并且可以使用作为其他上下文中的标识符：

 * `by`
     - [将接口的实现委托给另一个对象](delegation.md)。
     - [将属性的访问器的实现委托给另一个对象](delegated-properties.md)。
 * `catch` 开始一个代码块[处理一个特定的异常类型](exceptions.md)。
 * `constructor` 声明一个[主要或者辅助构造器](classes.md#constructors)。
 * `delegate` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `dynamic` 在Kotlin/JS代码中引用一个[动态类型](dynamic-type.md)。
 * `field` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `file` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `finally` 开始一个在[try 代码块结束后总会执行](exceptions.md)的代码块。
 * `get`
     - 声明[属性的 getter](properties.md#getters-and-setters)。
     - is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `import` [将另一个包中的声明导入当前文件](packages.md)。
 * `init` 开始一个[初始化代码块](classes.md#constructors)。
 * `param` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `property` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `receiver`is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
 * `set`
     - 声明[属性的 setter](properties.md#getters-and-setters)。
     - is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
* `setparam` is used as an [annotation use-site target](annotations.md#annotation-use-site-targets).
* `value` 使用 `class` 关键字声明一个[内联类](inline-classes.md)。
* `where` 指定[泛型类型参数的约束](generics.md#upper-bounds)。

## 修饰符关键字

以下标记在声明的修饰符列表中充当关键字，它们可以用作标识符在其他情况下：

 * `abstract` 标记一个类或成员是[抽象的](classes.md#abstract-classes)。
 * `actual` 在[多平台项目](multiplatform.md)中，表示特定平台的实现。
 * `annotation` 声明一个[注解类](annotations.md)。
 * `companion` 声明一个[伴生对象](object-declarations.md#companion-objects)。
 * `const` 标记一个属性为[编译时常量](properties.md#compile-time-constants)。
 * `crossinline` 禁止[lambda表达式的非本地返回传递给内联函数](inline-functions.md#non-local-returns)。
 * `data` 指示编译器[为一个类生成规范成员](data-classes.md)。
 * `enum` 声明一个[枚举类](enum-classes.md)。
 * `expect` 标记一个声明为[特定平台](multiplatform.md), 期待在平台模块的一个实现。
 * `external` 标记一个声明为Kotlin外的实现(通过[JNI](java-interop.md#using-jni-with-kotlin)或者[JavaScript](js-interop.md#external-modifier)可访问)。
 * `final` 禁止[重载一个成员](inheritance.md#overriding-methods)。
 * `infix` 允许调用一个方法使用[中缀符号](functions.md#infix-notation).。
 * `inline` 告诉编译器[内联一个方法和在调用站点传递它的lambda表达式](inline-functions.md)。
 * `inner` 允许从[嵌套类](nested-classes.md)引用外部类实例。
 * `internal` 比较一个声明为[在当前模块是可见的](visibility-modifiers.md)。
 * `lateinit` 允许[在构造器外初始化一个非空属性](properties.md#late-initialized-properties-and-variables)。
 * `noinline` 关闭[传递给内联函数的lambda的内联](inline-functions.md#noinline)。<!-- TODO -->
 * `open` 允许[继承一个类或者重载一个成员](classes.md#inheritance)。
 * `operator` 标记一个函数为[重载运算符或实现约定](operator-overloading.md)。
 * `out` 标记一个类型参数为[协变](generics.md#declaration-site-variance)。
 * `override` 标记一个成员为[一个父类的成员的重载](inheritance.md#overriding-methods)。
 * `private` 标记一个声明为[在当前类或文件可见](visibility-modifiers.md)。
 * `protected` 标记一个声明为[在当前类和其子类可见](visibility-modifiers.md)。
 * `public` 标记一个声明为[在任何地方可见](visibility-modifiers.md)。
 * `reified` 标记一个内联函数的类型参数为[在运行时可调用](inline-functions.md#reified-type-parameters)。
 * `sealed` 声明一个[密封类](sealed-classes.md) (一个具有受限子类的类)。
 * `suspend` 标记一个方法或者lambda表达式为挂起(可用作[协程](coroutines-overview.md))。
 * `tailrec` 标记一个方法为[尾递归](functions.md#tail-recursive-functions) (允许编译器使用迭代替换递归)。
 * `vararg` 允许[给参数（parameter）传递可变数量的参数(arguments)](functions.md#variable-number-of-arguments-varargs)。

## 特殊标识符

以下标识符由编译器在特定上下文中定义，它们可以用作常规标识符其他上下文中的标识符：

 * `field` 在属性访问器内部用于引用[属性支持的字段](properties.md#backing-fields)。
 * `it` 在lambda表达式内部[隐式引用其参数](lambdas.md#it-implicit-name-of-a-single-parameter)。

## 运算符和特殊符号

Kotlin支持以下操作符和特殊符号：

 * `+`, `-`, `*`, `/`, `%` - 数学运算符。
     - `*` 也用在[传递数组到可变数量参数](functions.md#variable-number-of-arguments-varargs)。
 * `=`
     - 赋值运算符。
     - 用于指定[参数地默认值](functions.md#default-arguments)。
 * `+=`, `-=`, `*=`, `/=`, `%=` - [增强赋值运算符](operator-overloading.md#augmented-assignments)。
 * `++`, `--` - [递增和递减运算符](operator-overloading.md#increments-and-decrements)。
 * `&&`, `||`, `!` - 逻辑 'and', 'or', 'not' 运算符 (对于按位运算，使用相应的中[中缀函数](numbers.md#operations-on-numbers) instead)。
 * `==`, `!=` - [相等运算符](operator-overloading.md#equality-and-inequality-operators) (对于非原始类型可以转换为调用 `equals()`)。
 * `===`, `!==` - [引用相等运算符](equality.md#referential-equality)。
 * `<`, `>`, `<=`, `>=` - [比较运算符](operator-overloading.md#comparison-operators) (对于非原始类型可以转换为调用 `compareTo()`)。
 * `[`, `]` - [索引访问运算符](operator-overloading.md#indexed-access-operator) (转换为调用`get` 和 `set`)。
 * `!!` [断言表达式为非空](null-safety.md#the-operator)。
 * `?.` 执行[安全调用](null-safety.md#safe-calls) (当接收器为非空时调用方法或者访问属性)。
 * `?:` 当左侧为null时采用右侧地值([三元运算符(elvis operator)](null-safety.md#elvis-operator))。
 * `::` 创建一个[成员引用](reflection.md#function-references)或者一个[类引用](reflection.md#class-references)。
 * `..` 创建一个[范围](ranges.md)。
 * `:`  在声明中分割名字和类型。
 * `?` 标识一个类型为[可空（nullable）](null-safety.md#nullable-types-and-non-null-types)。
 * `->`
     - 分割[lambda 表达式](lambdas.md#lambda-expression-syntax)中的参数和主体。
     - 分割[方法类型](lambdas.md#function-types)中的参数和返回类型声明。
     - 分割[when 表达式](control-flow.md#when-expression)中分支的条件和主体。
 * `@`
     - 引入[注解](annotations.md#usage)。
     - 引入或引用[循环标签（loop label）](returns.md#break-and-continue-labels)。
     - 引入或引用[lambda 标签](returns.md#return-to-labels)。
     - [从外部范围引用'this'表达式](this-expressions.md#qualified-this)。
     - [引用外部超类](inheritance.md#calling-the-superclass-implementation)。
 * `;` 在同一行分割多个语句。
 * `$` 在[string 模板（template）](strings.md#string-templates)中引用变量或表达式。
 * `_`
     - 在[lambda 表达式](lambdas.md#underscore-for-unused-variables)替换未使用的参数。
     - 在[解构声明（destructuring declaration）](destructuring-declarations.md#underscore-for-unused-variables)替换未使用的参数。

有关运算符优先级，请参阅[Kotlin语法 表达](https://kotlinlang.org/docs/reference/grammar.html#expressions)。