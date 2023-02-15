# WIP autonorm.py
Auto-normer for 42 school's norminette

# How it works
When you compile with gcc, you can use the lever "-D" to define a macro (Exemple: gcc main.c -D SOMEVAR="abcdef" -o main)
You can put literally any piece of code in a define, so this works:

- test.c:
```
#define MAIN int main() {\
printf("TEST\n");\
}

MAIN
```
Meaning we can basically put the entire source code of a project in defines, which is exactly what this scripts do.

# How to use
Execute the script with your source files directory as argument
python3 autonorm.py ./srcs

When the script is finished, you have in your clipboard all the "-D ...=...". Create a new variable in your makefile and compile with that variable as argument.
Exemple:

- Makefile:
```
DEFINES=(ctrl+V here)
...
$(CC) $(DEFINES) -c $< -o $@
```

You will see that a new folder appeared, called "normed". It contains all the new source files. So be sure to compile theses files to build your executable.
