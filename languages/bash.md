# Bash

Output to console and print to file, -a to append.

```bash
echo "any command" | tee myfile.txt;
```

Get my IP:

```bash
curl https://checkip.amazonaws.com;
```

Kill process using port xxx:

```bash
kill -9 `lsof -t -i :xxx`
```

Alias to `clearPort xxx` (add to `~/.zshrc`):

```bash
clearPort() {
    if [ -n "$1" ]
    then
        kill -9 `lsof -t -i :$1`
    else
        echo "Provide a port"
    fi
}
```

Use overwrite file used in command(s):

```bash
# Could do
echo '{"welcome":["hello"]}' > test.json && ## create example file
echo "$(jq '.welcome += ["world"]' < test.json)" > test.json &&
cat test.json ## show output

# Generally shouldn't pipe into same file though, better to have a temp one
echo '{"welcome":["hello"]}' > tmp/test.json &&
(jq '.welcome += ["world"]' < tmp/test.json) > tmp/test1.json &&
mv tmp/test1.json tmp/test.json
```
