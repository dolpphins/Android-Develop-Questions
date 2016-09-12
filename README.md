Android开发常见问题
=====================

1.Android Studio提示Error：Configuration with name ‘default’ not found

解决方法：Project的settings.gradle文件中include了不存在的工程，删去即可。

2.Android Studio报Error：File path too long on Windows, keep below 240 characters

解决方法：在主工程的build.gradle中的allprojects节点中添加buildDir = "C:/tmp/${rootProject.name}/${project.name}"，即：
```
allprojects {
    buildDir = "C:/tmp/${rootProject.name}/${project.name}"
    repositories {
       ...
    }
}
```

3.Android Studio导入项目时下载制定版本的gradle文件过慢

解决方法：手动下载相应版本的gradle文件，然后复制到C:\Users\{用户名}\.gradle\wrapper\dists\{gradle文件全名}\{一串字符串}\ 目录下，Android Studio会自动创建该目录，然后重启Android Studio即可。
