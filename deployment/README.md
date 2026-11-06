# 1 模型部署管理 - 导出和导入部署示例
按照https://docs.gpustack.ai/2.3/zh/user-guide/model-deployment-management/教程

## 1. PD分离
### 1.1.1 后端参数
需填写
1. IP及端口相关
2. 模型名称及密钥相关
3. kv-transfer相关
以外的所有变量
且需要手动填写dp/tp相关数量

### 1.1.2 环境变量
若因engram-config参数需要设置shm-size，还需要设置GPUSTACK_MODEL_RUNTIME_SHM_SIZE_GIB