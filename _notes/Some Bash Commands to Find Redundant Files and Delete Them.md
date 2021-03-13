---
title: Some Bash Commands to Find Redundant Files and Delete Them
tree_state: 🌱
---

### Run the following commands in terminal:

Here is how you can find the file name intersections between two directories, and write the names of the intersecting files to a file called `tmp.txt`
```
comm -12 <(ls dir_path_1) <(ls dir_path_2) > output_file.txt
```

Here is how you can read from the list of file names ( `output_file.txt`) and delete all files in your current directory that match the names in the list.
```
while read -r file; do rm -- "$file"; done < path_to_output_file.txt
```

Here is how you can move all the files from one directory, into another directory
```
mv  -v folder_path_to_move_from/* folder_path_to_move_to/
```