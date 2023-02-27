# Lua - 跨入门槛
lua是一种轻量级的脚本语言，由巴西里约热内卢天主教大学的一个研究小组于1993年开发而来。它是一种基于C语言的扩展脚本语言，可以被嵌入到C/C++程序中使用。由于它的轻量级和可嵌入性，它在游戏开发、嵌入式设备控制、Web开发等领域得到广泛应用。

## 输出
在Lua中，输出使用`print`函数，它的语法如下：
```
print("Hello, Lua!")
```
上述代码将输出一个字符串 `"Hello, Lua!"` 到控制台。

## 变量
在Lua中，变量不需要先声明，它会在第一次赋值时自动创建。变量名区分大小写。
```
myVar = "Hello, Lua!"
print(myVar)
```
上述代码将输出字符串 `"Hello, Lua!"`。

## 数据类型
在Lua中，有以下几种数据类型：

- `nil：空值`
- `boolean：布尔值`
- `number：数值`
- `string：字符串`
- `function：函数`
- `userdata：用户数据`
- `thread：协程`
- `table：表格`
  
```
-- nil
local var1
print(var1) -- 输出 nil

-- boolean
local var2 = true
local var3 = false
print(var2) -- 输出 true
print(var3) -- 输出 false

-- number
local var4 = 100
local var5 = 3.14
print(var4) -- 输出 100
print(var5) -- 输出 3.14

-- string
local var6 = "Hello, Lua!"
print(var6) -- 输出 Hello, Lua!

-- function
local function myFunc()
  print("This is a function")
end
myFunc() -- 输出 This is a function

-- userdata
local var7 = io.stdin
print(var7) -- 输出 userdata: 0x7fdadbc02f30

-- thread
local function myThread()
  print("This is a coroutine")
end
coroutine.resume(coroutine.create(myThread)) -- 输出 This is a coroutine

-- table
local var8 = {1, 2, 3, name = "John"}
print(var8[1]) -- 输出 1
print(var8.name) -- 输出 John
```
## 运算符
<p>在Lua中，有以下运算符：</p>
<ul><li>算术运算符：+、-、*、/、%、^</li><li>关系运算符：==、~=、&lt;、&gt;、&lt;=、&gt;=</li><li>逻辑运算符：and、or、not</li><li>其他运算符：#、..、=、..</li></ul>

```
-- 算术运算符
local var1 = 10
local var2 = 3
print(var1 + var2) -- 输出 13
print(var1 - var2) -- 输出 7
print(var1 * var2) -- 输出 30
print(var1 / var2) -- 输出 3.3333333333333
print(var1 % var2) -- 输出 1
```
<br>
<p>其中，乘法运算符 <code>*</code> 用于计算两个数的乘积，除法运算符 <code>/</code> 用于计算两个数的商，取模运算符 <code>%</code> 用于计算两个数的余数。</p>
<p>除法运算符 <code>/</code> 的结果为浮点数，而不是整数。如果要进行整数的除法运算，可以使用两个斜杠 <code>//</code>。</p>

```
-- 整数除法运算符
local var1 = 10
local var2 = 3
print(var1 // var2) -- 输出 3
```
<br>
除了算术运算符，Lua 还提供了其他的运算符，例如比较运算符、逻辑运算符和位运算符。接下来，我们可以介绍其中的一些运算符，并通过示例来解释它们的用法。
<br>
<br>

```
-- 比较运算符
local var1 = 10
local var2 = 3
print(var1 > var2) -- 输出 true
print(var1 < var2) -- 输出 false
print(var1 == var2) -- 输出 false
print(var1 ~= var2) -- 输出 true
```

比较运算符 `>` 和 `<` 分别用于比较两个数的大小，`==` 用于判断两个数是否相等，`~=` 用于判断两个数是否不相等。注意，在 Lua 中，相等运算符是 `==`，而不是 `=`。
<br>
```
-- 逻辑运算符
local a = true
local b = false
print(a and b) -- 输出 false
print(a or b) -- 输出 true
print(not a) -- 输出 false
```
逻辑运算符 `and` 和 `or` 用于对两个逻辑表达式进行求值，并返回一个逻辑值。`and` 运算符返回第一个表达式为 `false` 的值，否则返回第二个表达式的值。`or` 运算符返回第一个表达式为 `true` 的值，否则返回第二个表达式的值。`not` 运算符用于对一个逻辑表达式取反。
<br>
