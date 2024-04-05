# Manipulate folders
 **Create a new directory**
```
mkdir [directory_name]
```

 **Rename files or folders**
```
ren [old_name] [new_name]
```

 **Delete a directory**
```
rmdir [directory_name]
```

---

> Note: You can use the `/s` option to delete a directory and all its contents recursively.

# Manipulate files

**Create a new file**
- Create an empty file
	```
	type nul > [filename.extension]
	```
- Create a new file and enter text into it
	```
	type [text] > [filename.extension]
	```

**Rename files or folders**
```
ren [old_name] [new_name]
```

**Copy files from one location to another**
```
copy [source_file] [destination_directory_path]
```

**Move files from one location to another**
```
move [source_file] [destination_directory_path]
```

**Delete files**
```
del [file_name]
```

---

> Type `[command] /?` to get more information about each command and its options.