# AI-pacman

### Question 1 (4 points): Perceptron

- Perceptron Tận dụng hàm classify cho trước để phân loại nhãn. Sau đó cập nhật vector trọng số.

### Question 2 (1 point): Perceptron Analysis

- Perceptron Analysis Dùng hàm sortedKeys() của util.Counter() để sắp xếp trọng số của các features. Sau đó in ra kết quả Đáp án của câu hỏi là 'a'.

### Question 3 (6 points): MIRA

- MIRA Tương tự như perceptron tuy nhiên thêm hệ số tau nhân vào trước vector features trong mỗi lần cập nhật vector trọng số. Hệ số tau được tính theo công thức đã ghi trong slide bài giảng.

### Question 4 (6 points): Digit Feature Design

- Enhanced Digit Features Design Feature được thêm vào là số khoảng trắng trên dữ liệu đầu vào. Viết thêm hàm pixArray() dùng DFS để đánh dấu các khoảng trắng. Số khoảng trắng với các kí tự số sẽ là 1, 2 và 3 tương ứng với 3 features được thêm vào và được khởi tạo với giá trị 0.

### Question 5 (4 points): Behavioral Cloning

- Pacman Behavioral Cloning Tương tự như Câu 1. Tuy nhiên vì sử dụng chung vector trọng số cho tất cả các nhãn( các hành động tương ứng với 1 trạng thái của pacman) nên khi cập nhật sẽ đồng thời cộng và trừ vào vector trọng số đó.

### Question 6 (4 points): Pacman Feature Design

- Enhanced Pacman Features Design
