# chmod (System Call) (example)
## C, Filesystem, Permissions 
### URL: https://www.jesusninoc.com/2014/12/01/chmod-system-call-example/
```PowerShell
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <errno.h>
#include <sys/stat.h>

int main(int argc, char **argv)
{
char mode[] = "0777";
char buf[100] = "/home/user/example.txt";
int i;
i = strtol(mode, 0, 8);
if (chmod (buf,i) < 0)
{
fprintf(stderr, "%s: error in chmod(%s, %s) - %d (%s)\n",
argv[0], buf, mode, errno, strerror(errno));
exit(1);
}
return(0);
}

```
