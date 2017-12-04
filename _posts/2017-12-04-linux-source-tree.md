---
title:  "Linux Source Tree Stuff"
categories: [ "linux dev" ]
---

## Contents
{: .no_toc}
* TOC 
{:toc}
<hr/>

	
## Build tree
`cd ~/linux`

`make help`: Get details of the Makefile targets.

`make olddefconfig`: Use an old config, and use defaults for new options.

`make -j4 > ~/build.log 2>&1 &`: Build in background (4 parallel jobs).

## Run checkpatch.pl on a sub-tree
`git ls-files drivers/staging/*.[ch] | xargs ./scripts/checkpatch.pl -f -q`

Only check *.c and *.h files, only output messages about issues (-q).




<hr/>

## Specifics & Resources
* Working with linux-next ([kernel.org](https://www.kernel.org/doc/man-pages/linux-next.html))


