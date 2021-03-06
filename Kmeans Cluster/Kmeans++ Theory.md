# Kmeans & Kmeans++ 
-------------


* **Kmeans 聚类**

样本集合<a href="http://www.codecogs.com/eqnedit.php?latex=X=\begin{pmatrix}&space;X_{1},&space;&X_{2},&space;&&space;\cdots&space;,&&space;X_{N}&space;\end{pmatrix}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X=\begin{pmatrix}&space;X_{1},&space;&X_{2},&space;&&space;\cdots&space;,&&space;X_{N}&space;\end{pmatrix}" title="X=\begin{pmatrix} X_{1}, &X_{2}, & \cdots ,& X_{N} \end{pmatrix}" /></a>， <a href="http://www.codecogs.com/eqnedit.php?latex=N" target="_blank"><img src="http://latex.codecogs.com/gif.latex?N" title="N" /></a>为样本个数。<a href="http://www.codecogs.com/eqnedit.php?latex=X_{i}=\begin{bmatrix}&space;X_{i}^{1}&space;&&space;X_{i}^{2}&\cdots&space;&&space;X_{i}^{m}&space;\end{bmatrix}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{i}=\begin{bmatrix}&space;X_{i}^{1}&space;&&space;X_{i}^{2}&\cdots&space;&&space;X_{i}^{m}&space;\end{bmatrix}" title="X_{i}=\begin{bmatrix} X_{i}^{1} & X_{i}^{2}&\cdots & X_{i}^{m} \end{bmatrix}" /></a>，<a href="http://www.codecogs.com/eqnedit.php?latex=m" target="_blank"><img src="http://latex.codecogs.com/gif.latex?m" title="m" /></a>为每个样本的特征个数。

要把这些样本分为<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>类，<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别的样本集合分别为<a href="http://www.codecogs.com/eqnedit.php?latex=\begin{matrix}&space;C1,&&space;C2,&&space;\cdots,&space;&&space;Ck&space;\end{matrix}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\begin{matrix}&space;C1,&&space;C2,&&space;\cdots,&space;&&space;Ck&space;\end{matrix}" title="\begin{matrix} C1,& C2,& \cdots, & Ck \end{matrix}" /></a>。


得到的<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别要使得下式取得最小值：

<a href="http://www.codecogs.com/eqnedit.php?latex=D&space;=&space;\sum_{k=1}^{K}\sum_{i=1}^{nk}dis(X_{ki}-Ckc)" target="_blank"><img src="http://latex.codecogs.com/gif.latex?D&space;=&space;\sum_{k=1}^{K}\sum_{i=1}^{nk}dis(X_{ki}-Ckc)" title="D = \sum_{k=1}^{K}\sum_{i=1}^{nk}dis(X_{ki}-Ckc)" /></a>

其中<a href="http://www.codecogs.com/eqnedit.php?latex=nk" target="_blank"><img src="http://latex.codecogs.com/gif.latex?nk" title="nk" /></a>表示第<a href="http://www.codecogs.com/eqnedit.php?latex=k" target="_blank"><img src="http://latex.codecogs.com/gif.latex?k" title="k" /></a>个类别的样本集合中样本的个数；<a href="http://www.codecogs.com/eqnedit.php?latex=Ckc" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Ckc" title="Ckc" /></a>表示第<a href="http://www.codecogs.com/eqnedit.php?latex=k" target="_blank"><img src="http://latex.codecogs.com/gif.latex?k" title="k" /></a>个类别的中心；<a href="http://www.codecogs.com/eqnedit.php?latex=X_{ki}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{ki}" title="X_{ki}" /></a>表示第<a href="http://www.codecogs.com/eqnedit.php?latex=k" target="_blank"><img src="http://latex.codecogs.com/gif.latex?k" title="k" /></a>个类别的样本集合中的第<a href="http://www.codecogs.com/eqnedit.php?latex=i" target="_blank"><img src="http://latex.codecogs.com/gif.latex?i" title="i" /></a>个样本。<a href="http://www.codecogs.com/eqnedit.php?latex=dis(X_{ki}-Ckc)" target="_blank"><img src="http://latex.codecogs.com/gif.latex?dis(X_{ki}-Ckc)" title="dis(X_{ki}-Ckc)" /></a>表示第<a href="http://www.codecogs.com/eqnedit.php?latex=k" target="_blank"><img src="http://latex.codecogs.com/gif.latex?k" title="k" /></a>个类别的样本集合中的样本与该类别中心的距离。

 
* **不同的距离计算方式**
有两个点<a href="http://www.codecogs.com/eqnedit.php?latex=\mathbf{A,B}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\mathbf{A,B}" title="\mathbf{A,B}" /></a>, 坐标分别为<a href="http://www.codecogs.com/eqnedit.php?latex=\mathbf{A}=[a1,a2,\cdots,am]\begin{matrix}&space;&&space;\end{matrix}&space;\mathbf{B}=[b1,b2,\cdots,bm]" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\mathbf{A}=[a1,a2,\cdots,am]\begin{matrix}&space;&&space;\end{matrix}&space;\mathbf{B}=[b1,b2,\cdots,bm]" title="\mathbf{A}=[a1,a2,\cdots,am]\begin{matrix} & \end{matrix} \mathbf{B}=[b1,b2,\cdots,bm]" /></a>。

    + 欧几里得距离
   
   <a href="http://www.codecogs.com/eqnedit.php?latex=E(\mathbf{A,B})&space;=&space;\sqrt{\sum_{i=1}^{m}(ai-bi)^{2}}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?E(\mathbf{A,B})&space;=&space;\sqrt{\sum_{i=1}^{m}(ai-bi)^{2}}" title="E(\mathbf{A,B}) = \sqrt{\sum_{i=1}^{m}(ai-bi)^{2}}" /></a>
 
   + 曼哈顿距离
   
   <a href="http://www.codecogs.com/eqnedit.php?latex=M(\mathbf{A,B})&space;=&space;\sum_{i=1}^{m}\left&space;|&space;ai-bi&space;\right&space;|" target="_blank"><img src="http://latex.codecogs.com/gif.latex?M(\mathbf{A,B})&space;=&space;\sum_{i=1}^{m}\left&space;|&space;ai-bi&space;\right&space;|" title="M(\mathbf{A,B}) = \sum_{i=1}^{m}\left | ai-bi \right |" /></a>
   
   
   + 闵可夫斯基距离
  
   <a href="http://www.codecogs.com/eqnedit.php?latex=HM(\mathbf{A,B})&space;=&space;\begin{pmatrix}&space;\sum_{i=1}^{m}(ai-bi)^{p}&space;\end{pmatrix}&space;^{1/p}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?HM(\mathbf{A,B})&space;=&space;\begin{pmatrix}&space;\sum_{i=1}^{m}(ai-bi)^{p}&space;\end{pmatrix}&space;^{1/p}" title="HM(\mathbf{A,B}) = \begin{pmatrix} \sum_{i=1}^{m}(ai-bi)^{p} \end{pmatrix} ^{1/p}" /></a>
    

根据样本特征选择不同的距离公式，本算例采用欧几里得距离。



* **Kmeans 聚类步骤**

     1. 随机选择<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别中心<a href="http://www.codecogs.com/eqnedit.php?latex=\begin{matrix}&space;C1c,&&space;C2c,&&space;\cdots,&space;&&space;Ckc&space;\end{matrix}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\begin{matrix}&space;C1c,&&space;C2c,&&space;\cdots,&space;&&space;Ckc&space;\end{matrix}" title="\begin{matrix} C1c,& C2c,& \cdots, & Ckc \end{matrix}" /></a>；
     
     
     2. 对每一个样本计算和<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别中心的距离，找到距离最小的<a href="http://www.codecogs.com/eqnedit.php?latex=Ckc" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Ckc" title="Ckc" /></a>，
     
     然后将该样本添加到样本集合<a href="http://www.codecogs.com/eqnedit.php?latex=Ck" target="_blank"><img src="http://latex.codecogs.com/gif.latex?Ck" title="Ck" /></a>中；
     
     3. 计算得到的<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别的样本集合中样本的均值，作为新的<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别中心；
     
     4. 满足迭代次数或者类别<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个类别中心不再变化，则停止。
    
     
Kmeans聚类算法的结果会因为初始的类别中心的不同差异很大，为了避免这个缺点，下面介绍对初始类别中心的选择进行了优化的**Kmeans++聚类**算法。

* **Kmeans++聚类步骤**


    1. 从样本集合中随机选择一个样本作为第1个类别中心；
    
    2. 对于样本集合中的每一个样本<a href="http://www.codecogs.com/eqnedit.php?latex=X_{i}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?X_{i}" title="X_{i}" /></a>，计算其与上一个刚被选择成为
    
    类别中心的样本之间的距离<a href="http://www.codecogs.com/eqnedit.php?latex=dis" target="_blank"><img src="http://latex.codecogs.com/gif.latex?dis" title="dis" /></a>；

    3. <a href="http://www.codecogs.com/eqnedit.php?latex=dis" target="_blank"><img src="http://latex.codecogs.com/gif.latex?dis" title="dis" /></a>较大的样本，被选取作为类别中心的概率较大；
    
    4. 重复步骤<a href="http://www.codecogs.com/eqnedit.php?latex=\textrm{ii}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\textrm{ii}" title="\textrm{ii}" /></a>和<a href="http://www.codecogs.com/eqnedit.php?latex=\textrm{iii}" target="_blank"><img src="http://latex.codecogs.com/gif.latex?\textrm{iii}" title="\textrm{iii}" /></a>直到<a href="http://www.codecogs.com/eqnedit.php?latex=K" target="_blank"><img src="http://latex.codecogs.com/gif.latex?K" title="K" /></a>个初始的类别中心被选出；
    
    5. 进行Kmeans算法。


     



            
            
        

            
            


