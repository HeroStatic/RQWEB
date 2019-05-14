# LyProject
 此demo总结
 1.根据todos计算todos里面hasfinished为true的个数
    todos.reduce((prev,cur)=>prev+(cur.hasfinished?1:0),0)
 2.计算属性的 get 和 set  
    get 是通过其他的状态变化 得到当前绑定的状态
    set 是修改当前的状态   会得到一个当前的value
 3.计算属性可以作为另外一个计算属性的属性 通过this调用