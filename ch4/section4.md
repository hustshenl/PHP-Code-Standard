# SESSION

1. 大部分系统会使用Session记录用户身份授权状态，Session信息依赖于用户Cookie，Cookie信息泄露同时会造成Session信息泄露；
2. 预防Session泄露建议
    + 会话完成后，及时销毁会话数据
    + 不要将Session文件保存在默认路径，保存到Web目录或者数据库
    + 读取Session时验证IP
    + 敏感操作二次验证密码