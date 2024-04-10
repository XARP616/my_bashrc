# Bash tricks

## grep

```bash
grep -v                        # exclude from results
grep -rnwl [dir] -e [expr]     # find string recursively in files. Remove l to show contents
grep --color=always -z [expr]  # highlight the expression, but do not hide the rest of the results
```
