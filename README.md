# EdgeOne Cloud Functions

这是一个运行在EdgeOne平台上的云函数，提供URL重定向、键值存储、HTTP代理和IP查询等功能。

## 功能概述

### 1. URL重定向, 短链
根据预设的路径映射规则，将请求重定向到指定URL。

### 2. 键值存储 (KV Storage)
提供简单的键值对存储功能，支持设置和获取键值对。

### 3. HTTP代理
允许代理请求到目标URL，并可自定义请求头。

### 4. IP查询
获取客户端的真实IP地址。

## API接口说明

### 重定向功能
访问已配置的路径会自动重定向到目标URL。

### 设置键值对
- **URL**: `/setKV?key={key}&value={value}`
- **方法**: GET
- **参数**:
  - `key` (必需): 键名
  - `value` (必需): 键值

### 设置链接重定向
- **URL**: `/setLink?key={key}&value={value}`
- **方法**: GET
- **参数**:
  - `key` (必需): 路径名
  - `value` (必需): 重定向目标URL

### 获取所有链接映射
- **URL**: `/getLink`
- **方法**: GET

### 获取键值
- **URL**: `/getKV?key={key}`
- **方法**: GET
- **参数**:
  - `key` (必需): 要获取的键名

### IP查询
- **URL**: `/ip`
- **方法**: GET
- **返回**: 客户端IP地址

### HTTP代理
- **URL**: `/?url={targetUrl}`
- **方法**: GET/POST/PUT/DELETE等
- **参数**:
  - `url` (必需): 目标URL
  - `host` (可选): 自定义Host头
  - `referer` (可选): 自定义Referer头

## 使用示例

### 设置键值对