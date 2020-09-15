# Bash

Output to console and print to file, -a to append.

```bash
echo "any command" | tee myfile.txt;
```

Get my IP

```bash
curl https://checkip.amazonaws.com;
```

Kill process using port xxx

```bash
kill -9 `lsof -t -i :xxx`
```

Alias to `clearPort xxx`

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
