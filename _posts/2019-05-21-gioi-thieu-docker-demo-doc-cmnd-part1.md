---
layout: post
title: Giới thiệu docker và demo ứng dụng đọc số chứng minh nhân dân qua hình ảnh với docker (Part1)
subtitle: Docker là gì?
gh-repo: duyluongphung/blogs
gh-badge: [star, fork, follow]
tags: [docker]
author: duy_luong
comments: false
---

Docker là một platform mã nguồn mở, với chức năng chính là xây dựng một môi trường ảo để khởi chạy các ứng dụng một cách độc lập với host platform. 

Một ví dụ đơn giản: bạn xây dựng một web app với python + flask, bạn muốn run app này trên ubuntu. Tuy nhiên dev team của bạn có 3 người và đang sử dụng nhiều môi trường khác nhau: 1 người sử dụng ubuntu, 1 người sử dụng windows, 1 người sử dụng MacOS.
>absl-py==0.7.0  
astor==0.7.1  
astroid==2.2.5  
Cython==0.29.7  
decorator==4.3.2  
dlib==19.17.0  
dnspython==1.16.0  
entrypoints==0.3  
eventlet==0.24.1  
ffmpy==0.2.2  
Flask==1.0.2  
Flask-Cors==3.0.7  
Flask-SocketIO==3.3.2  
...

>*Act cool đứng hình mất 5s!!!*

Khi đó với vai trò là người support CI/CD cho dự án rõ ràng lúc này bạn phải setup và fixbug cho cả 3 môi trường để quá trình develop và test không bị stuck: Ubuntu, Windows, MacOS => việc này quá tốn time và có thể sẽ gây ra sự confuse giữa các OS khác nhau.

=> Vấn đề này sẽ được giải quyết với Docker. Với docker bạn chỉ cần cài Docker trên tất cả các máy này và define các packages cần thiết cho môi trường đích (production release) là ubuntu mà thôi. Docker sẽ làm phần còn lại, dev team của bạn khi đó ko cần quan tâm đến develop environment nữa.

