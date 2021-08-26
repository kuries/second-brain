- How to unrar a .rar file
```bash
unrar lb javase_course_material.rar | perl -ne 'chomp; -d ? rmdir : unlink'
```

- How to untar a .tar file
```bash
tar -C /myfolder -xvf file_name.tar
```

- change the file or directory name
```bash
mv /home/user/oldname /home/user/newname
```