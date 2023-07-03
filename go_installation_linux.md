#### Установка Go на компьютер с установленной OS Linux (терминал)
Команды выполнять по очереди не закрывая терминал:
```
cd $HOME
```
```
wget -O VERSION https://go.dev/VERSION?m=text && \
wget -O go.tar.gz https://dl.google.com/go/$(cat VERSION).linux-amd64.tar.gz && \
tar -xf go.tar.gz && rm go.tar.gz
```
```
mv .bashrc .bashrc.old && \
echo "export GOROOT=$HOME/go" >> .bashrc && \
echo "export GOPATH=$HOME/gopath" >> .bashrc && \
echo "export PATH=$PATH:$HOME/go/bin:$HOME/gopath/bin" >> .bashrc && \
cat .bashrc.old >> .bashrc && rm .bashrc.old
```
```
source .bashrc
```
```
go version
```
Если в результате вывелось что-то вроде ```go version go1.21rc2 linux/amd64``` установка прошла успешно.