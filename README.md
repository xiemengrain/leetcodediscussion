# leetcodediscussion


# LRU Cache

### Problem


### Ideas
LRU is a cache data structure that uses LRU policy to purge the data once it reaches the storage capacity defined. It supports O(1) access time for read and write. And uses O(N) storage space.

The problem can be solved with a hashtable that keeps track of the keys and its values in the double linked list. One interesting property about double linked list is that the node can remove itself without other reference. In addition, it takes constant time to add and remove nodes from the head or tail.

we can create a pseudo head and tail to mark the boundary, so that we don't need to check the NULL node during the update. This makes the code more concise and clean, and also it is good for the performance as well.

### pseudo algorithm

Get method : get the cached value give the key
 - check if it exists in the cache. If it exist, return the value and also set this node to be most recently used. If it doesn't exist, return -1.
 
 
Put method: put a new (key, value) pair in the cache or update an exisitng (key, value) pair with a new value
- check if it exists in the cache. 
    - If it exists, set this node to be most recently used; 
    - If it doesn't. Check if the cache is full
        - if the cache is not full; Add this value to the cache and set it to be most recently used
        - if the cache is full; Evict the least used node and then add this value to the cache and set it to be most recently used
        
Operations that will need to support this algorithm from the doubly linked list
- Add a node to the front: When adding a new (key, value) pair, add that node to the front
- remove a node from the back: evict a node
- move to front: Set an exisiting node as most recently used.


