---
title:  "Linux Source Tree Stuff"
categories: [ "linux dev" ]
---

## Contents
{: .no_toc}
* TOC 
{:toc}
<hr/>


## Get linux-next
git clone https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git linux-next
Note: this can't be updated using a simple `git pull`. See 'Working with linux-next' (below).
	
## Build tree
`cd ~/linux`

`make help`: Get details of the Makefile targets.

`make olddefconfig`: Use an old config, and use defaults for new options.

`make -j4 > ~/build.log 2>&1 &`: Build in background (4 parallel jobs).

<hr/>

## Specifics & Resources
* Working with linux-next ([kernel.org](https://www.kernel.org/doc/man-pages/linux-next.html))


