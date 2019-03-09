### Optimistic Lock And Pessimistic Lock

1.Optimistic Lock </br>

Optimistic lock is an optimistic thought, that is, **to read more and write less**, and to encounter the possibility of concurrent writing is low. </br>

Each time it **reads**, it assumes that the data has not been modified, so **it will not be locked. But lock updates occur during write operations.** </br>

Locks in optimistic locks are implemented using **CAS operations**. **CAS(CompareAndSet) is an updated atomic operation.** Its principle is to compare the current value with the expected value, if the same, update, otherwise fail.</br>

2.Pessimistic Lock </br>

Pessimistic lock is pessimistic thought, that is to say, **writing more**, encounter the possibility of concurrent writing is high.Every read and write operation will be locked, **the typical pessimistic lock is synchronized.** </br>