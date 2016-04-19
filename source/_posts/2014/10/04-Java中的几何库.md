---
title: Java中的几何库
date: 2014-10-4
categories: Java
---
> 最近因为手头的项目需要处理几何问题，自己写又太麻烦了，所以去找基于Java的几何库。大多数都是基于C++的，有点难找

### java.awt.geom

- 简介：这不是几何库，这是个几何图形库

### Esri Geometry API

- 地址：[github](https://github.com/Esri/geometry-api-java)
- 简介：Esri是一家GIS服务提供商，该公司制作的api，主要解决地理信息的处理中，遇到的拓扑问题。
- 功能：数据传输，多边体的二元操作
- 结论：我的项目要处理的只跟简单几何图形有关，像是圆和三角形，但是这个api连直线都没有，只有多段线。所以果断弃用。

### JTS Topology Suite

- 地址：[sourceforge](http://sourceforge.net/projects/jts-topo-suite/)
- 简介：一个用于支持名为GEOS的开源GIS系统的几何库
- 功能：建立几何模型，多边体的操作
- 结论：该库为了支持GEOS，规模十分庞大，功能十分齐全。但是这也是个问题，我找了半天，都没找到怎么求两直线的交点，他实在是太大了。对于我这种小项目，还是不要用他的好。

### javaGeom

- 地址：[sourceforge](https://sourceforge.net/projects/geom-java/)
- 简介：一个简单的对2D/3D几何图形进行计算的几何库
- 功能：处理2D/3D图形间的简单操作
- 结论：很不错，对于我这种不用太高深功能的小项目，这些正好
