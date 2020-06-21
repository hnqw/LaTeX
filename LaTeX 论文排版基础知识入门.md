这两天忙一个课程作业 我们课程要求是随便用一个IEEE模板完成一次论文排版。


# 前期工作
首先准备工作做好。
*我们上网下载LaTeX论文模板。
链接：[https://journals.ieeeauthorcenter.ieee.org/create-your-ieee-journal-article/authoring-tools-and-templates/tools-for-ieee-authors/ieee-article-templates/](模板选择器)
![首页选择](https://img-blog.csdnimg.cn/20200621193053579.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
左侧选择 ： IEEE Article Templates
右侧点击 蓝字：IEEE Template Selector
如上图所示。
进入后如图所示 一步一步选择
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621193848817.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
翻译一下{选择你要找的模板}
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621193940373.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
下一步是看出版物（你可以直接搜索）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621194042501.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
选择文章类型 直接选  下一步选择格式的时候 选择LaTeX
直接下载
目前我们的准备工作就算是做好了。

接下来点开下载的文件夹
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621194521186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)

以此为例（我的文件夹编译过 所以比较多文件 不要在意这些细节 继续看）找到   ==bare_jrnl.tex==  这个文件用winedt打开
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621194852936.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
发现里面有一堆代码  不要慌听我说 灰色的你都需用管他 前面带%都是注释。下面你看到的 这一张图里都是注释。
我知道你们都不爱读，其实问题不大，也没啥大用 ，继续看。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621195036416.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
往下看 你终于遇见一行带颜色的代码：
~~~
\documentclass[journal]{IEEEtran}
~~~
这句话是说格式的不用管它 放着别动
~~~
 
\ifCLASSINFOpdf
   
\else
 
\fi
  
\hyphenation{op-tical net-works semi-conduc-tor}

~~~
这几句也不动看 反正别动他就对了


接来来激动了 终于进入正文了


我补充点LaTeX的常识： ==重点==

# 一、章节问题
这样会不会好理解一点，就是这样用：
~~~
\section{Introduction}
这里写大标题 例如1  2  3  
\subsection{Subsection Heading Here}
这里写下面的下标题例如 1.1  2.1   3.1 
\subsubsection{Subsubsection Heading Here}
这里写的是下一标题的标题例如 1.1.1 2.1.1 3.1.1

~~~

# 二、 插入表格table
前提导入一个库
~~~
\usepackage{picinpar,graphicx}
~~~
写上这句话（写在下图这个位置，建议这三个都导入）
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621210934477.png)
表格好整一些因为我找到了在线做表格的网站
链接：https://www.tablesgenerator.com/latex_tables
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621202247733.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
在网站填好表摁generate 下面代码就生成了
可以直接复制。
~~~
\begin{table}[!t]
\renewcommand{\arraystretch}{1.3}
\caption{An Example of a Table}
\label{table_example}
\centering
\begin{tabular}{|c||c|}
\hline
One & Two\\
\hline
Three & Four\\
\hline
\end{tabular}
\end{table}

~~~


caption这个后面写table标题
举个我自己的例子
~~~
\begin{table}[!t]
\caption{ Distribution of ISCX-IDS 2012 training and testing dataset.}
\begin{tabular}{cccc}
\hline
Dataset/Network Flows & \#Feature & Training       & Testing        \\ \hline
ISCX-UNB Saturday     & 8         & 85,222 1353    & 45,889 1353    \\
ISCX-UNB Monday       & 8         & 108,945 2451   & 58,664 1320    \\
ISCX-UNB Tuesday      & 8         & 347,308 24,295 & 187,012 13,083 \\
ISCX-UNB Wednesday    & 8         & 339,470 0      & 182,793 0      \\
ISCX-UNB Thursday     & 8         & 255,054 3381   & 137,338 1822   \\ \hline
\end{tabular}
\end{table}
~~~
# 三、 插入图figure
~~~
\begin{figure}[!t]
\centering
\includegraphics[width=2.5in]{写picture.png/jpg等格式的图片}
\caption{Simulation results for the network.}
\label{fig_sim}
\end{figure}
~~~
文章里面有注释有写这个，所以就按这个格式来写
看好[!t]、[width=2.5in]这个是不能缺的 ，缺了图就不一定长啥样宽了窄了就不好说了
caption这个后面写图figure标题
还有图片一定要和.tex文件在同一目录下。
举个我自己的例子

~~~
\begin{figure}[!t]
\centering
\includegraphics[width=2.5in]{picture1.jpg}
\caption{An overview of the proposed ID model}
\label{fig_sim}
\end{figure}
\subsection{Datasets}
~~~

# 四、插入公式
公式的话直接写 问题不大
前面也需要写上这么一句话
~~~
\usepackage{algorithm, algorithmic}
~~~
~~~
\begin{equation}
公式
\end{equation}
~~~
当然公式有在线网站的 
链接奉上：http://latex.codecogs.com/eqneditor/editor.php
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621202431470.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
举个自己的例子
~~~
\begin{equation}
TPR=DR=TP/(TP+FN)=x/(x+y)
\end{equation}
~~~
# 五、插入文献
这个位置难为了我两天 有两种方法，我就只讲一种了
讲一个简单的，但是工作量貌似有点大
（但如果是pdf改.tex就好办了）
（pdf已复制每句话前面填一个\bibitem{01}01 02就排下去不用动脑非常好用）
首先解释一下{99}这个可以按自己要用的文件数改  
比如你写了5个文献 你 { } 里就看可以写5 或者5以上的数
~~~
\begin{thebibliography}{99}

\bibitem{01}Xu, C.; Shen, J.; Du, X.; Zhang, F. An intrusion detection system using a deep neural network with gated recurrent units. IEEE Access 2018, 6, 48697–48707.
\bibitem{02}Vinayakumar, R.; Soman, K.P.; Poornachandran, P. Applying convolutional neural network for network intrusion detection. In Proceedings of the International Conference on Advances in Computing,Communications and Informatics (ICACCI), Udupi, India, 13–16 September 2017; pp. 1222–1228.
\bibitem{03}Sharma, S.; Gupta, R. Intrusion detection system: A review. Int. J. Secur. Its Appl. 2015, 9, 69–76.

\end{thebibliography}
~~~
这样文献插入你就完成一半了
另外一半在你的正文里面
举个例子
~~~
text  text   \cite{01}  text text 
~~~
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621204244142.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
纯手写出来 \cite{} 会自动跳出弹框选择数字 回车  或者直接输入数字回车或者insert
出现的样子就是[01]这样

比如[04,05]   你可以直接 \cite{} 手打数字04,05
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020062120472320.png)
[04-07]  你可以直接 \cite{} 手打数字04-07
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621204917665.png)
一篇论文就算是改完了 
# 六、编译
在编译的时候当初傻了吧唧自己摸索半天也没找到他们说的小闪电，怪我天真了，但凡给我张图 是吧 害。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621210514237.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FpeWloYW4=,size_16,color_FFFFFF,t_70)
在这个位置选择 ==pdflatex==  点击按钮 会在文件夹出现一个PDF 如果想再次编译需要把PDF删除（这个适用于你插入图片的时候）

（没插入图片）你可以选择LaTeX 那个选项 编译成功后选择同一排后面有个放大镜还写着div这个  就能直接查看文件了![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621205522776.png)
# 七、如何判断运行成功
运行一半怎么也不动了 还出现了   ==？== 就说明出现错误了
如果出现下图 就是成功了 虽然有警告和不好的表格 但已经算是完成了
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621211422287.png)
# 八、找运行错误
提示了line 哪行有错误  你可以让它显示哪行
右键点击左边小白条
选择show line number 你就可以自己找错误改错误啦
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621211108317.png)
# 九、提醒一点
~~~
\IEEEPARstart{I}{nformation}
~~~
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621211600531.png)
编译完是这个效果的 首字母变成这样   知道一下就行
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200621211707644.png)
我要说的就这么多 大家加油。又不懂可以问，一起研究。


补充：（模板的大框 我给单独拿出来了）
~~~
\begin{document}
\title{Bare Demo of IEEEtran.cls\\ for IEEE Journals}
\author{Michael~Shell,~\IEEEmembership{Member,~IEEE,}
        John~Doe,~\IEEEmembership{Fellow,~OSA,}
        and~Jane~Doe,~\IEEEmembership{Life~Fellow,~IEEE}% <-this % stops a space

\maketitle

 
\begin{abstract}
The abstract goes here.
\end{abstract}

 
\begin{IEEEkeywords}
IEEE, IEEEtran, journal, \LaTeX, paper, template.
\end{IEEEkeywords}

 \end{center}
 .
\IEEEpeerreviewmaketitle

\section{Introduction}
text 
\hfill mds

\hfill August 26, 2015

\subsection{Subsection Heading Here}
Subsection text here.

\subsubsection{Subsubsection Heading Here}
Subsubsection text here.

\section{Conclusion}
The conclusion goes here

\appendices
\section{Proof of the First Zonklar Equation}
Appendix one text goes here.

\section{}
Appendix two text goes here.

\section*{Acknowledgment}
The authors would like to thank...

\ifCLASSOPTIONcaptionsoff
  \newpage
\fi

\bibitem{IEEEhowto:kopka}
H.~Kopka and P.~W. Daly, \emph{A Guide to \LaTeX}, 3rd~ed.\hskip 1em plus
  0.5em minus 0.4em\relax Harlow, England: Addison-Wesley, 1999.

\end{thebibliography}

\begin{IEEEbiography}{Michael Shell}
Biography text here.
\end{IEEEbiography}

\begin{IEEEbiographynophoto}{John Doe}
Biography text here.
\end{IEEEbiographynophoto}
 
\begin{IEEEbiographynophoto}{Jane Doe}
Biography text here.
\end{IEEEbiographynophoto}

  
\end{document}

~~~
