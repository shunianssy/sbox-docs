---
title: Sbox小盒子社区API
layout: about
---

# Sbox小盒子社区 API

权限范围（Scope）
只允许获取用户名，邮箱，id

## 1. 注册OAuth应用
/OAuth

## 2. 获取授权码

## 3.访问
https://sbox.yearnstudio.cn/oauth/authorize?
  client_id=BZ6h9QfiRJcCXV4Une23gA&
  redirect_uri=http://localhost:5000/callback&
  response_type=code&
  scope=basic

用户授权后，会重定向到您的回调地址：

https://shunx.top/callback?code=233

## main.py
import requests

resp = requests.post('https://sbox.yearnstudio.cn/oauth/token', json={
    "grant_type": "authorization_code",
    "code": "yH5UU2Y3A-MxLwhm0R-eIIacq5JzBwEOfQSp-J9ZuGE",
    "client_id": "NY5BG7ehRiuEJHm9AE-KpQ",
    "client_secret": "_ajEeT6hnW4e_ZhiRXDyEeLNQweo1CjW1ewmaNV-nNQ",
    "redirect_uri": "http://localhost:5000/"
})

print("Status Code:", resp.status_code)
print("Response Headers:", resp.headers)
print("Raw Response Text:")
print(resp.text)  # ← 查看实际返回内容


## get_user_info.py
import requests

ACCESS_TOKEN = "x4PiasD5JdYrcE4_GoIcxg3s4aJiOaPbQeSpQWzbHGDQcaLddTs5-cm5yBKNbZzG"

headers = {
    "Authorization": f"Bearer {ACCESS_TOKEN}"
}

resp = requests.get("https://sbox.yearnstudio.cn/oauth/user", headers=headers)

print("Status:", resp.status_code)
print("User Info:", resp.json())