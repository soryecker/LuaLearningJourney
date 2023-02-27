# Lua - 协程(coroutine)
在 Lua 中，协程(`coroutine`)是一种轻量级线程，它允许在运行中的代码中挂起和恢复执行。协程非常适合用于异步编程和协作式多任务处理等场景。

在 Lua 中，协程通过 `coroutine` 库来创建和操作。`coroutine` 库提供了 `coroutine.create()`、`coroutine.resume()`、`coroutine.yield()`、`coroutine.status()` 等函数来支持协程的创建、恢复、挂起和状态查询等操作。

下面是一个简单的例子：
```
-- 定义一个简单的协程函数
function simpleCoroutine()
  print("协程开始")
  
  -- 进入挂起状态，直到协程唤醒
  coroutine.yield()
  
  print("协程结束")
end

-- 创建一个新的协程对象
co = coroutine.create(simpleCoroutine)

print("主程序开始")

-- 启动协程
coroutine.resume(co)

print("主程序结束")

```

输出结果为：
```
主程序开始
协程开始
主程序结束
```

<ul><li>第 1 行定义了一个函数 <code>simpleCoroutine</code>，用于作为协程的执行体。</li><li>第 5 行通过 <code>coroutine.create</code> 函数创建了一个新的协程对象 <code>co</code>，该协程的执行体为 <code>simpleCoroutine</code> 函数。</li><li>第 8 行输出了 "主程序开始"，表示主程序的执行已经开始。</li><li>第 11 行通过 <code>coroutine.resume(co)</code> 启动了协程 <code>co</code>，并执行其协程函数 <code>simpleCoroutine</code>。执行到第 6 行时，协程函数进入了挂起状态，等待协程的唤醒。</li><li>第 13 行输出了 "主程序结束"，表示主程序的执行已经结束。</li><li>此时，协程仍处于挂起状态，没有继续执行。如果需要唤醒协程，需要调用 <code>coroutine.resume(co)</code> 再次启动协程。</li></ul>
<p>需要注意的是，协程函数中的 <code>yield</code> 函数会挂起当前协程，直到协程的唤醒。因此，在 <code>yield</code> 之后的代码都不会得到执行，直到协程再次启动。</p>