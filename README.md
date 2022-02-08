# CS114.M11.KHCL
<html>
<h1> Giới thiệu nhóm </h1>
<p> NGUYỄN THỊ LY - MSSV : 19521818 </p>
<p> NGÔ ANH VŨ -  MSSV : </p>
<h1> Đồ án cuối kì </h1>
<p>Tên đồ án : Phát hiện người đeo khẩu trang </p>
  Mô tả bộ dataset
  Chúng em tiến hành thu thập dữ liệu từ các camera an ninh của các cửa hàng , công ty.Ngoài ra  còn có một phần dữ liệu được lấy từ dữ liệu của cuộc thi
Data-Centric AI Competition
  
![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/1.png)
  

  Do lí do bảo mật nên nhóm gặp khó khăn trong việc xin trích xuất camera của các cửa hàng và công ty tuy nhiên nhóm đã cố gắng van nài ,xin xỏ .Thành quả đó là thu thập được 8 video trích xuất từ camera trong .Trong đó có 5 video được trích từ cổng ra vào công ty.Ở góc camera này thì thu được tương đối nhiều số lượng người ra vào song vấn đề gặp phải ở đây là góc camera khá rộng khuôn mặt người ở một số khung hình nhỏ )
  
  ![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/2.png)
  

  Ngoài ra thì chất lượng hình ảnh từ camera cũng ko tốt,độ phân giải không cao.Các vấn đề này sẽ gây khó khăn cho việc huấn luyện mô hình và chạy mô hình sau này.Có 3 video được lấy từ trích xuất camera cửa hàng tạp hóa có góc ảnh vừa đủ độ phân giải của ảnh tốt.
  
  ![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/3.png)
  

Sau khi tiến hành thu thập dữ liệu thì chúng em sẽ trích xuất các frame ảnh từ video .Các frame được trích xuất với tiêu chí chọn các frame có khuôn mặt người có thể nhìn rõ được .Đối với các frame ảnh ko có người thì chúng ta bỏ qua không lấy.Bởi video được thu thập ở quê,dân cư thưa thớt,mật độ dân số thấp cho nên số lượng người xuất hiện trong video không nhiều nên mặc dù số video thu được nhiều nhưng số lượng frame ảnh được lấy chỉ tầm 1034 bức ảnh .Với lượng số ảnh trên thì nhóm chúng em tiến hành lấy thêm dữ liệu của cuộc thi  Data-Centric AI Competition là 1064 bức ảnh nữa.Vậy tổng cộng bộ dữ liệu của tụi em có 2098 bức ảnh với 3252 khuôn mặt được gán nhãn No Mask hoặc Mask. Công cụ được chúng em sử dụng để tiến hành gãn nhãn đó là makesense.ai.Thì thông số cụ thể của từng nhãn đó là 1827 khuôn mặt được dán nhãn label ‘ No Mask’ và 1425 khuôn mặt  được dán nhãn ‘Mask’.

  ![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/4.png)

Các thông số về bounding box khuôn mặt được tổ chức và lưu ở 2 định dạng đó là file.csv và file .txt.
 
![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/5.png)
  
Mỗi bức ảnh tương ứng với mỗi file txt,mỗi khuôn mặt sẽ tương ứng với mỗi dòng trong file txt.Có 5 gia trị trên mỗi dòng thì gia trị đầu tiên là thông số về nhãn,2 giá trị tiếp theo là tọa độ của điểm trái trên của boundingbox khuôn mặt,2 điểm còn lại là giá trị high và weight.  

  ![kjksjd](https://github.com/nguyenthily1605/CS114.L21.KHCL/blob/main/image/6.png)
  
Tất cả các khuôn mặt được bounding box của 2098 bức ảnh được gán nhãn và lưu tại 1 file csv. Đối với file csv thì được tổ chức với 6 columns bao gồm columns nhãn,tọa độ x và y của điểm trái trên,weight và high ngoại ra còn chứa tên của ảnh chứa khuôn mặt được bounding box

  
  
