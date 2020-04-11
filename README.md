# typo3 hook list
List of potential hooks found in TYPO3 LTS 8,9,10


I run this script from the /typo3 folder of each LTS release to get a list of what might be hooks:

```bash
grep -roh "foreach (\$GLOBALS\['TYPO3_CONF_VARS'\]\['SC_OPTIONS'\].*as " . | sed 's/foreach (\(.*\) as/\1/' | sed 's/\(.*\)?? \[\]/\1/' | awk '{$1=$1};1' | uniq
```
