### stratify = y
- Có tác dụng là đảm bảo tỷ lệ các lớp trong tập train và test giống nhau như trong toàn bộ dữ liệu ban đầu.

- Nếu không có stratify -> chia ngẫu nhiên 80 20 có thể xảy ra việc train set có 90% là lớp 0, 10% là lớp 1, test set có 100% là lớp 0 mất luôn lớp 1

- Khi dùng stratify

| Tập dữ liệu | Tỷ lệ lớp 0 | Tỷ lệ lớp 1 |
| ----------- | ----------- | ----------- |
| Toàn bộ     | 80%         | 20%         |
| Train       | 80%         | 20%         |
| Test        | 80%         | 20%         |

### shape

`x_train.shape` trả về một tuple `(số hàng, số cột)`

`x_train.shape[0]` trả về phần tử đầu tiên -> Số hàng

### Trong phương pháp naive bayes, khi nào sử dụng MultinomialNB, khi nào sử dụng GausianNB

| Loại Naive Bayes  | Khi nào dùng                                                                  | Dạng dữ liệu phù hợp                                                      | Ví dụ điển hình                                                           |
| ----------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **GaussianNB**    | Khi đặc trưng (feature) là **liên tục (continuous)**                          | Các giá trị thực (float) có phân phối gần **chuẩn (normal distribution)** | Chiều cao, cân nặng, điểm số, giá tiền, v.v.                              |
| **MultinomialNB** | Khi đặc trưng là **rời rạc (discrete)** và biểu diễn **tần suất/đếm (count)** | Số lần xuất hiện của từ, số lần click, số lượt xem, v.v.                  | Phân loại văn bản (Text Classification), Email Spam, Topic Classification |

- GaussianNB thích hợp cho:
    - Dự đoán điểm thi, giá nhà, thu nhập, v.v.
    - Bộ dữ liệu như Iris, Wine, Social Network Ads (tuổi, thu nhập, ...)

- MultinomialNB thích hợp cho:
    - Phân loại văn bản (Email spam, sentiment analysis)
    - Khi đặc trưng là số lượng hoặc tần suất (counts)