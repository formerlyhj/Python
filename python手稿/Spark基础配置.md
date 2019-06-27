## **Spark基础配置**

`pip install pyspark`

RDD变换操作
==========
reduceByKey(func),合并相同键的值

groupByKey()，对具有相同键的值进行分组。

combineByKey()，使用不同的返回类型合并具有相同的键。

mapValues(func)，对Pair RDD中的每个值应用一个函数而不改变键值。

flatMapValues(func)

keys()，返回一个包含键的RDD。

values()，返回一个包含值的RDD。

sortByKey()，返回一个根据键排序的RDD。

subtractByKey(),删除掉RDD中与其它RDD中键相同的元素。

join，对两个RDD进行内连接。

RDD行为
=======
reduce,并行整合RDD中所有数据

aggregate，与reduce类似，但是通常返回不同类型的函数

collect,返回RDD中所有的元素

take，从RDD中返回num个元素

first，返回第一个元素

count，求元素个数

top，从RDD中返回最前面num个元素

foreach，对RDD中的每个元素使用给定的函数
