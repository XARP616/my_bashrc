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

## Short circuit evaluation and one lines in bash
```bash
# Commands run consecutively, no matter the result
$ false ; echo "OK"
  OK
$ true  ; echo "OK"
  OK

# The first must success for the 2nd to execute
$ false && echo "OK"
$ true  && echo "OK"
  OK

# Stops when a statement evaluates as true
$ false || echo "OK"
  OK
$ true  || echo "OK"  # Since the first statement evaluated
$                     # successful, the 2nd one does not execute
```
* [Read here](https://unix.stackexchange.com/questions/88850/precedence-of-the-shell-logical-operators#answer-88851)
* [Read here](https://unix.stackexchange.com/questions/187145/whats-the-difference-between-semicolon-and-double-ampersand#187148)

## Strip first chars of a string
```bash
var="pid: 1234"
var=${var:5}
```
[](https://stackoverflow.com/questions/11469989/how-can-i-strip-first-x-characters-from-string-using-sed#answer-11470727)
