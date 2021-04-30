# Translate2MinizincData
这个工具的用途是通过描述输入格式（这里主要面对的是NOIP的题目输入）生成一个Translator，它可以将输入数据转为适用于Minizinc的输入文件。
## 语法
支持声明变量、输入、输出三种操作。
* 变量类型int,float,string，声明变量的语句形如`int n;`数组的声明方式为`array[n][m] of int candies;`目前仅支持1维和2维数组，注意声明数组的时候数组长度n和m必须已经完成输入，具体示例可以见test.txt文件。
* 输入变量的语句形如`input:n;`
* 输出变量的语句形如`output:n;`输出数组的语句形如`output:candies;`
* 支持简单的循环，形如`for i in range(n){ }` 同样，这里的n需要已经完成输入。
## 运行
* 在Translate2MinizincData.jar所在的目录下（假定在D:/），执行`java -jar D:/Translate2MinizincData.jar test.txt`，（注意这里的jar文件需求绝对路径）其中test.txt是输入描述文件，如果不使用这一参数那么可以在命令行中输入（以CTRL+z结束）。这样能得到一个Translator.java文件。
* 执行`javac -cp .;Translate2MinizincData.jar Translator.java`
* 执行`java -cp .;Translate2MinizincData.jar Translator testdata.txt`，其中testdata.txt是题目的输入数据文件（暂不支持命令行输入），将会得到一个testdata.dzn文件。
## 说明
目前阶段支持的语法还十分简单，对于一些输入可能还无法处理，后续会有更新。
