## Command for the analysis

```sh
ls -ltr ~/ | tr -s ' ' | cut -d ' ' -f 9 | xargs -I {} echo {} | xargs -I {} ls -ltr ~/{}
```

#### What this does?

It will list out directory/files present in the home directory, then squeeze the multiple consecutive space character to a single space character results from the
individual line of previous command. 


#### This command will help us to understand:-

1) Linux pipeline
2) Basic command - ls, tr, cut
3) Why xargs is required when command pipeline is used
