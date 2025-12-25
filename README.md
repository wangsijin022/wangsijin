3.6.1 密码加密算法
// 使用BCrypt算法，迭代次数12
String hashedPassword = BCrypt.hashpw(plainPassword, BCrypt.gensalt(12));

3.6.2 JWT生成算法
// JWT头部
Header = {"alg": "HS256", "typ": "JWT"}

// 载荷
Payload = {
  "sub": user_id,
  "username": username,
  "roles": ["admin", "operator"],
  "iat": issued_at_time,
  "exp": expiration_time
}

// 签名
Signature = HMACSHA256(
  base64UrlEncode(Header) + "." + 
  base64UrlEncode(Payload),
  secret_key
)


3.6.3 权限验证算法
函数 hasPermission(user, permission):
  如果 user 为空 返回 false
  对于 user.roles 中的每个角色:
    如果 role.permissions 包含 permission 返回 true
  返回 false

