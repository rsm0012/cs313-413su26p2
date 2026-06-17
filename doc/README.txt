TestList.java and TestIterator.java

TODO also try with a LinkedList - does it make any difference?
Using a LinkedList instead of ArrayList makes no difference for basic operations
as the behavior is identical as both can implement the List interface.

TestList.java

testRemoveObject()

list.remove(5); // what does this method do?
This removes the element at INDEX 5.
In this list it removes 77 at index 5.

list.remove(Integer.valueOf(5)); // what does this one do?
This removes the first occurrence of the VALUE 5.
From the list it removes the number 5,

TestIterator.java

testRemove()

i.remove(); // what happens if you use list.remove(Integer.valueOf(77))?
Using list.remove(Integer.valueOf(77)) directly wouldn't be possible,
you can't modify a list directly while iterating over it with an iterator.

TestPerformance.java

SIZE 10
                         #1
testArrayListAddRemove:  191ms
testLinkedListAddRemove: 22ms
testArrayListAccess:     20ms
testLinkedListAccess:    12ms

SIZE 100
                         #1
testArrayListAddRemove:  201ms
testLinkedListAddRemove: 22ms
testArrayListAccess:     16ms
testLinkedListAccess:    22ms

SIZE 1000
                         #1
testArrayListAddRemove:  312ms
testLinkedListAddRemove: 23ms
testArrayListAccess:     17ms
testLinkedListAccess:    244ms

SIZE 10000
                         #1
testArrayListAddRemove:  1601ms
testLinkedListAddRemove: 24ms
testArrayListAccess:     18ms
testLinkedListAccess:    3188ms

listAccess - which type of List is better to use, and why?
ArrayList is better for access. Because the access time stays constant (around 18ms)
regardless of its size, because it uses an index-based array structure.

listAddRemove - which type of List is better to use, and why?
LinkedList is better for add or remove. Its time stays nearly constant
(22-24ms) regardless of its size because it just updates node pointers.
