# Find Command Practical Example In Linux

# What is the Find command on Linux?

The `find` command is a powerful utility that is built in Linux operating systems. It is used to search for files and directories in a specified location on your system. With the `find` command, you can search for files based on various criteria, such as their name, size, modification time, and permissions.

## The syntax of the **find** command:

```apache
$ find [path] [options..] [filename..]
```

## Find command examples

### 1\. How to Search for a File by Name

In this illustrative example, I will elucidate the process of locating a particular file within the current directory through the utilization of the `find` command.

```apache
$ find . -name file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676710765227/e9064987-9cfd-4e3a-96c5-9cf7c8c15412.png align="center")

## 2\. How to Efficiently Locate All Files Starting with the Letter 'a'

The `find` command is a powerful tool for searching files on the command line and can be used to efficiently locate files starting with a specific letter or character.

```apache
$ find . -iname "a*"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676711639004/f89d5f28-2e72-45b3-bb65-c6226f9b7de6.png align="center")

## 3\. Efficiently Locating Files with a Specific Extension

This guide provides a comprehensive overview of how to efficiently locate files with a specific extension using the `find` command.

```apache
$ find . -iname "*.txt"
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676712055868/362037a7-daa3-4afe-abe6-98044daa6682.png align="center")

### 4\. How to Perform Case-Insensitive Searches for Efficiently Locating Files with Various Naming Conventions

This article provides a comprehensive guide on how to perform case-insensitive searches using the `find` command to locate files with various naming conventions.

```apache
$ find . -name name.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676712552125/134b0896-7586-4730-8310-a8d77489617c.png align="center")

## 5\. Efficiently Locating Only Files or Directories in a Given Path

How to efficiently locate either files or directories in a given path using the `find` command.

```apache
$ find . -type d
$ find . -type f
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676712885570/65777418-f3fc-4b63-a30f-fca6c8f86392.png align="center")

## 6\. Locating Files Owned by a Specific User on a Linux System

The guide explains how to use the '-user' option in the `find` command to search for files that are owned by a specific user.

```apache
$ find . -user root
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676713309876/2098f727-db8c-4a85-836f-c53cdaea66b8.png align="center")

## 7\. Efficiently Locating Files Based on Their Permissions Using the Find Command in Linux

A comprehensive guide on how to use the 'find' command in Linux to efficiently locate files based on their permissions. The guide offers step-by-step instructions on how to use the '-perm' option in the `find` command to search for files with specific permissions.

```apache
$ find . -perm /u=w
$ find . -perm 777
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676713727537/e3ab0510-9a47-4b89-88d4-5b3afa54ed3a.png align="center")

## 8\. How to search all files which are created after the file.txt

The guide explains how to use the `-newer` option in the `find` command to search for files that have been modified or created after the specified file.

```apache
$ find . -newer file.txt
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676714038476/9d770aba-bae9-4270-9c7d-5812459740c9.png align="center")

## 9\. How to search all the empty files in the given directory

A comprehensive guide on how to use the 'find' command in Linux to locate all the empty files in a given directory. The guide offers step-by-step instructions on how to use the `-empty` option in the `find` command to search for empty files in the specified directory.

```apache
$ find . -empty
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676714342112/05a5e3c7-9bf0-4cf8-bbc0-0331bced785a.png align="center")

## 10\. How to search all empty files and delete them

The guide explains how to use the `-empty` option in the 'find' command to search for empty files, and how to use the `-delete` option to remove them.

```apache
$ find . -empty -delete
$ find . -empty -exec rm {} \;
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676714569796/93a2b134-be2f-4192-a310-b317a3ace1c7.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676714775579/77b9f18f-11e7-408e-8663-0bf25387ae98.png align="center")

## 11\. Efficiently Locating a File by Its Inode Number

The guide explains how to use the `-inum` option in the 'find' command to search for files with a specific inode number.

```apache
$ find . -inum 1600162
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676715193018/43483773-f896-46b8-adec-49121ff9c957.png align="center")

## 12\. Efficiently Locating Files by Size Using the find Command

The guide explains how to use the `-size` option in the `find` command to search for files that are larger or smaller than a specific size in bytes, kilobytes, or megabytes.

```apache
$ find . -size 4k
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676715948658/04240ffd-afbc-4738-9d80-bccee84c3d89.png align="center")

## 13\. Methods for Searching and Identifying Files Within a Specific Size Range of 1-50 Kilobytes

The `find` command is a powerful tool available in most Unix-based operating systems that allows users to search for files based on various criteria, including file size. To search for files within a specific size range of 1-50 kilobytes using the `find` command, one can use the following syntax in a terminal.

```apache
$ find . -size +1k -size -50k
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676716429877/136ed538-ba76-4ca0-acb0-172f0832c5fc.png align="center")

## Conclusion

The `find` command is a powerful and flexible tool for searching and identifying files within a specific size range on a computer or file system. By using the `-size` option in combination with other options such as `-type` and specify a range of file sizes, and users can quickly and easily search for files that meet their specific needs. This can be particularly useful for managing disk space, identifying large or small files, or searching for specific types of files. While the syntax for using the `find` command can be complex, with a bit of practice, it can become a valuable tool for file management and organization, you can also check the man page of the find command.

That's all! Thank you for getting this far. I hope you find this article useful. If you did find this article valuable.

Toss us a follow for more amazing articles on Linux, Networking etc

And be sure to share with other Linux folks who you think it might be useful to them.