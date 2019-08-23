---
layout: post
title: Multi threading, con dao hai lưỡi của developer
subtitle: Multi threading hay đa luồng lợi - hại ra sao?
gh-repo: duyluongphung/blogs
gh-badge: [star,fork,follow]
tags: [multi-thread,multi,threading]
comments: true
---

Multi threading, hay đa luồng là một phương pháp lập trình hướng tới việc xử lý các tác vụ đồng thời song song dựa trên thiết kế phần cứng và cụ thể là CPU.

Trên thực tế, các bạn developer thường không tiếp cận nhiều đến các xử lý liên quan đến đa luồng, vì chúng phức tạp và có nhiều rủi ro.
Vậy thì đa luồng có gì hay ho và có những rủi ro gì mà chúng ta cần biết?
Let's go!!!

Lấy ví dụ bạn cần unzip thông tin idols từ 1000 file đã được zip. Mỗi file bạn mất 10 phút để giải nén chẳng hạn:
1000 * 10 = 10.000 phút (~7 ngày) để giải nén hết đống này.

=> cơ mà thế thì lâu vãi ra, bạn muốn trong 1 ngày thôi ~~

-> ez, chia ra 7 máy làm, mỗi máy 1000/7 files ==.

Nhưng mà đợi đã mình đang xài con i7-8750H (lấy đại thôi) cơ mà?? Cơ bản CPU của mình có 12 Thread (nhân thực).
=> Đồng nghĩa với việc là CPU này có thể xử lý song song 12 tác vụ, trường hợp này là file). Trên lí thuyết là thế, nhưng thực ra 12 threads đó còn phải care các task của OS nữa ==!

Đây chính là bài toán mà đa luồng sẽ được sử dụng để giải quyết.
>Thay vì sử dụng 1 thread để xử lý hết 1000 files thì chúng ta sử dụng 7 thread để xử lý 1000 files này. Vì lí thuyết là thời gian thực hiện
sẽ giảm xuống 7 lần, thực tế còn phụ thuộc vào memories nữa. Khi đó CPU sẽ thực hiện 7 tác vụ song song cho app của chúng ta.

*thế là ngon rồi, 1 ngày là xong mịa rồi =))*

Yup, thế thì có gì đâu mà risk?
Hơ hơ, nếu mỗi file bạn tạo ra 1 Thread để sử dụng thì => 1000 Threads, ù uôi, chúng sẽ được load lên RAM, ví dụ mỗi file là 1GB (idols chắc hơn nữa cơ) 
=> cần 1000GB RAM. Nà ní =_=

Rõ ràng điều này là bất khả thi, giả sử PC của bạn 16 GB RAM thì chắc chắn sẽ bị crash app vì xảy ra lỗi tràn bộ nhớ.
=> Khi sử dụng đa luồng chúng ta cần quản lý nó, sln là thay vì tạo ra 1000 threads thì chúng ta tạo ra 1 thằng quản lý (pooling - thread pooling), nó sẽ cho thực hiện mỗi lần 7 file và chỉ thực hiện file thứ 8 khi 1 trong các file được hoàn thành.

Đại khái nó nhưng 1 cái hồ bơi (~ connection pooling), nó tạo ra 7 cái đường bơi, nó sẽ cho một thằng vào bơi nếu có 1 đường bơi nào đó đang rảnh (đang không có thằng nào bơi, chắc là nó dơ =)) ).

Trên đây, là chia sẻ của mình mạn bàn về một vài khía cạnh, một vài chú ý khi sử dụng đa luồng (multi threading) trong lập trình!
Cảm ơn vì bạn đã đọc tới đây!!!

Refer with c# tuts: 
[https://www.tutorialspoint.com/csharp/csharp_multithreading.htm](https://www.tutorialspoint.com/csharp/csharp_multithreading.htm)
[https://docs.microsoft.com/en-us/dotnet/api/system.threading.threadpool?view=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.threading.threadpool?view=netframework-4.8).

