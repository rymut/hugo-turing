+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'is_float'
type = 'test'
+++
 
# is_float test

{{< turing/test/execute partial="turing/reflect/is_float" arguments=+10.0 operator="true" >}} 
{{< turing/test/execute partial="turing/reflect/is_float" arguments=-10.0 operator="true" >}}
{{< turing/test/execute partial="turing/reflect/is_float" arguments=22.2 operator="true" >}} 
{{< turing/test/execute partial="turing/reflect/is_float" arguments=22 operator="false" >}} 
