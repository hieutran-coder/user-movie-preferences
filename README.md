# User’s Preference in Movies
## Giới thiệu    
Hệ thống gợi ý (Recommender Systems - RS) là một dạng của hệ thống lọc thông tin (information filtering), nó được sử dụng để dự đoán sở thích (preferences) hay xếp hạng (rating) mà người dùng có thể dành cho một mụcthông tin (item) nào đó mà họ chưa xem xét tới trong quá khứ (item có thể là bài hát, bộ phim, đoạn video clip, sách, bài báo,..).
## Các kĩ thuật chính trong RS
Hiện tại, trong RS có rất nhiều giải thuật được đề xuất, trong số đó gồm giải thuật lọc theo nội dung (content-based filtering) giải thuật lọc cộng tác (collaborative filtering). Nhóm đề xuất sử dụng content-based filtering.

##	Content-based filtering
The content-based filtering method là phương pháp dựa vào dữ liệu về các bộ phim mà người xem đã thích trong quá khứ để tính độ tương tự với bộ phim trong hệ thống. Từ đó, gợi ý những bộ phim tương tự với phim mà người xem đã thích, đã xem, đã mua trong quá khứ.
     ![image](https://github.com/user-attachments/assets/59f798ef-caf0-484e-ad11-b3615f2467db)

## Mô tả và tiền xử lý dữ liệu
Dữ liệu gồm 2 file: movies.csv và ratings.csv, được lấy từ trang MovieLens.

 File movies.csv có 10.000 bản ghi, gồm các trường: ID phim, tên phim (title), năm sản xuất, thể loại (genres). Chúng ta có thể nhìn thấy một số bộ phim quen thuộc như Toy Story, 12 Monkeys, Apollo 13, …
  
![image](https://github.com/user-attachments/assets/357edf5c-550a-43e4-b456-c53077b3a963)

  
File ratings.csv gồm 100.000 bản ghi, gồm các trường (theo thứ tự từ trái sáng phải) là: ID của người đánh giá, ID của phim được đánh giá, số điểm (là 1 số trong khoảng 0,5 đến 5,0 và được làm tròn).

![image](https://github.com/user-attachments/assets/6335050d-624e-4861-8ff5-23a6a77b2ad5)


## Phương pháp đánh giá Hold-out
Nhóm sử dụng hàm Root-Mean-Square Deviation (RMSE) làm tiêu chuẩn

![image](https://github.com/user-attachments/assets/f7642802-2da3-4cdd-b8bb-78e29441490e)

## Tóm tắt các mô hình sử dụng
### 1. KNN
Thuật toán: KNN sử dụng thước đo khoảng cách nhỏ nhất để tìm những người hàng xóm gần nhất của nó. Một phương pháp phổ biến là phương pháp khoảng cách Euclide (Căn bậc hai của tổng bình phương khoảng cách giữa hai điểm). 

![image](https://github.com/user-attachments/assets/68689074-225f-41bc-a50b-1cc676a44dc8)

### 2. Matrix Factorization
Ý tưởng của phương pháp này dựa vào việc mỗi bộ phim có thể mang một số thuộc tính ẩn. Mỗi thuộc tính ẩn này sẽ được gắn với một giá trị để đo các độ liên quan giữa bộ phim và thuộc tính đó. Tương tự ta cũng có mức độ yêu thích của một người dùng với từng thuộc tính ẩn. Kết hợp 2 yếu tố này ta thấy mức độ yêu thích của một người dùng với từng thuộc tính càng giống độ liên quan của một bộ phim tới các thuộc tính đó thì khả năng người dùng thích bộ phim là càng cao. 
### 3. Neural Network
Mô hình này sử dụng cùng chung một ý tưởng về các thuộc tính phụ giống như Matrix Factorization nhưng thay vì sử dụng Gradient Decent thì ta sử dụng một mạng neuron để huấn luyện X và W.
### 4. Random Forest
Random Forest là một thuật toán học có giám sát, sử dụng các cây (tree) để làm nền tảng. Đây là một tập hợp của các Decision Tree, mà mỗi cây được chọn theo một thuật toán dựa vào ngẫu nhiên.
![image](https://github.com/user-attachments/assets/c1034afb-c51a-4e8d-a8f2-cf710d435d51)


-----
Ps: Tham khảo chi tiết các cách xây dựng mô hình trong báo cáo 
