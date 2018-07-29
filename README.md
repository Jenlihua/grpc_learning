#### 安装
1. 下载需要的安装包：https://github.com/google/protobuf/releases 
protoc-3.1.0-win32.zip
protobuf-java-3.1.0.zip
2. 将protoc-3.1.0-win32中的protoc.exe拷贝到c:\windows\system32中 
3. 将proto.exe文件拷贝到解压后的protobuf-3.1.0\src目录中 
4. protobuf-3.1.0\java 目录下执行maven package命令编辑该包 生成protobuf-java-3.1.0.jar文件（这一步相当于安装了,位于protobuf-3.1.0\java\core\target目录中）

#### 原生命令生成java文件：
cmd module
1.  打开dos命令行，进入到D:/src目录下，先执行命令：protoc  --java_out=d:/src rpc_demo.proto，生产对应的序列化文件；
2.  然后再执行命令：protoc --plugin=protoc-gen-grpc-java=d:/src/protoc-gen-grpc-java-1.8.0-windows-x86_64.exe --grpc-java_out=d:/src/ rpc_demo.proto

####maven 方式：
grpc_maven module
1.  pom配置 https://github.com/Jenlihua/grpc-java
2.  在src/main/protos(pom.xml中配置)目录下编辑 .proto文件
3.  mvn build