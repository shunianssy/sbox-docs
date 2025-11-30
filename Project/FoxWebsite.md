---
title: FoxWebsite
layout: about
---

# 📘 foxwebsite Web 框架官方文档  
> 一个轻量级、异步、Flask 风格的 Python Web 框架 —— 由中学生独立开发并持续维护 ❤️  
> 你可以赞助我：[ifdian.net/a/shunian](https://www.ifdian.net/a/shunian)  
> 项目邮箱：sbox520@163.com  

---

## ✅ 1. 安装与快速启动  

### 安装依赖  

```bash
pip install uvicorn
```

（可选）如需使用 Jinja2 模板引擎（虽然是可选，但我还是推荐您使用）：

```bash
pip install jinja2
```

> foxwebsite 自带 `string.Template` 引擎，不装 Jinja2 也能用基础模板功能。

---

### 创建第一个应用  

新建 `app.py`：

```python
from foxwebsite import create_app

app = create_app(secret_key="your-secret-here")

@app.route("/")
def home(request):
    return "<h1>Hello, foxwebsite!</h1>"

@app.route("/user/{name}")
