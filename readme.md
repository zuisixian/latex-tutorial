# latex 学习

## package下载地址
[package](http://mirrors.cqu.edu.cn/CTAN/macros/latex/)
这里面包含各种各样的package，直接下载后放入Style文件夹中进行引用。


ps:先在本地已经有个了这个仓库，需要把这个仓库上传。然后在github上新建了一个仓库，写了`.gitignore`和`License`，需要将这两个项目合并。
1. 关联远程仓库
`git remote add origin git@github.com:zuisixian/latex-tutorial.git`
2. git pull是遇到问题`Please specify which branch you want to merge with`

3. 指定本地`master`分支与远程`origin/master`分支的链接，根据提示，设置`master`和`origin/master`的链接：`git branch --set-upstream-to=origin/master master`

4. `git pull`还是遇到问题`fatal: refusing to merge unrelated histories`

5. 解决方法：`git pull origin master --allow-unrelated-histories`，原因：两个不同的项目合并。





## 添加图片
``` tex
  \begin{figure}
    \includegraphics[width=\linewidth]{image/qwe.jpg}
    \caption{A CAT.}
    \label{fig:cat1}
  \end{figure}
```
使用 `\ref{fig:cat1}`来进行引用, `\ref`和`\label`成对出现。

##设置目录显示深度

在document之前
`\setcounter{tocdepth}{2} % Show sections`

`\tableofcontents % 显示目录`

在section之中
`\addtocontents{toc}{\setcounter{tocdepth}{1}} % Set depth to 1`

## 添加参考文献
1. 新增 *.bib文件，在这个文件里面添加参考文献。
```
@BOOK{melissa:1,
AUTHOR="melissa Yang",
TITLE="THE REFERENCE ARTICLE",
PUBLISHER="NONE",
YEAR="2018",
}

```


2. 在正文中进行引用，`\cite{melissa:1}`



生成PDF命令
```
pdflatex first.tex
bibtex first
pdflatex first.tex
pdflatex first.tex

```


## 使用问题
Latex错误：The remote package repository is not registered. You have to choose another repository. 

解决办法： 

1. MikTex Package manager => Repository => Change Package Repository => Package shall be installed from the Internet => 下一步 => 完成，这样就连接上网络了。 
2. 然后再MikTex Package manager => Repository => Synchronize 就完成同步了。 
3. 然后再找到需要安装的宏包，选中，+号，即可。 






