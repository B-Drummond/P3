The stack overflow tarball is just the main part of this project and the input file to run is input-6.txt.

The heap overflow tarball is an attempt at the extra credit portion. The input file to run is input-6.txt. We noticed that they did not check bounds on their scanf of the key in the set_object function. So we put in a very long key value which is just the address of the system call, repeated a lot. I then added code in the set_object function to malloc a struct A object (called in_obj) and added a call to in_obj->op0() so that the op0 function pointer (which should now be overwritten with the address of the system call in shell()) will be called. 

We also noticed that they did not NULL their pointers after they freed them, so I though about a use-after-free exploit but that probably wouldn't work because of the protection settings.

We tried to add minimal code to exploit the heap overflow, but we had to add some so we understand if we do not get full credit for the extra credit portion.

NOTE: I probably have a few extraneous print statements in there, I was trying to do the extra credit up until the last minute.