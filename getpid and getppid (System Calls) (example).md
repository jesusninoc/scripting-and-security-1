# getpid and getppid (System Calls) (example)
## C, Processes 
### URL: https://www.jesusninoc.com/2014/11/21/getpid-getppid-system-calls-example/
```C
#include<stdio.h>
#include<unistd.h>
#include<stdlib.h>

int main(void)
{
	printf("PID=%d\n", getpid());
	printf("PPID=%d\n", getppid());
}
```
