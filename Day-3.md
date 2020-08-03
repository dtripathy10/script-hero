
### How to get the file name from the absolute path

```sh
pwd | xargs -I {} echo "{}/keeper/FileName.txt" | sed -e 's/.*\///g'
```
### How to get the directory name from the absolute path

```sh
pwd | xargs -I {} echo "{}/keeper/FileName.txt" | sed -e 's/\(.*\/\).*/\1/g'
```


For more example, I've followed these below blogs:-

1) https://www.thegeekstuff.com/2009/09/unix-sed-tutorial-printing-file-lines-using-address-and-patterns/

