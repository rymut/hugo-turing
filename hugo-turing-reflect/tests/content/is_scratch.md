+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'is_scratch'
type = 'test'
+++

{{< turing/test/execute partial="turing/reflect/is_scratch" arguments=`&{map[testing]}` operator="false" >}} 

{{< turing/test/execute partial="turing/reflect/is_scratch" arguments=newScratch argumentsType="function" operator="false" >}}

{{< turing/test/execute partial="turing/reflect/is_scratch" arguments= operator="false" >}}

{{< turing/test/execute partial="turing/reflect/is_scratch" arguments=.Page operator="false" >}}
 
