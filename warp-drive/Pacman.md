### fix \(invalid or corrupted package \(PGP signature\)\)
```warp-runnable-command
sudo pacman-key --init
sudo pacman-key --populate
```
### error\: failed to commit transaction \(conflicting files\)
eg\: `kguiaddons: /usr/bin/kde-geo-uri-handler exists in filesystem (owned by kguiaddons5)`
```warp-runnable-command
sudo pacman -S --overwrite '*' <PKG_NAME>
sudo pacman -S --overwrite '*' kdeconnect
```
