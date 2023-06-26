![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/ad3fe08b-09ee-44b7-b3e3-d40bec426064)## Chủ đề: Phân khúc khách hàng công ty OLIST tại Brazil dựa trên mô hình RFM và thuật toán K-Means 
***Cơ sở lý thuyết*
### 1.	Mô hình RFM
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/4106a8c1-55c8-4d58-9fbe-fa516b443e20)
###### Phân tích RFM cho phép người làm marketing nhắm mục tiêu các nhóm khách hàng cụ thể với các thông tin liên lạc phù hợp hơn nhiều với hành vi cụ thể của họ – và do đó tạo ra tỷ lệ phản hồi cao hơn nhiều, cộng với sự trung thành và giá trị lâu dài của khách hàng tăng lên.
###### Phân tích RFM là một kĩ thuật phân khúc khách hàng dựa trên hành vi giao dịch của khách hàng trong quá khứ, RFM bao gồm 3 chỉ số chính:
-	Recency (R): Thời gian giao dịch cuối cùng.
-	Frequency (F): Tổng số lần giao dịch chi tiêu.
-	Monetary value (M): Tổng số tiền giao dịch chi tiêu.
###### Lợi ích của phân tích RFM:
-	Tăng tỷ lệ giữ chân khách hàng.
-	Tăng tốc độ phản hồi từ khách hàng.
-	Tăng tỷ lệ doanh thu từ khách hàng.
Nó dựa trên tiên đề tiếp thị rằng 80% doanh thu doanh nghiệp của bạn đến từ 20% khách hàng của bạn. RFM giúp xác định những khách hàng có nhiều khả năng phản hồi các chương trình khuyến mãi hơn bằng cách phân khúc họ thành các danh mục khác nhau.

#### Để tính điểm RFM cho mỗi khách hàng, chúng ta cần dữ liệu giao dịch bao gồm những thông tin sau:
- một id khách hàng duy nhất
-	số lượng giao dịch / đơn đặt hàng.
-	tổng doanh thu từ khách hàng.
-	số ngày kể từ lần ghé thăm gần nhất.
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/723cb1f1-950a-4bc1-9d85-aa4db88fa5d5)
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/54b94d6a-0bf7-4ef0-a38e-49589d9ab36b)
- Nhận xét: Có thể thấy công ty đang gặp vấn đề về khách hàng rất lớn, những điểm RFM đáng lo ngại như 344, 444 có số lượng lớn.

### 2. Phân cụm K-means
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/cc683550-7025-41d2-a332-50fb779e8906)
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/3b069e03-f5c9-45a1-9f75-4cc4898595f8)
→ Dựa vào phương pháp Elbow, ta chọn K = 5.

***Kết quả*
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/a41c9fa5-21b8-46ba-8a48-398292e70bd0)
Dựa vào sự phân bố của các cụm dựa vào các điểm RFM ta có thể thấy:
-	Với cụm cluster 0: Ta thấy cụm phân bố nhiều ở các điểm [211,212,311,411] là những khách hàng đã bỏ ra rất nhiều tiền để mua hàng, mua hàng thường xuyên,tuy nhiên đã lâu rồi không mua hàng → Khách hàng chi tiêu nhiều.
-	Với cụm cluster 1: Ta thấy cụm phân bố nhiều ở các điểm [223,233,333,422,433] là những khách hàng đã lâu rồi không mua, nhưng mua hàng không thường xuyên và chi ra số tiền khá thấp → Khách hàng có rủi ro rời công ty.
-	Với cụm cluster 2: Ta thấy cụm phân bố nhiều ở các điểm [244,344,444] là những khách hàng từ lâu rồi chưa mua hàng và mua với tần suất rất thấp,chi tiêu rất ít cho những lần mua → Khách hàng chắc chắn rời công ty.
-	Với cụm cluster 3: Ta thấy cụm phân bố nhiều ở các điểm [133,134,142,143,144] là những khách hàng mới mua gần đây, nhưng mua hàng không thường xuyên và số tiền chi ra vẫn ở mức thấp → Khách hàng mới.
-	Với cụm cluster 4: Ta thấy cụm phân bố nhiều ở các điểm [111,112,113,121,122,123,131,132] là những khách hàng mua hàng giao dịch gần đây, mua hàng thường xuyên, chi tiêu nhiều → Khách hàng trung thành.
***Phác họa chân dung mỗi nhóm khách hàng:*
 	![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/a6d71044-15e0-464e-a07c-e14d0ad46b9d)
 	![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/27c1baa3-544f-4a37-a129-995ad2b118ef)
***Đặc điểm khách hàng:*
-	Khách hàng chi tiêu nhiều nhất: Phân khúc khách hàng này chỉ dựa trên một trong ba chỉ số: những khách hàng có điểm số cao nhất về giá trị tiền tệ. 
-	Khách hàng trung thành: Đây là một phân khúc khách hàng khác chỉ xem xét một trong ba chỉ số: khách hàng có điểm cao nhất về tần suất. Mặc dù mua hàng thường xuyên nhưng họ không nhất thiết phải là người chi tiêu nhiều nhất.
-	Khách hàng có rủi ro rời công ty: Những khách hàng từng ở cấp cao nhất của công ty trước đây (chi tiêu nhiều và/hoặc trung thành) nhưng hiện có điểm thấp về mức độ gần đây và tần suất thấp.
-	Khách hàng mới: Đây là một phân khúc khách hàng khác chỉ xem xét một trong ba chỉ số: những mua hàng mua hàng gần đây nhưng không thường xuyên và giá trị chi tiêu còn thấp.
-	Khách hàng chắc chắn rời công ty: Những khách hàng này đã chi rất ít, mua rất ít lần và đặt hàng lần cuối cách đây khá lâu.
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/8c2a978a-9b54-40de-8a01-c9de8982bdbf)
![image](https://github.com/quynguyen6702/Olist_RFM/assets/125745108/00d8debe-e7cb-4cf7-afd2-16fc5ca1b112)

***Nhận xét:*
-	Khách hàng có rủi ro rời công ty đang chiếm tỷ lệ % khá lớn.
-	Khách hàng chi tiêu nhiều chiếm 23.9% có thể thấy đây là nguồn doanh thu lớn của công ty.

### Thực hiện các bước xây dựng bài toán bằng Code
| Trình tự thực hiện | Tên các bước                                                      | Link code                                                    |
| ----- | ------------------------------------------------------------                   | ------------------------------------------------------------ |
| 1     |Làm sạch dữ liệu | [👆](https://drive.google.com/file/d/1eLf7Lqr2u5jzKl6zV8QHhOgzDoOX0Qcr/view?usp=sharing) |
| 2     |Thực hiện phân khúc khách hàng | [👆](https://drive.google.com/file/d/1-kR5OhHNnbfWNFxuBYOiQnN3uTLQK8Py/view?usp=sharing) |
