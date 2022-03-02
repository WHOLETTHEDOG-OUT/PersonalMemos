


以十月份遇到的独狼Rootkit为例，

stage0.exe释放了stage1.sys,

stage1.sys中包含两个解密函数，一个用于解密stage2.dll，一个用于解密字符串，

（1）解密PE的函数如下

这种类型的代码单纯进行了大量的算术运算，接受参数一个是cipher.data, 另一个是 cipher.len，

因此很适合用Unicorn来执行这段代码，以自动解密
![image](https://github.com/WHOLETTHEDOG-OUT/MalwareAnalysisSkills/blob/main/1.Unicorn%E5%9C%A8%E6%A0%B7%E6%9C%AC%E5%88%86%E6%9E%90%E7%8B%AC%E7%8B%BCRootkit%E6%97%B6%E7%9A%84%E5%BA%94%E7%94%A8/img/DecryptFunc.code.png)
