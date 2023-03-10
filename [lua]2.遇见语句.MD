# lua
## 欢迎来到lua基础的第二篇,这篇主要介绍一些语句
<br>
<h1>控制流语句</h1>
<p>控制流语句使程序能够根据特定条件执行不同的操作。在 Lua 中，控制流语句包括条件语句和循环语句。</p>

<h2>条件语句</h2>
<p>条件语句允许程序在满足特定条件时执行不同的代码块。Lua 中有两种类型的条件语句：if 语句和switch 语句</p>
<h2>if 语句:</h2>
<p>if 语句是最基本的条件语句，它允许程序在满足特定条件时执行不同的代码块。if 语句的语法如下：</p>

```
if (condition) then
    -- 执行代码块
end
```
下面是一个使用 if 语句的例子：
```
local num = 10
if (num > 0) then
    print("num 是一个正数")
end
```
在这个例子中，如果变量 `num` 的值大于 0，则会打印 "num 是一个正数"。

`if` 语句也可以与 `else` 语句结合使用，以在条件不成立时执行其他操作。下面是一个使用 `if` 和 `else` 语句的例子：

```
local num = -5
if (num > 0) then
    print("num 是一个正数")
else
    print("num 是一个负数")
end
```
在这个例子中，如果变量 `num` 的值小于或等于 0，则会打印 "`num` 是一个负数"。

<h2>switch 语句:</h2>

`switch` 语句允许程序根据特定的值执行不同的代码块。在 Lua 中，`switch` 语句是通过 `if` 语句的连续使用来模拟的。

下面是一个使用 `if` 语句模拟 `switch` 语句的例子：
```
local fruit = "apple"
if (fruit == "apple") then
    print("这是一个苹果")
elseif (fruit == "orange") then
    print("这是一个橙子")
else
    print("这是一个未知的水果")
end
```
在这个例子中，如果变量 `fruit` 的值为 "apple"，则会打印 "`这是一个苹果`"。如果变量的值为 "orange"，则会打印 "`这是一个橙子`"。否则，会打印 "`这是一个未知的水果`"。

循环语句
循环语句使程序能够多次执行同一段代码。Lua 中有两种类型的循环语句：`while` 循环和`for` 循环

## while 循环
`while`循环，它会不断重复执行一段代码块，直到指定的条件不再成立为止。`while` 循环的语法格式如下：
```
while (condition)
do
   -- 循环体
end
```
其中 `condition` 是一个布尔表达式，循环体是需要重复执行的代码块。每次循环开始时，都会先判断 `condition` 是否为真，如果为真就执行循环体，然后再重新判断 `condition` 是否为真，如此往复直到 `condition` 不再成立为止。

下面是一个简单的示例，演示如何使用 `while` 循环来计算数字 1 到 10 的和：
```
local i = 1
local sum = 0

while (i <= 10)
do
    sum = sum + i
    i = i + 1
end

print("1到10的和为：" .. sum) -- 输出 1到10的和为：55
```
在这个示例中，我们首先定义了变量 i 和 sum，然后使用 `while` 循环来计算数字 1 到 10 的和。循环开始时，i 的值为 1，sum 的值为 0。每次循环中，我们都将 i 加到 sum 中，并将 i 的值加 1。当 i 的值大于 10 时，循环就结束了。

需要注意的是，如果循环条件一开始就不成立，那么循环体中的代码不会被执行。例如：
```
local i = 11

while (i <= 10)
do
    print(i) -- 这行代码不会被执行
    i = i + 1
end

print("循环结束") -- 输出 循环结束
```
在这个示例中，i 的初始值为 11，所以循环条件不成立，循环体中的代码不会被执行。因此，程序直接输出了“循环结束”。

## repeat-until 循环
repeat-until 循环是一种与 while 循环类似的循环结构。其基本语法如下：
```
repeat
   -- 循环体
until condition
```
这里 `condition` 是一个表达式，如果其值为 `false` 或 `nil`，则继续循环；如果其值为非 `false` 和非 `nil`，则退出循环。因此，`repeat-until` 循环与 `while` 循环的主要区别在于判断条件的时机：`while` 循环在循环体开始前判断条件是否成立，而 `repeat-until` 循环在循环体结束后判断条件是否成立。

下面是一个简单的 `repeat-until` 循环的例子，它将打印出 1~5 的整数：
```
local i = 1
repeat
    print(i)
    i = i + 1
until i > 5
```
该循环首先将变量 `i` 赋值为 1，然后进入循环体，打印出 `i` 的值，并将 `i` 加 1。接着，循环条件 `i > 5` 被判断，如果其值为 `true`，则退出循环；否则，继续执行循环体，直到满足循环条件为止。因此，该循环将输出以下内容：
```
1
2
3
4
5
```

