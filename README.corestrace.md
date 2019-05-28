Coredump contains stack information as well. If you can use this stack information along with the EBP and EIP register values in the coredump file, you can print the stack trace. I had written a program to do this. You can find the program in the following link.

https://gist.github.com/root42/c979b037f85dc4b2be1f3735afedeb1d

Usage: Compile the above program and give the corefile when you execute it.

       $corestrace core
       
If you want symbols also to be printed, you do like this: Let's assume the program that generated the core is 'test'.

       $ nm -n test > symbols
       $ corestrace core symbols
       
Sample output looks like this:

       $ ./coretrace core symbols 

        0x80483cd foo+0x9
        0x8048401 func+0x1f
        0x8048430 main+0x2d
