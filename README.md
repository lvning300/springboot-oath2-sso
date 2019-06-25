## SSO授权登陆git-hub 
### 准备工作: 
`首先在git-hub注册Auth Apps，并分配clientId,clientSecret, 填写callback URL `
1. 第一步：用户请求index.html登陆页面 
1. 第二步：系统转发至授权页面https://github.com/login/oauth/authorize(需要clientId) 
1. 第三步：跳转至gitHub登陆页面(需要clientId) 
1. 第四步：授权同意返回授权码和callback URL 
1. 第五步：根据返回的code获取Token,https://github.com/login/oauth/access_token(需要clientId,clientSecret,code) 
1. 第六步：获取到Token请求API，https://api.github.com/user(需要access_token) 
1. 第七步：获取gitHub中返回第用户数据


### 获取Token

``
$ curl lvning:acmroot@localhost:8090/oauth/token -d grant_type=client_credentials
{"access_token":"370592fd-b9f8-452d-816a-4fd5c6b4b8a6","token_type":"bearer","expires_in":43199,"scope":"read write"}

密码模式：
$ curl acm:acmroot@localhost:8090/oauth/token -d grant_type=password -d username=user -d password=a80d4e2c-1654-4bca-a4d0-7a71b667dc08
{"access_token":"aa49e025-c4fe-4892-86af-15af2e6b72a2","token_type":"bearer","refresh_token":"97a9f978-7aad-4af7-9329-78ff2ce9962d","expires_in":43199,"scope":"read write"}
``