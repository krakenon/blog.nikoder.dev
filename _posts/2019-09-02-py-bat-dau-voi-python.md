---
layout: post
title: Python series (part1), Bắt đầu với python
subtitle: Series giới thiệu về python và những suy nghĩ đầu tiên về python
gh-repo: duyluongphung/blogs
gh-badge: [star,fork,follow]
tags: [python,starter]
author: duy_luong
comments: false
---


# Part1: Bắt đầu với python
Ở part này mình sẽ không đi sâu vào các khái niệm liên quan đến python quá nhiều, kiểu như định nghĩa, các thông tin chi tiết của python. Mình sẽ giới thiệu cho các bạn những khái niệm cơ bản và cách bắt đầu làm việc với python, hello python!

    Python là gì?

![Philadelphia's Magic Gardens. This place was so cool!](https://i.imgur.com/VDKpivG.jpg "python")

> Ờ thì python là con trăn =))

Python là một ngôn ngữ lập trình bậc cao, được phát triển bởi [Guido van Rossum](https://en.wikipedia.org/wiki/Guido_van_Rossum). Mục tiêu ban đầu là để tạo ra một ngôn ngữ lập trình dễ hiểu và ngắn gọn.

Python được dùng chủ yếu trong lĩnh vực Compute Science, các nhóm nghiên cứu, gần đây thì là web.

## 1. Một số khái niệm cần nắm
### Trình biên dịch
Một ngôn ngữ lập trình thì cần có bộ biên dịch để dịch ra mã máy đúng không?

Python tương thích với nhiều trình biên dịch (compiler) khác nhau: C/C++, Java, Dotnet, Python (tự sướng luôn),...
Trong số này đáng kể là bộ complier với C/C++ (GCC).

> Trong series này mình cũng sẽ sử dụng compier Cython (C/C++), bởi vì hầu hết cái libs của python được build trên C/C++.

Refer: [https://cython.readthedocs.io/en/latest](https://cython.readthedocs.io/en/latest)

### Packages management
Trình quản lý packages (libs).
> Được sử dụng để cài các packages sử dụng, publish package lên indexing, v.v...

    pip là trình quản lý packages mặc định của python.

Python là open source, do đó các packages của python được đóng góp và index offical tại: [https://pypi.org](https://pypi.org).

### Working environments
Python cung cấp 2 environments:
- Global
- Virtual

Global là môi trường chung cho chả device (PC, hoặc server). Các projects trong cùng một device sẽ dùng chung các packages, do đó nếu một project nào đó sử dụng một packages khác version thì chúng ta phải quản lí rất phức tạp.

Virtual là môi trường cho phép bạn tạo ra một môi trường chỉ sử dụng cho một hoặc một vài project mong muốn. Nghĩa là các packages và settings trong môi trường virtual sẽ không ảnh hưởng tới các project không được assgin sẽ sử dụng nó.


> Thông thường chúng ta sử dụng cả 2 môi trường này. Chúng ta sẽ các packages common lên global, và các packages riêng biệt lên môt trường virtual.

##2. Hello world với python
> Đang hiểu là các bạn đã cài xong python lên máy rồi nha!
Nếu chưa cài python thì các bạn tham khảo: [https://www.python.org/downloads/](https://www.python.org/downloads/)

### Thao tác trực tiếp trên command line
Mở command line lên

     python --version

> Kết quả: *Python 3.6.7*

     python

> Kết quả: *switch qua màn hình thao tác với python*

    print("Hello world!")

> Kết quả: *Hello world!*

Như vậy là chúng ta đã tiếp cận cách thao tác với python qua command line.

### Tạo file code
Trong thực tế sẽ không ai sử dụng hoàn toàn command line cho 1 dự án viết bằng python cả. Command line chỉ sử dụng cho các TH build tools, quá trình development, hay các đoạn script runtime. Mà chúng ta sẽ đưa mã nguồn vào các file có đuôi ".py".

    touch main.py

> Tạo ra file *"main.py"*

Dán đoạn code bên dưới vào file "main.py"
    
    print("Hello world!")

Save lại và chúng ta đã có file mã nguồn.
Chạy thử file mã nguồn vừa tạo:

    python main.py
> Kết quả: *Hello world!*

Như vậy là chúng ta đã kết thúc part đầu tiên làm quen với Python, kết lại thì cần nắm được một số khái niệm cở bản của python. Chạy được một ví dụ hello world với python.


Cảm ơn các bạn đã đọc tới đây. Phần tiếp theo chúng ta sẽ học cách sử dụng một package với pip và publish 1 package tự viết lên pypi.
