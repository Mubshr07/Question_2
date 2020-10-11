# Write the output of below code and also draw the process tree. Submit pdf file of output and tree.

  
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)
 

## C++ Code
 
> #include <iostream>

> #include <stdio.h>

> #include <unistd.h>

> #include <sys/types.h>

> #include <unistd.h>

> #include <signal.h>

>using namespace std;

>int main(int argc, char** argv)

>{

>     pid_t pid, ppid;

>     int n, i;

>     int childstate;

>     int count = 0;

>     n = 2;

>     fork();

>     for(i=1; i<n+1; i++) {

>         if(i % 2 != 0){

>             fork();

>             if(getpid() == 0) {

>                 kill(getppid(), 9);

>             }

>         } else {

>             if(fork() > 0) {

>                 fork();

>                 if(getpid() == 0){
>                 kill(getppid(), 9);
                 
                }
                
            }
            
        } // end of if else
        
        if(i == n) {
        
            printf("Process: %d \n", i);
            
        }
        
    } // end of for loop
    
    cout <<endl<<endl<<endl;
    
    return 0;
}

