# jq Recipes

Extract all domains from a HAR file

```jq
cat ${HAR_FILE} | jq '.log.entries[].request.url' | sed -r "s/\"http[s]:\/\/([^/]*)\/.*/\1/" | sort | uniq
```
