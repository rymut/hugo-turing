+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'is_json'
type = 'test'
+++

{{< turing/test/execute partial="turing/reflect/is_json" expected=false operator="eq" arguments=`test` argmentsType="string" >}}
{{< turing/test/execute partial="turing/reflect/is_json" expected=false operator="eq" arguments=`test` argmentsType="string" >}}
{{< turing/test/execute partial="turing/reflect/is_json" expected=true operator="eq" arguments=`true` >}}
{{< turing/test/execute partial="turing/reflect/is_json" expected=true operator="eq" arguments=`"false"` argumentsType="string" >}}

{{< turing/test/execute partial="turing/reflect/is_json" expected=true operator="eq" arguments=`null` argumentsType="string" >}} 

