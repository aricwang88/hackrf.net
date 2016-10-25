---
ID: 375
post_title: HackRF / GNURadio 发射 64QAM 信号
author: scateu
post_date: 2014-03-19 15:55:45
post_excerpt: ""
layout: post
permalink: >
  http://www.hackrf.net/2014/03/hackrf-64qam-transmit/
published: true
views:
  - "4515"
duoshuo_thread_id:
  - "1312073613704167475"
---
<a href="http://www.hackrf.net/wp-content/uploads/2014/03/64QAM.png"><img class="alignnone size-full wp-image-376" alt="64QAM" src="http://www.hackrf.net/wp-content/uploads/2014/03/64QAM.png" width="829" height="431" /></a>

&nbsp;

通过搭建以上的框图，我们可以进行64QAM的发射。

需要注意的几点:
<ol>
	<li>Multiply Const用于对输出IQ的幅度进行限制</li>
	<li>QAM Mod输入的数据类型为Byte，输出Complex</li>
	<li>送入QAM Mod的值
<ol>
	<li>可以选为Vector Source，这里我们使用Python的range函数生成了从[0,1,2,3, ... , 63]的序列</li>
	<li>也可以选择为Random Source，这样生成的数值就为随机值了</li>
</ol>
</li>
</ol>
&nbsp;

使用上述信号流程图，发出的信号送入Agilent E8491B和89600软件中，测得EVM指标为1.5%左右。

&nbsp;

<a href="http://www.hackrf.net/wp-content/uploads/2014/03/89600_64QAM.png"><img class="alignnone size-full wp-image-259" alt="89600_64QAM" src="http://www.hackrf.net/wp-content/uploads/2014/03/89600_64QAM.png" /></a>