### Output type in linux

1) Standard error - stderr(2)
2) Standard output - stdout(1)

### How to redirect standard error to the null stream so that the data would not be displayed on the console

```sh
./main 1 2 3 4 2> /dev/null
```

1) Articles on the digital ocean which explains the details of how to use I/O redirection
https://www.digitalocean.com/community/tutorials/an-introduction-to-linux-i-o-redirection

2) A c program which explain how to pass message to standard output/error

```c
#include "stdio.h"
#include "stdlib.h"
#include <sys/stat.h>
#include <fcntl.h>

int main(int argc, char **argv) {

  printf("The program is started with argc = %d\n", argc);

  printf("The program name is = %s\n", argv[0]);

  int i = 0;

  perror("Passing the message to the error channel");

  int fd = open("/etc/spasswd", O_RDONLY);
  if (fd == -1) {
    perror("open");
  }

  while(++i < argc) {
    printf("The program arguments at position = %d is %s\n", i, argv[i]);
  }

  printf("Hi! This is my name %s , and my virtual age = %d\n", "Debabrata Tripathy",43);
  return -1;
}

```
