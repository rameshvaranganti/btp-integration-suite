<!-- loiofb103944fc9340efae59631bdb7b145e -->

# Create Heap and Thread Dumps

Learn how to create heap and thread dumps.



## Context

You can create heap and thread dumps either by:

-   Creating a diagnostic task. Open *Diagnostics* through the *Quick Links* card in the Operations Cockpit and create a *Heap* or *Thread Dump* task.

    For more information, see [Diagnostics](diagnostics-80f3050.md).

-   Using the `jcmd` tool. To do so, perform the following procedure:


> ### Note:  
> The commands and examples in this document use the placeholder *<your-namespace\>*. Replace this with the actual namespace you defined during the deployment. If you kept the default settings, your namespaces are `edge-icell`, `edge-icell-services`, `edge-icell-ela`, or `istio-gateways`.



## Procedure

1.  To identify the pod for which you want to trigger a dump, use `kubectl get pods -n <your-namespace>`.

2.  To connect to a worker pod, use `kubectl exec -it <pod name> -n <your-namespace> -- bash`.

3.  To create a thread dump, use `jcmd org.apache.karaf.main.Main Thread.print > <path/file name>`.

4.  To create a heap dump, use `jcmd org.apache.karaf.main.Main GC.heap_dump <path/file name>`.

    > ### Note:  
    > If external storage is enabled, the shared file system is mounted on `/var/lib/worker/data` on worker pods.

    You can copy files using `kubectl -n <your-namespace> cp <pod name>:<path>/<file name> <dest file name>`.


