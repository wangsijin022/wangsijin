3.10.1 模块头部注释

/**
 * 用户权限管理模块 - 认证服务
 * 
 * 功能描述：处理用户登录、注册、权限验证等核心安全功能
 * 作者：XX技术团队
 * 版本：v1.2.0
 * 创建时间：2024-01-15
 * 修改历史：
 *   v1.1.0 2024-01-10 增加JWT令牌刷新机制
 *   v1.2.0 2024-01-15 优化权限缓存策略
 */


 3.10.2 关键函数注释

 /**
 * 用户登录认证
 * 
 * @param username 用户名，4-20字符
 * @param password 密码（前端已加密）
 * @param ipAddress 客户端IP地址，用于日志记录
 * @return AuthResponse 包含认证结果、令牌和用户信息
 * @throws AuthException 认证失败时抛出，包含错误代码和描述
 * 
 * 算法复杂度：O(1)平均，O(log n)最坏（数据库索引）
 * 线程安全：是，使用线程局部变量存储用户上下文
 */
public AuthResponse authenticate(String username, String password, String ipAddress) {
    // 实现代码...
}




3.10.3 复杂逻辑注释
// 权限验证逻辑：基于角色的访问控制(RBAC)
// 1. 首先检查用户是否被授予该权限
// 2. 然后检查用户所属角色是否拥有该权限
// 3. 最后检查权限是否在有效期内
if (!user.isActive()) {
    log.warn("用户 {} 账号已被禁用", user.getUsername());
    throw new PermissionDeniedException("账号已被禁用");
}
