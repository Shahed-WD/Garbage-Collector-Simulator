
The purpose of this project is to acquire better understandings of mark-and-sweep garbage collection, as described in Course Notes #12, by emulating it inside source programs involving BSTs. In this project the root nodes of the object graph are the class-type fields of the AR objects contained in the runtime stack. Use depth-first traversal of the object graph in the mark phase.
This project must be implemented by expanding these class templates. The required functionalities are described in comments. You will need to add classes implementing your runtime stack (used in Project 3) and data structure maintaining constructed Obj objects (used in Project 1 & 2).
Each call to GC.gc( ) is to perform GC emulation and display the following in an output file:
A list of the Obj objects traversed in the mark phase. Display each object in the format: mark:objId:className:(optional info).
A list of the Obj objects swept in the sweep phase. Display each object in the format: sign:mark:objId:className:(optional info) where sign is "+" or "−" according as the object is reachable or unreachable.
The total # of reachable objects. The total # of unreachable objects.
Here's an example of expected output from running MainGCtest.main.
You might want to invoke GC emulation at different times for testing/experimentation, but the submitted program must invoke it at the exact times specified in the class templates. For example, here's an expected output from modified MainGCtest.main and AR_BST_test.BST_test where GC.gc( ) is invoked when every call to delete( ) is about to return but at no other times. Notice carefully that whenever the PC object to be deleted is found in a node whose left or right subtree is empty, their garbage collection is delayed to the next invocation of GC.gc( ) because they are still reachable from the target field until the AR object is popped.
(Note: In reality, the ObjId values of the garbage-collected objects should be recycled and reused, but this is omitted in this project.)
Submission

