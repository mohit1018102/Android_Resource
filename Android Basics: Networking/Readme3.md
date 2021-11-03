# Lesson 3: Threads and Parallelism

1. **NetworkOnMainThreadException :** doing network operation on main thread/ ui thread(which is no allowed).


## Threads

1. A threads performed a process/task at a time.
2. Tasks are scheduled in a queue.
<p align="center">
       <img src="./img/mainthread.PNG" />
  </p>
  
3. Network request time is uncertain and might take long processing time to execute the task.
4. thus, blocks other operation in Ui thread and result in ANR( Application Not Responding).
5. So, Network operation are not allowed in main/ui thread.
