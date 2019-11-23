# Traversable

检测一个类是否可以使用 `foreach` 进行遍历的接口。无法被单独实现的基本抽象接口。相反它必须由 `IteratorAggregate` 或 `Iterator` 接口实现。