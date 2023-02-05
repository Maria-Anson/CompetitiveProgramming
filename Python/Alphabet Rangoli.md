You are given an integer, . Your task is to print an alphabet rangoli of size . (Rangoli is a form of Indian folk art based on creation of patterns.)

Different sizes of alphabet rangoli are shown below:

#size 3

\----c\----
\--c\-b\-c\--
c\-b\-a\-b\-c
\--c\-b\-c\--
\----c\----

#size 5

\--------e\--------
\------e\-d\-e\------
\----e\-d\-c\-d\-e\----
\--e\-d\-c\-b\-c\-d\-e\--
e\-d\-c\-b\-a\-b\-c\-d\-e
\--e\-d\-c\-b\-c\-d\-e\--
\----e\-d\-c\-d\-e\----
\------e\-d\-e\------
\--------e\--------

#size 10

\------------------j\------------------
\----------------j\-i\-j\----------------
\--------------j\-i\-h\-i\-j\--------------
\------------j\-i\-h\-g\-h\-i\-j\------------
\----------j\-i\-h\-g\-f\-g\-h\-i\-j\----------
\--------j\-i\-h\-g\-f\-e\-f\-g\-h\-i\-j\--------
\------j\-i\-h\-g\-f\-e\-d\-e\-f\-g\-h\-i\-j\------
\----j\-i\-h\-g\-f\-e\-d\-c\-d\-e\-f\-g\-h\-i\-j\----
\--j\-i\-h\-g\-f\-e\-d\-c\-b\-c\-d\-e\-f\-g\-h\-i\-j\--
j\-i\-h\-g\-f\-e\-d\-c\-b\-a\-b\-c\-d\-e\-f\-g\-h\-i\-j
\--j\-i\-h\-g\-f\-e\-d\-c\-b\-c\-d\-e\-f\-g\-h\-i\-j\--
\----j\-i\-h\-g\-f\-e\-d\-c\-d\-e\-f\-g\-h\-i\-j\----
\------j\-i\-h\-g\-f\-e\-d\-e\-f\-g\-h\-i\-j\------
\--------j\-i\-h\-g\-f\-e\-f\-g\-h\-i\-j\--------
\----------j\-i\-h\-g\-f\-g\-h\-i\-j\----------
\------------j\-i\-h\-g\-h\-i\-j\------------
\--------------j\-i\-h\-i\-j\--------------
\----------------j\-i\-j\----------------
\------------------j\------------------

The center of the rangoli has the first alphabet letter *a*, and the boundary has the alphabet letter (in alphabetical order).

**Function Description**

Complete the *rangoli* function in the editor below.

*rangoli* has the following parameters:

*   *int size:* the size of the rangoli

**Returns**

*   *string:* a single string made up of each of the lines of the rangoli separated by a newline character (\\n)

**Input Format**

Only one line of input containing , the size of the rangoli.

**Constraints**

**Sample Input**

```
5

```

**Sample Output**

```
--------e--------
------e-d-e------
----e-d-c-d-e----
--e-d-c-b-c-d-e--
e-d-c-b-a-b-c-d-e
--e-d-c-b-c-d-e--
----e-d-c-d-e----
------e-d-e------
--------e--------
```
```
def print_rangoli(size):
    # your code goes here
    char_list = [chr(char+97) for char in range(size)]
    reverse = -2
    space = len('-'.join(char_list + char_list[1:]))
    for i in range(size + size-1):
        center_pointer_index = size-i-1
        center_char = char_list[center_pointer_index]
        if i==0 or i==size+size-1:
            print(center_char.center(space, '-'))
        else:
            # Reversing the case to previous iterations
            if i>=size:
                i = i + reverse
                center_pointer_index = size-i-1
                center_char = char_list[center_pointer_index]
                reverse = reverse-2 
            # Adding the characters   
            suffix = char_list[center_pointer_index+1:center_pointer_index+1+i]
            prefix = list(reversed(suffix))
            generated_string = '-'.join(prefix + [center_char] + suffix)

            print(generated_string.center(space, '-'))
    
    
if __name__ == '__main__':
    n = int(input())
    print_rangoli(n)
```
