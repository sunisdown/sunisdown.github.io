无用的 CAP 理论
==========================================


很多分布式系统中都无法避开 CAP 这个理论，从 Consistency/Availability/Partition tolerance 三个特性里面选出两个来实现。实际上，这三个特性放在一起让人来选择很容易误导人，因为这三个选项里面，有一个是必须要面对的选项，像网络问题，这是一个无论如何都需要面对的问题。

----------------------------

通常情况，如果网络没有问题，那一个系统也就同时可以保证 Consistency/Availability，但是当网络出现问题的时候，你就需要从 Consistency 与 Availability 中选择一个来实现。所以对与 CAP 理论更好的解释是，当你在 Partitioned 状态下，选择 Consistency 还是 Availability。一个稳定的网络可以减少这种选择，但是有的时候，这种选择是无法避免的。

在讨论 CAP 时，对于 Availability 的定义都有一些矛盾的地方，很多说 `highly available` (fault-tolerant) 系统，通常跟 CAP 里面的 `availability` 不是一回事。总之，在 CAP 里面有很多让人误解的地方，并且他也不能帮助我们更好的理解某一个系统。


