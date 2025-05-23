# Chapter 9: File Handling in Python

**Table of Contents**:

- [Chapter 9: File Handling in Python](#chapter-9-file-handling-in-python)
  - [9.1. Introduction to File Handling](#91-introduction-to-file-handling)
  - [9.2. File Opening Modes](#92-file-opening-modes)
  - [9.3. Opening and closing a file in python](#93-opening-and-closing-a-file-in-python)
  - [9.4. Reading a file](#94-reading-a-file)
    - [The newer approach using `with` keyword](#the-newer-approach-using-with-keyword)
  - [9.5. Writing into a file](#95-writing-into-a-file)
  - [9.6. Appending into a file](#96-appending-into-a-file)
  - [9.7. Reading a file line by line](#97-reading-a-file-line-by-line)

## 9.1. Introduction to File Handling

- Python is capable of handling or manipulating data stored in files.
- We can open a file using inbuilt `open()` function.
- While opening a file, we have to pass different modes as a parameter to specify what we're trying to do with the file.

## 9.2. File Opening Modes

1. `r`: **Reading** mode
   - The default mode.
   - It allows you only to read the file, not to modify it.
   - When using this mode the file must exist.

2. `w`: **Writing** mode
   - It will create a new file if it does not exist, otherwise will erase the file and allow you to write to it.

3. `a`: **Append** mode
   - It will write data to the end of the file.
   - It does not erase the file, and the file must exist for this mode

4. `rb`: **Binary Reading** mode
   - same as `r` but reading is forced in binary mode.
   - This is also a default choice.

5. `wb`: **Binary Writing** mode
   - same as `w` but writing is forced in binary mode.

6. `ab`: **Binary Apend** mode
   - same as `a` but appending is forced in binary mode.

7. `r+`: **Reading** mode plus **Writing** mode at the same time
   - This allows you to read and write into files at the same time without having to use `r` and `w`.

8. `w+`: **Writing** mode plus **Reading** mode at the same time.
   - If the file does not exist, a new one is made. otherwise overwritten.

9. `a+`: **Apend** mode

    - similar to `w+`

10. `rb+`: **Binary Reading** mode
     - same as `r+` mode but forced in binary mode

11. `wb+`: **Binary Writing** mode
    - same as `w+` mode but forced in binary mode

12. `ab+`: **Binary Apend** mode
    - same as `a+` mode but forced in binary mode

## 9.3. Opening and closing a file in python

- We use `open()` function to open the file.
- We use `file.close()` method to close the file.

**Basic Syntax**:

```python
file_obj = open("<filename>", "<mode>")
# do our stuff over here
file_obj.close()
```

## 9.4. Reading a file

```python
file = open("my_file.txt", "r")
file.read()
file.close()
```

### The newer approach using `with` keyword

- If we open the file with `with` keyword, then we do not need to explicitly close the file.
- It automatically closes the file whenever it goes out of the scope.

```python
with open('my_file.txt', 'r') as f:
    # do our stuff here
    f.read()
print("At this point, the file is closed")
```

## 9.5. Writing into a file

```python
with open('my_file.txt', 'w') as f:
    f.write("This is the content to the file.")
```

## 9.6. Appending into a file

```python
with open('my_file.txt', 'a') as f:
    f.write("This is the appended content to the file.")
```

## 9.7. Reading a file line by line

```python
with open ('my_file.txt', 'r') as f:
    for line in f:
        print(line)
```

we can also achieve the same result using `readlines()` method.

```python
with open ('my_file.txt', 'r') as f:
    for line in f.readlines():
        print(line)
```
