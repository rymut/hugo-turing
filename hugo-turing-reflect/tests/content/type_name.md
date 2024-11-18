+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'type_name'
type = 'test'
+++

# boolean

{{< turing/test/execute partial="turing/reflect/type_name" arguments=true operator="eq" expected=`"boolean"` >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=false operator="eq" expected=`"boolean"` >}} 

# float

{{< turing/test/execute partial="turing/reflect/type_name" arguments=10.1 operator="eq" expected=`"float"` >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=.0 operator="eq" expected=`"float"` >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=0.0 operator="eq" expected=`"float"` >}} 

# int

{{< turing/test/execute partial="turing/reflect/type_name" arguments=-10 operator="eq" expected=`"int"` >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=0 operator="eq" expected=`"int"` >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=10 operator="eq" expected=`"int"` >}} 

# slice

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`[]` operator="eq" expected=`"slice"` >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`[{}, {}]` operator="eq" expected=`"slice"` >}} 

# map

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`{}` operator="eq" expected=`"map"` >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`{"test":10}` operator="eq" expected=`"map"` >}} 


