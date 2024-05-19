# Bash tricks

## grep

```bash
grep -v                        # exclude from results
grep -rnwl [dir] -e [expr]     # find string recursively in files. Remove l to show contents
grep --color=always -z [expr]  # highlight the expression, but do not hide the rest of the results
```
[Stack overflow](https://stackoverflow.com/questions/16956810/find-all-files-containing-a-specific-text-string-on-linux#answer-16957078)
