Java internally uses doubly queue to implement queue -> reason if we have to dequeue then its easy to it than that of single queue





|PriorityQueue<br />				↓<br /><br />Iterable <--  Collection <-- Queue <-- Dequeue <--  ArrayDequeu<br />		↑			↑<br />		List	<-------------	LinkedList<br />|
|-|





ArrayDequeue- > Array implementation of queue



LinkedList - > Linkedlist implementation of queue

There nothing like stack class in java(it is there but no legacy) but ArrayDequeue class can also implement stack with limited use case of doubly queue or ArrayDeque(just push and pop from one side)

Also ArrayDequeue can also be used as singly queue

We can use LinkedList class a Stack as well

push(I) ->  offerFirst();

pop() ->  pollFirst();

both are same

In internal implementation of queue if size of array is less than the  required elements then new element created and in circular order java manages the order

As per java docs use ArrayDequeu for stack and queue.

Reason: contiguous nature of array it makes cache friendliness

if we are using ArrayDequeu -> can't insert null but in LinkedList we can

its considered to not put null as value as it is used to know that if value exist or not



if we do

queue.add(1); // any how if it is now possible to insert it will throw exception

queue.offer(1); // it will return false in case of err

&#x20;

queue.peek();//  return null in case no element found

queue.element(); // throws exception in case no element found



queue.remove();  //throws exception if not able to remove

queue.poll(); // return null if not able to remove



in case of Dequeue->

q.addFirst()

q.addLast()

q.offerFirst()



element->  getFirst(), getLast();

peak-> peeakFirst(), peakLAst();

all these methods are available in dequeue and ArrayDequeue for stack as well





in case of stack use

All first methods of dequeue.

push(e) -> offerFirst()

pop() -> pollFirst();

peek() -> peekFirst();



stack LIFO and queue FIFO -> are Behavioural contract we have to maintain them





PriorityQueue:
does not follows FIFO.

There is nothing loke front and rear in prioritQueue

elements have priority

pq.poll()-> removes smallest Element first(by default)

PQ implements Heap Data Structure

PQ without any argument in constructor is min heap gives min value

PQ with (a,b)-> b-a in constructor argument is max heap gives max value

