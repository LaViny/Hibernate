hibernat:
save(),persist()两个方法均能使对象变为持久化，但是在save方法前插入Id时，此id值是无效的，会执行Insert操作，若在persist方法前插入id值，则会报错，不会执行Insert操作。get
1.(1).get()方法和load()方法，get会立即执行查询操作，加载对象。而load方法会延迟检索。延迟加载。（get立即检索，load延迟检索）；
  (2).若数据库中没有查询的数据。get返回Null,load会抛出异常（因为代理对象已经存在，而查询不到，所以抛出异常）；
  (3).load可能会抛出LazyInitException(懒加载)异常，因为初始化代理对象之前session已经关闭了。
2.save(),update().若oid为空，数据表中没有记录，执行save操作。(此时的对象为游离对象。)
