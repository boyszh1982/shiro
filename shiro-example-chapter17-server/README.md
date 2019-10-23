https://wiki.jikexueyuan.com/project/shiro/oauth-two.html

首先通过如 http://localhost:8080/chapter17-server/authorize?client_id=c1ebe466-1cdc-4bd3-ab69-77c3561b9dee&response_type=code&redirect_uri=http://localhost:9080/chapter17-client/oauth2-login 访问授权页面；
该控制器首先检查 clientId 是否正确；如果错误将返回相应的错误信息；
然后判断用户是否登录了，如果没有登录首先到登录页面登录；
登录成功后生成相应的 auth code 即授权码，然后重定向到客户端地址，如 http://localhost:9080/chapter17-client/oauth2-login?code=52b1832f5dff68122f4f00ae995da0ed；在重定向到的地址中会带上 code 参数（授权码），接着客户端可以根据授权码去换取 access token。