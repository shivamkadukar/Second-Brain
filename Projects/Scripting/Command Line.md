In Linux, filenames aren’t required to represent the contents of the file. You can create a file called funny.gif that isn’t actually a GIF.
To find out what kind of file a file is
```bash
$ file banana.jpg
```

Read a file, combine multiple files and show output(concatenate)
```bash
$ cat banana.jpg apple.jpg
```

Displayed text from a text file page by page
```bash
$ less ${file_path}
```

List Down History of commands on bash
```bash
$ history
```

Run previous command 
```bash
$ !!
```

Search through previous commands to autocomplete
`Ctrl + R`

Copy a file 
```bash
cp ${file_to_copy} ${destination_path}

cp *.jpg ${destination_path} # copy all .jpg file to destination

# other wildcard characters
# - ? used to represent one character
# - [] used to represent any char withing the brackets

cp -r ${dir_to_copy} ${destination_dir} # copy all files recuresively

cp -i ${dir_to_copy} ${destination_dir} # prompt before overwriting a file
```

Move or Rename a file

```bash
mv ${file_name} ${new_file_name} #Rename a file or directory

mv ${file1} ${file2} ${destination_dir} # move a file or more files

mv -i {dir} {destination_dir} # prompt before overwriting

mv -b {dir} {destination_dir} # create backup of file instead of overwriting, rename old with ~
```

Make directory

```bash
mkdir {dir1} {dir2} # make one or more directories

mkdir -p {dir1/dir1_child/child1_child} # create dir and subdir at the same time 
```

Remove file or directory

```bash
rm ${file}

rm -f ${file}
```