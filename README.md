# 准备中的问题
## [灰沉积](http://cfd-china.com/topic/2053/%E5%88%86%E4%BA%AB-%E4%B8%80%E4%B8%AA-latex-%E8%AE%BA%E6%96%87%E6%A8%A1%E6%9D%BF/10)

## [等值面](http://cfd-china.com/topic/664/cd%E8%AE%A1%E7%AE%97%E4%B8%8D%E5%87%86%E7%9A%84%E9%97%AE%E9%A2%98-les-re3900-%E4%B8%89%E7%BB%B4%E5%9C%86%E6%9F%B1%E7%BB%95%E6%B5%81-pisofoam/1040)

> 再次打扰了，我想做一下尾部三维的涡结构，可是为什么创建 contour 等值面时，contour by 后面的选项只有压力 P 和 nut ，并没有后来 vorticity 命令计算出来的变量 vorticity，vorticity 只能以云图的形式出现，我需要怎样创建 wake 的结构呢？

因为你的数据中没有包含 vorticity。 通常来讲，你需要在后处理的过程中来处理。比如 ( OF v4.1 )：

```
pisoFoam -postProcess -func -vorticity
```

实际上，漩涡在数学上的定义是速度的旋度：curl of velocity

```latex
\begin{equations}
\omega = \nabla \cdot  V
\end{equations}
```
<a href="https://www.codecogs.com/eqnedit.php?latex=\omega&space;=&space;\nabla&space;\cdot&space;V" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\omega&space;=&space;\nabla&space;\cdot&space;V" title="\omega = \nabla \cdot V" /></a>


漩涡在流体力学中经常被用到，但是如果深入探讨这个概念，其实这不是一个假单的概念。

> The notion of a vortex is so widely used in fluid dynamics that few pause to examine what the word strictly means. Those who do take a closer look quickly realize the difficulty of defining vortices unambiguously.

Chong et al. (1990) 年的时候，用速度梯度的特征根，在拉格朗日座标系下讨论了流场中任意一点的流场特征。他们说流场核心的区域就是速度梯度的复特征值。
就我个人来讲， 对尾流区涡状结构的宏观分析，我会选用一些准则：

example: [so cool](http://cfd-china.com/topic/2133/paraview%E8%BE%93%E5%87%BA%E5%B0%BE%E6%B6%A1/2)

## [c++ 模板](http://cfd-china.com/topic/2127/%E5%85%B3%E4%BA%8Etmp-volscalarfield-%E7%94%A8%E6%B3%95%E7%9A%84%E7%96%91%E9%97%AE)
## [静电场](http://www.cfd-china.com/topic/2132/%E9%A2%97%E7%B2%92%E7%94%B5%E9%87%8F)
## [自适应网格](http://cfd-china.com/topic/612/%E4%BA%8C%E7%BB%B4%E8%87%AA%E9%80%82%E5%BA%94%E7%BD%91%E6%A0%BC/18)
## [进口边界条件](http://cfd-china.com/topic/2133/paraview%E8%BE%93%E5%87%BA%E5%B0%BE%E6%B6%A1/2)
## [什么是湍流](http://cfd-china.com/topic/2118/%E6%80%8E%E4%B9%88%E7%90%86%E8%A7%A3%E6%B9%8D%E6%B5%81%E5%BC%BA%E5%BA%A6-%E6%98%AF%E4%B8%80%E7%BB%84%E5%8F%98%E5%8C%96%E7%9A%84%E6%95%B0%E5%80%BC-%E8%BF%98%E6%98%AF%E4%B8%80%E4%B8%AA%E5%8D%95%E7%8B%AC%E7%9A%84%E6%95%B0%E5%80%BC)
## [丑丑的c++](http://cfd-china.com/post/11368)
```c++
if (phase1_.divU().valid() && phase2_.divU().valid())
    {
        tdgdt =
        (
            alpha2()
           *phase1_.divU()()()
          - alpha1()
           *phase2_.divU()()()
        );
    }
```
# 打包过的问题

# 用到的工具
## http://upli.st/l/list-of-all-ascii-emoticons
## https://www.codecogs.com/latex/eqneditor.php
