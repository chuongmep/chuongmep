---
title: "How to split string in Dynamo"
subTitle: "Làm thế nào  để ngắt một chuỗi trong Dynamo"
category: dynamo
layout: post
---

Chào mừng các bác đã ghé thăm blog của mình.😄

---

Hôm trước mình có viết một <a href="https://chuongmep.com/break-string-in-dynamo-list-with-characters" target="_blank">bài</a> ngăn cách giữa các phần tử danh sách với dấu phẩy, hôm nay mình sẽ tiếp tục làm công việc lấy phần tử từ bên trong một chuỗi **List** ra.Ví dụ , trong danh sách có các phần từ `Level 01 `thì mình chỉ muốn lấy `01` ra để  sử dụng tiếp mà thôi, vậy thì mình sẽ bắt tay vào làm thôi.

### Cách 1 : Sử dụng Python Scripts
#### Tạo một **CodeBlock** hoặc một **Python Script** và dán mã này vào

```
levels = IN[0]
levelnew = []
for level in levels :
	levelnew.append(level[-2::])
#Assign your output to the OUT variable.
OUT = levelnew
```
#### Sau đó ta sẽ nhìn thấy kết quả được lấy ra là hai kí tự phía sau chuỗi
![](https://github.com/chuong9x/DataBlog/blob/master/splitstring/SplitString01.png?raw=true)
#### Tuy nhiên vấn đề này chỉ giải quyết cho hai kí tự trở xuống thôi , nếu muốn 3 kí tự phía sau khoảng trống thì không lấy được.Như vậy một là mình phải cải tiến Scripts, hai là mình sẽ sử dụng cách hai bên dưới
Mình sẽ cải tiến Python Scripts với cú pháp Sau,3 hay bao nhiêu kí tự phía sau cũng sẽ lấy được hết. split()[1] chính là lấy từng phần tử trong đoạn list ấy, các bác cứ hiểu là ` chữ Hồ Văn Chương có 3 chữ thì thì chữ **Văn** sẽ là phần tử thứ 1`
```
#Author HoangThanhLong
OUT = [level.split()[1] for level in IN[0]]
```
### Cách 2 : Sử dụng Node `String.Split` kết hợp với `List.GetItemAtIndex`
![](https://github.com/chuong9x/DataBlog/blob/master/splitstring/SplitString02.png?raw=true)

Lưu ý : Ta để Lacing cho Node `List.GetItemAtIndex` để nhận hết list nhé.
### Kết quả : 
![](https://github.com/chuong9x/DataBlog/blob/master/splitstring/Screenshot_1.png?raw=true)

Như vậy mình đã có thể giải quyết được cho cả vấn đề có bao nhiêu kí tự phía sau khoảng cách đi chăng nữa.
#### Tổng kết
Vậy là mình đã kể cho các bác nghe xong hết câu chuyện nữa rồi đó, cứ thấy gì đó vui vui hay hay là mình lại viết lên cho a e tham khảo và góp ý, nếu có ý tưởng gì giúp cải thiện nhanh hơn thì các bác bình luận bên dưới nhé, mình sẽ bổ sung để bài viết được hoàn thiện hơn.Cám ơn các bác đã ghé thăm blog của mình !

### Tham khảo :
<a href="https://primer.dynamobim.org/04_The-Building-Blocks-of-Programs/4-4_strings.html" target="_blank">Dynamo Primer</a>

<a href="https://github.com/htlcnn" target="_blank">Hoàng Thanh Long</a>  
