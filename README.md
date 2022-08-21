# Install VSCode in Termux

## To install vscode in Termux you need to install ubuntu first from [here.](https://github.com/ask9027/Install-Android-Studio-in-Termux/blob/main/install-ubuntu-on-termux.md)

### Download VS Code by following


```
sudo apt install gnupg
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys EB3E94ADBE1229CF

#Add vscode repo
echo "deb [arch=arm64,amd64,armhf signed-by=/etc/apt/trusted.gpg] http://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list

sudo apt update
sudo apt install code -y
```
### After install code need some changes to run code by following

```
#run this command
vi /usr/share/code/bin/code
```
and replace `ELECTRON_RUN_AS_NODE=1 "$ELECTRON" "$CLI" --ms-enable-electron-run-as-node "$@"` to `ELECTRON_RUN_AS_NODE=1 "$ELECTRON" "$CLI" --ms-enable-electron-run-as-node --no-sandbox --disable-gpu "$@"`.

now edit code launcher

```
vi /usr/share/applications/code.desktop

```

and replace `Exec=/usr/share/code-insiders/code-insiders --unity-launch %F` and `Exec=/usr/share/code-insiders/code-insiders --new-window %F` to `Exec=/usr/share/code-insiders/bin/code-insiders --new-window %F` and `Exec=/usr/share/code-insiders/bin/code-insiders --new-window %F`.

also change following file
```
vi /usr/share/applications/code-insiders-url-handler.desktop
```

and replace `Exec=/usr/share/code-insiders/code-insiders --open-url %U` to `Exec=/usr/share/code-insiders/bin/code-insiders --open-url %U`.

## Now you can use VS Code.
