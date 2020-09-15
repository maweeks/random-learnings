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
lsof -i :xxx | awk '{system("kill -9 " $2)}'

lsof -i :xxx
kill -9 [PID from previous]
```
