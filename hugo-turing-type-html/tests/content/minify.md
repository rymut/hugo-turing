+++
date = '2024-11-09T10:30:19+01:00'
draft = false
title = 'minify'
type = 'test'
+++

TESTING

{{< turing/test/execute partial="turing/minify/html" expected=`<br/>` operator="eq" arguments=`\r <br/>\n\t` argmentsType="string" >}}


{{< turing/test/execute partial="turing/minify/html" expected=`<pre>\n\ntest ala ma kota\t</pre>` operator="eq" arguments=`  <pre>\n\ntest ala ma kota\t</pre>   ` argmentsType="string" >}}
