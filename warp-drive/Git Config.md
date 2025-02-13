### Configure Git Credentials
```warp-runnable-command
USERNAME="Mahmoud Mohamed (00xWolf - Gmail/GitHub: @mmsaeed509)"
E_MAIL="mmsaeed509@gmail.com"

git config --global user.name ${USERNAME}
git config --global user.email ${E_MAIL}
```
### set the default editor for commit msg
```warp-runnable-command
git config --global core.editor "nvim"
```
### raising the postBuffer size
```warp-runnable-command
git config --global http.postBuffer 524288000
```
### cache your credentials \(in my case\, it\'s useful for using GitLab\)
```warp-runnable-command
git config --global credential.helper cache  # caching your credentials for 15 min timeout

git config --global credential.helper 'cache --timeout=31536000'  # caching your credentials for 1-year timeout
```
### enables color output for Git commands globally
```warp-runnable-command
git config --global color.ui true
```
### error\: `RPC failed;`
```warp-runnable-command
Cloning into 'exodia-bspwm-Predator'...
remote: Enumerating objects: 5845, done.
remote: Counting objects: 100% (2100/2100), done.
remote: Compressing objects: 100% (700/700), done.
error: RPC failed; curl 92 HTTP/2 stream 5 was not closed cleanly: CANCEL (err 8)
error: 534 bytes of body are still expected
fetch-pack: unexpected disconnect while reading sideband packet
fatal: early EOF
fatal: fetch-pack: invalid index-pack output
failed to run git: exit status 128
```
to resolve it 
```warp-runnable-command
git config --global http.postBuffer 524288000
```
