---
layout: post
title: Xử lý đồng bộ và bất đồng bộ trong javascript
subtitle: synchronus/asynchronus và multiple thread
gh-repo: duyluongphung/blogs
gh-badge: [star, fork, follow]
tags: [javascript,async,sync]
author: duy_luong
comments: false
---

Với các bạn lập trình web thì hẳn khái niệm bất đồng bộ (asynchronus) và đồng bộ (synchronus) không còn quá xa lạ. Tuy nhiên có rất nhiều sự nhầm lẫn giữa synchronus/asynchronus với multiple threading. Chúng ta cùng phân tích nhe!

# Bài này có gì
```
  1. Nắm được khái niệm về synchronus/asynchronus
  2. Phân biệt được sự khác nhau giữa synchronus/asynchronus và multiple thread
  3. Synchronus/asynchronus trong javascript được sử dụng ra sao?
  4. Một số lỗi thường gặp khi sử dụng synchronus/asynchronus
```

## Synchronus/asynchronus là gì?

Để hiểu được một cách rõ ràng 2 khái niệm này chúng ta đi từ một ví dụ thực tế, như sau: tôi load 1 trang tin tức chẳng hạn, trong đó có 1 tấm hình và content của bài viết; và cần download image từ server, tuy nhiên file của tôi khá nặng khoảng đâu đó 3Mb cộng với việc mạng nhà tôi hơi chậm nên tôi phải mất 5 phút mới lấy được ảnh xong.
Theo flow bình thường chúng ta sẽ có 3 dòng lệnh chính như sau:
```
  1. Lấy file từ server (5 phút)
  2. Show ảnh này lên màn hình
  3. Xử lí tiếp theo của màn hình (có thể là scroll content bên dưới, bla.bla...)
```
Nếu chúng ta thực hiện tuần tự lệnh 1 -> lệnh 2 -> lệnh 3 => tối thiểu 5p chúng ta mới có thể scroll để đọc content của bài blog.
*Cơ chế này được gọi là blocking*
> Đại khái blocking là cơ chế đóng băng các xử lý cho đến khi được unblock. Trong trường hợp này trang tin tức sẽ bị block cho đến khi load xong được hình.


