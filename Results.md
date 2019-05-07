We see that in epoch-async mode our application achieves very good (superlinear) scaling, surpassing the ideal speedup (likely because Spark with n=1 induces large overhead compared to an optimized sequential code, which we did not run). We see that batch-async, however, performs very poorly with n>2.

We believe this is a result of growing communication overhead. Investigation into the CPU utilization of the worker nodes shows that only ~50% (of 400%) of each worker is being utilized for training. Meanwhile, when n>2, the communication server seems to be bottlenecked. We achieve roughly the same ~65-70% accuracy in all experiments.


