**SSO授权登陆git-hub**
****准备工作:****
首先在git-hub注册Auth Apps，并分配clientId,clientSecret, 填写callback URL
第一步：用户请求index.html登陆页面
第二步：系统转发至授权页面https://github.com/login/oauth/authorize(需要clientId)
第三步：跳转至gitHub登陆页面(需要clientId)
第四步：授权同意返回授权码和callback URL
第五步：根据返回的code获取Token,https://github.com/login/oauth/access_token(需要clientId,clientSecret,code)
第六步：获取到Token请求API，https://api.github.com/user(需要access_token)
第七步：获取gitHub中返回第用户数据