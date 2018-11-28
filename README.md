# Assignment 4
### Week 24th to 28th Sept

The week from sept 24th to 28th had discussions on naming in distributed systems. As in Project 3 we will be using distributed hash tables for naming purposes, I decided to implement a rpc system using rabbitmq message broker as this weeks assignment. 

In the rpc system, I tried to implement a simplistic approach of the an application of rpc listed [here](https://www.w3.org/History/1992/nfs_dxcern_mirror/rpc/doc/Introduction/ExampleApplications.html) which provides remote file access. I stripped the application down in order to execute `cat` unix command on a remote server and return the contents of file present at that location. Let's call that `cat-remote`

#### Prerequisites
- [RabbitMQ](https://www.rabbitmq.com/download.html)
- [GoLang](https://golang.org/dl/)

#### Building
- Compile the `rpc_server.go` file
```
go build rpc_server.go
```
- Compile the `cat-remote.go` file
```
go build cat-remote.go
```
#### Execution

- Execute the `rpc_server.go`
```
go run rpc_server.go
```
-Execute `cat-remote`
```
./cat-remote <filename>
```

For example,
```
./cat-remote file.txt
```
This should return the file contents

Let's try to execute `cat-remote` for a file that doesn't exist
```
./cat-remote file2.txt
```
This will gives us the following error, 
```
2018/10/05 22:03:46  [x] Requesting readfile(file2.txt)
2018/10/05 22:03:46  [.] Got Error retrieving file file2.txt: open file2.txt: no such file or directory
```


