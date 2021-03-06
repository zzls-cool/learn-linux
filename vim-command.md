# vim快捷键操作  
## 移动光标
```c  
h			   //左  
j              //下  
k		       //上  	
l              //右  
Ctrl+f       //向下翻一页  
Ctrl+b       //向上翻一页  
Ctrl+d       //向下翻半页  
Ctrl+u       //向上翻半页  
+            //光标移动到非空格符的下一行  
-            //光标移动到非空格符的上一行  
n<space>     //按下数字后再按空格键，光标会向右移动这一行的 n 个字符  
0/Home       //移动到这一行的最前面字符处  
$/End        //移动到这一行的最后面字符处  
H	         //光标移动到这个屏幕的最上方那一行的第一个字符  
M	         //光标移动到这个屏幕的中央那一行的第一个字符  
L	         //光标移动到这个屏幕的最下方那一行的第一个字符  
G	         //移动到这个档案的最后一行(常用)  
nG	         //移动到这个档案的第 n 行  
gg	         //移动到这个档案的第一行  
n<Enter>	 //光标向下移动 n 行  
```  
## 搜索替换  
```c
/word	     //向光标之下寻找一个名称为 word 的字符串  
?word	     //向光标之上寻找一个字符串名称为 word 的字符串  
n	         //这个 n 是英文按键。代表重复前一个搜寻的动作  
N	         //这个 N 是英文按键。与 n 刚好相反，为『反向』进行前一个搜寻动作  
:n1,n2s/word1/word2/g	  //n1 与 n2 为数字。在第 n1 与 n2 行之间寻找 word1 这个字符串，并将该字符串取代为 word2  
:1,$s/word1/word2/g 或 :%s/word1/word2/g	 //从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2  
:1,$s/word1/word2/gc 或 :%s/word1/word2/gc	 //从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2  
```  
## 删除、复制与粘贴    
```c
x, X	        //在一行字当中，x 为向后删除一个字符， X 为向前删除一个字符  
nx	            //n 为数字，连续向后删除 n 个字符  
dd	            //删除游标所在的那一整行  
ndd	            //n 为数字。删除光标所在的向下 n 行  
d1G	            //删除光标所在到第一行的所有数据  
dG	            //删除光标所在到最后一行的所有数据  
d$	            //删除游标所在处，到该行的最后一个字符  
d0	            //那个是数字的 0，删除游标所在处，到该行的最前面一个字符  
yy	            //复制游标所在的那一行(常用)  
nyy	            //n 为数字。复制光标所在的向下 n 行，例如 20yy 则是复制 20 行(常用)  
y1G	            //复制游标所在行到第一行的所有数据  
yG	            //复制游标所在行到最后一行的所有数据  
y0	            //复制光标所在的那个字符到该行行首的所有数据  
y$	            //复制光标所在的那个字符到该行行尾的所有数据  
p, P	        //p 为将已复制的数据在光标下一行贴上，P 则为贴在游标上一行  
J	            //将光标所在行与下一行的数据结合成同一行  
c	            //重复删除多个数据，例如向下删除 10 行，[ 10cj ]  
u	            //复原前一个动作。(常用)  
[Ctrl]+r	    //重做上一个动作。(常用)  
.	            //重复前一个动作  
```  
## 进入输入或取代的编辑模式  
```c
i, I	        //进入输入模式(Insert mode)：i为『从目前光标所在处输入』， I 为『在目前所在行的第一个非空格符处开始输入』。 (常用)  
a, A	        //进入输入模式(Insert mode)：a 为『从目前光标所在的下一个字符处开始输入』， A 为『从光标所在行的最后一个字符处开始输入』。(常用)  
o, O	        //进入输入模式(Insert mode)：这是英文字母 o 的大小写。o 为在目前光标所在的下一行处输入新的一行； O 为在目前光标所在的上一行处输入新的一行！(常用)  
r, R	        //进入取代模式(Replace mode)：r 只会取代光标所在的那一个字符一次；R会一直取代光标所在的文字，直到按下 ESC 为止；(常用)  
[Esc]	        //退出编辑模式，回到一般模式中(常用)  
```
## 指令行的储存、离开等指令
```c
:w	             //将编辑的数据写入硬盘档案中(常用)
:w!	             //若文件属性为『只读』时，强制写入该档案
:q	             //离开 vi (常用)
:q!	             //若曾修改过档案，又不想储存，使用 ! 为强制离开不储存档案。
:wq	             //储存后离开，若为 :wq! 则为强制储存后离开 (常用)
ZZ               //如果修改过，保存当前文件，然后退出
ZQ    	         //不保存，强制退出。效果等同于 :q!。
:w [filename]	        //将编辑的数据储存成另一个档案（类似另存新档）
:r [filename]	        //在编辑的数据中，读入另一个档案的数据。亦即将filename这个档案内容加到游标所在行后面
:n1,n2 w [filename]	   //将 n1 到 n2 的内容储存成 filename 这个档案。
:! command	           //暂时离开 vi 到指令行模式下执行 command 的显示结果
```  
## vim 环境的变更  
```c
:set nu	        //显示行号  
:set nonu       //取消行号  
```