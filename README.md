#tagfs 
##about 
 
+ fuse based filesystem for taging and organizing your files 
+ it does not hold any files, only symbolic links to them 
+ you do not need to use another tool, only standard operation like rm, mv, ln 
+ can be used with any software that browses files 
+ tree based tagging
 
##usage 
mounting: 
```shell
./tagfs  mount_point [fuse_options]  [--db other_tags_database]` 
```
to get fuse options: 
```shell
./tagfs -h
```

example after mounting: 
```shell
cd $mount_point 
cd tags
mkdir foo #create foo tag 
ln -s some_file foo/ #tags file as foo 
ls foo/ #show files with tag foo
```
##building 
requirement: sqlite3, fuse, xxhash, vsqlite++ 
```shell
premake4 gmake
make
```
##TODO some features i would like to add
+ [ ] some type of 'fsck':
  + relink file
  + rehash file
  + find non-fallowable links
  + check if file is in database
  + list files that lost all tags
+ [ ] statistics for file, like all tags
+ [ ] basic searching
+ [ ] tag values, eg year=2000
+ [ ] fuzzy tags for query 
 