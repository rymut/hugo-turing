+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'type_name'
type = 'test'
+++

# boolean

{{< turing/test/execute partial="turing/reflect/type_name" arguments=true expected="boolean" >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=false expected="boolean" >}} 

# float

{{< turing/test/execute partial="turing/reflect/type_name" arguments=10.1 expected="float" >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=.0 expected="float" >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=0.0 expected="float" >}} 

# int

{{< turing/test/execute partial="turing/reflect/type_name" arguments=-10 expected="int" >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=0 expected="int" >}}

{{< turing/test/execute partial="turing/reflect/type_name" arguments=10 expected="int" >}} 

# slice

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`[]` argumentsType="json" expected="slice" >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`[{}, {}]` argumentsType="json" expected="slice" >}} 

# map

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`{}` argumentsType="json" expected="map" >}} 

{{< turing/test/execute partial="turing/reflect/type_name" arguments=`{"test":10}` argumentsType="json" expected="map" >}} 


