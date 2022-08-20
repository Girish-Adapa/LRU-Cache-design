# LRU-Cache-design
We use two data structures to implement an LRU Cache.  
Queue is implemented using a doubly-linked list. The maximum size of the queue will be equal to the total number of frames available (cache size). The most recently used pages will be near the front end and the least recently used pages will be near the rear end.
A Hash with the page number as key and the address of the corresponding queue node as value.
When a page is referenced, the required page may be in the memory. If it is in the memory, we need to detach the node of the list and bring it to the front of the queue. 
If the required page is not in memory, we bring that in memory. In simple words, we add a new node to the front of the queue and update the corresponding node address in the hash. If the queue is full, i.e. all the frames are full, we remove a node from the rear of the queue, and add the new node to the front of the queue.


Here cap denotes the capacity of the cache and Q denotes the number of queries. Query can be of two types:

SET x y : sets the value of the key x with value y
GET x : gets the key of x if present else returns -1.

The LRUCache class has two methods get() and set() which are defined as follows.

get(key)   : returns the value of the key if it already exists in the cache otherwise returns -1.
set(key, value) : if the key is already present, update its value. If not present, add the key-value pair to the cache. If the cache reaches its capacity it should invalidate the least recently used item before inserting the new item.
In the constructor of the class the capacity of the cache should be intitialized.

Expected Time Complexity: O(1) for both get() and set().
Expected Auxiliary Space: O(1) for both get() and set().
