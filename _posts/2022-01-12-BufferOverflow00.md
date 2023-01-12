---
title: "Buffer Overflow 00"
excerpt: "Education: Buffer Overflow examples"
header:
  overlay_image: /assets/images/welcome.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Welcome"
  actions:
    - label: "More Info"
      url: "NullNinja0.github.io"

date: 2022-01-12T15:34:30-04:00
categories:
  - blog
  - programming
tags:
  - update
  - programming
  - education
  - code
---      
Example of C code with comments:
```c
#include <stdio.h>
#include <string.h>

int main(int argc, char *argv[]) {
    char buffer[10]; // Declare buffer of size 10

    // Check if there is an argument passed
    if(argc != 2) {
        printf("Usage: %s <string>\n", argv[0]); // argv[0] is the name of the file
        return 1;
    }
    // copy the passed argument to buffer
    strcpy(buffer, argv[1]);
    printf("You entered: %s\n", buffer);
    // check if the passed argument is larger than buffer size
    if(strlen(argv[1]) > sizeof(buffer)) {
        printf("Error: Input string is larger than buffer size\n");
    }
    return 0;
}
```
