说linux cd命令是Linux上使用率最高的两个命令之一不为过吧（另一个当然是ls了），前两天看到了一个linux cd命令的小技巧是我一直都不知道的，呵呵，这里顺便记下来。

cd -          #回到上次所在目录，这个技巧我原来还真是不知道，感觉还是比较有用，省略了很多输入。

cd !$          #把上个命令的参数作为输入。

cd           #回到主目录

cd ~         #同样也是回到主目录

下面连贯的做一个例子来说明：

引用

ocean@flower-laptop:~$ pwd     #查看当前目录路径

/home/ocean                                   

ocean@flower-laptop:~$ sudo tar xf wordpress.tar.gz -C /opt/lampp/htdocs/wordpress   #解压压缩包到/opt/lampp/htdocs/wordpress目录

ocean@flower-laptop:~$ cd !$       #执行linux cd  !$把上个命令最后的参数作为输入，即/opt/lampp/htdocs/wordpress

cd /opt/lampp/htdocs/wordpress                   

ocean@flower-laptop:/opt/lampp/htdocs/wordpress$ pwd          #查看当前目录路径

/opt/lampp/htdocs/wordpress           

ocean@flower-laptop:/opt/lampp/htdocs/wordpress$ cd   #执行linux cd命令回到了主目录

ocean@flower-laptop:~$ pwd    #查看当前目录路径

/home/ocean                                    

ocean@flower-laptop:~$ cd -    #执行linux cd -，回到上次所在目录。

/opt/lampp/htdocs/wordpress                      

ocean@flower-laptop:/opt/lampp/htdocs/wordpress$ pwd  #查看当前目录路径

/opt/lampp/htdocs/wordpress           

这样应该能看明白linux cd命令如何使用了吧。

#### Reference:

  * http://os.51cto.com/art/200907/140868.htm
