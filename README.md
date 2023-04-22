# 0x11. C - printf

This is a custom implementation of the `printf` function in C, completed as part of the ALX School curriculum. The `printf` function is used to format and print output to the standard output stream (stdout) in C. This custom implementation adheres to the requirements provided by ALX School, including using allowed editors, compiling with specific options, following the Betty style, and not using global variables.

## AUTHORS

- [Houssam Mrabet](https://github.com/HoussamMrabet) 👨‍💻
- [Mahmoud Khairi](https://github.com/Mahmoud-Khairi) 👨‍💻

## Requirements

- This custom `printf` function was developed and tested on Ubuntu 20.04 LTS using the GCC compiler with the options `-Wall -Werror -Wextra -pedantic -std=gnu89`.
- The code follows the Betty style, which is a set of guidelines for writing clean and readable C code.
- The custom `printf` function does not use global variables, and each file contains no more than 5 functions.
- The prototypes of all functions used in this custom `printf` function are included in a header file called `main.h`, which is properly include guarded.

## Features

This custom `printf` function supports the following format specifiers, similar to the standard `printf` function in C:

- `%c`: for printing characters
- `%s`: for printing strings
- `%d` and `%i`: for printing signed integers
- `%u`: for printing unsigned integers
- `%o`: for printing octal numbers
- `%x` and `%X`: for printing hexadecimal numbers
- `%%`: for printing a literal `%` character

Additionally, this custom `printf` function supports the following format modifier:

- `%r`: for printing a reverse string (a custom extension not found in the standard `printf` function)

This custom `printf` function also supports variable argument lists using the `<stdarg.h>` library, specifically the `va_start`, `va_end`, `va_copy`, and `va_arg` functions.

## Compilation and Usage

To compile the custom `printf` function, you can use the following command:

```
gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c
```

After compilation, you can include the `main.h` header file in your C program and use the `_printf` function with the supported format specifiers and modifiers as described above.

Here is an example of how you can use the custom `printf` function:

```c
#include <limits.h>
#include <stdio.h>
#include "main.h"

int main(void)
{
    int len;
    int len2;
    unsigned int ui;
    void *addr;

    len = _printf("Let's try to printf a simple sentence.\n");
    len2 = printf("Let's try to printf a simple sentence.\n");
    ui = (unsigned int)INT_MAX + 1024;
    addr = (void *)0x7ffe637541f0;
    _printf("Length:[%d, %i]\n", len, len);
    printf("Length:[%d, %i]\n", len2, len2);
    _printf("Negative:[%d]\n", -762534);
    printf("Negative:[%d]\n", -762534);
    _printf("Unsigned:[%u]\n", ui);
    printf("Unsigned:[%u]\n", ui);
    _printf("Unsigned octal:[%o]\n", ui);
    printf("Unsigned octal:[%o]\n", ui);
    _printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    printf("Unsigned hexadecimal:[%x, %X]\n", ui, ui);
    _printf("Character:[%c]\n", 'H');
    printf("Character:[%c]\n", 'H');
    _printf("String:[%s]\n", "I am a string !");
    printf("String:[%s]\n", "I am a string !");
    _printf("Address:[%p]\n", addr);
    printf("Address:[%p]\n", addr);
    len = _printf("Percent:[%%]\n");
    len2 = printf("Percent:[%%]\n");
    _printf("Len:[%d]\n", len);
    printf("Len:[%d]\n", len2);
    _printf("Unknown:[%r]\n");
    printf("Unknown:[%r]\n");
    return (0);
}
```

This would output the following:

```
Let's try to printf a simple sentence.
Let's try to printf a simple sentence.
Length:[39, 39]
Length:[39, 39]
Negative:[-762534]
Negative:[-762534]
Unsigned:[2147484671]
Unsigned:[2147484671]
Unsigned octal:[20000001777]
Unsigned octal:[20000001777]
Unsigned hexadecimal:[800003ff, 800003FF]
Unsigned hexadecimal:[800003ff, 800003FF]
Character:[H]
Character:[H]
String:[I am a string !]
String:[I am a string !]
Address:[0x7ffe637541f0]
Address:[0x7ffe637541f0]
Percent:[%]
Percent:[%]
Len:[12]
Len:[12]
Unknown:[%r]
Unknown:[%r]
```

Note: The `%b` format specifier is a custom extension not found in the standard `printf` function, and it prints the binary representation of an unsigned integer.