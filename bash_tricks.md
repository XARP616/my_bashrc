# Bash tricks

## grep

```bash
grep -v                        # exclude from results
grep -rnwl [dir] -e [expr]     # find string recursively in files. Remove l to show contents
grep --color=always -z [expr]  # highlight the expression, but do not hide the rest of the results
```
[Stack overflow](https://stackoverflow.com/questions/16956810/find-all-files-containing-a-specific-text-string-on-linux#answer-16957078)

## One line for processing lines/files.
This example adds a tab (`\t`) to the dumped file.
```bash
for item in *; do echo ${item}; cat ${item} | while read -r; do echo "  ${REPLY}"; done; echo ""; done
```
