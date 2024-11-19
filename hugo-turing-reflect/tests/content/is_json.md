+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'is_json'
type = 'test'
+++

{{< turing/test/execute partial="turing/reflect/is_json" operator="false" arguments=`test` >}}

{{< turing/test/execute partial="turing/reflect/is_json" operator="false" arguments=`test` >}}

{{< turing/test/execute partial="turing/reflect/is_json" operator="true" arguments=`true` >}}

{{< turing/test/execute partial="turing/reflect/is_json" operator="true" arguments=`"false"` >}}

{{< turing/test/execute partial="turing/reflect/is_json" operator="true" arguments=`null` >}} 

