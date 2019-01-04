# 准备中的问题
## [灰沉积](http://cfd-china.com/topic/2053/%E5%88%86%E4%BA%AB-%E4%B8%80%E4%B8%AA-latex-%E8%AE%BA%E6%96%87%E6%A8%A1%E6%9D%BF/10)

## [等值面](http://cfd-china.com/topic/664/cd%E8%AE%A1%E7%AE%97%E4%B8%8D%E5%87%86%E7%9A%84%E9%97%AE%E9%A2%98-les-re3900-%E4%B8%89%E7%BB%B4%E5%9C%86%E6%9F%B1%E7%BB%95%E6%B5%81-pisofoam/1040)

> 再次打扰了，我想做一下尾部三维的涡结构，可是为什么创建contour等值面时，contour by后面的选项只有压力P和nut，并没有后来vorticity命令计算出来的变量vorticity，vorticity只能以云图的形式出现，我需要怎样创建wake的结构呢？

因为你的数据中没有包含 vorticity。 通常来讲，你需要在后处理的过程中来处理。比如 (OF v4.1)：

```
pisoFoam -postProcess -func -vorticity
```

实际上，漩涡在数学上的定义是速度的旋度：curl of velocity

\begin{equations}
\omega = \daosanjiao X V
\end{equations}

不清楚云图是指？ 我觉得你指的是 contour?

就我个人来讲， 对尾流区涡状结构的宏观分析，我会选用一些准则：

example: [so cool](http://cfd-china.com/topic/2133/paraview%E8%BE%93%E5%87%BA%E5%B0%BE%E6%B6%A1/2)

## [c++ 模板](http://cfd-china.com/topic/2127/%E5%85%B3%E4%BA%8Etmp-volscalarfield-%E7%94%A8%E6%B3%95%E7%9A%84%E7%96%91%E9%97%AE)
## [静电场](http://www.cfd-china.com/topic/2132/%E9%A2%97%E7%B2%92%E7%94%B5%E9%87%8F)
## [zishiying](http://cfd-china.com/topic/612/%E4%BA%8C%E7%BB%B4%E8%87%AA%E9%80%82%E5%BA%94%E7%BD%91%E6%A0%BC/18)
## [question inlet](http://cfd-china.com/topic/2133/paraview%E8%BE%93%E5%87%BA%E5%B0%BE%E6%B6%A1/2)
# 打包过的问题
