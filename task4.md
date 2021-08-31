1. What is the option used to view the content of a compressed file.

    ```
    $ tar fvt
    ```

2. Backup /etc directory using tar utility.

    ```
    $ tar fcv archive_etc.tar /etc
    ```
    
3. List the inode numbers of /, /etc, /etc/hosts.

    ```
    ls -i /   ;  ls -i /etc ; ls -i /etc/hosts
    ```

4. Copy /etc/passwd to your home directory, use the commands diff and cmp, and Edit in the file you copied, and then use these commands again, and check the output.

    ``` 
    cp /etc/passwd ~  ;
    diff ~/passwd /etc/passwd ;
    cmp ~/passwd /etc/passwd ;
    diff ~/passwd /etc/passwd ;
    cmp ~/passwd /etc/passwd ;
    ```

5. Create a symbolic link of /etc/passwd in /boot.

```
 sudo ln -s /etc/passwd /boot
```

6. Create a hard link of /etc/passwd in /boot. Could you? Why?

```
 sudo ln -s /etc/passwd /boot
```

``` Yes,  because hard link on the same partition ```
