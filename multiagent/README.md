# AI-pacman

### Question 1 (4 points): Reflex Agent

- Hàm EvaluationFunction giúp ta tính toán điểm dựa trên khoảng cách tương đối giữa thức ăn và ma. Từ đó hàm getAction() dựa vào giá trị trẻ về để đánh giá đưa ra action phù hợp nhất.
- Giải thích code:
  . Gán giá trị minFoodDist =DƯƠNG VÔ CÙNG
  . Duyệt qua tất cả thức ăn hiện có để tìm ra khoảng các đến thức ăn nhỏ nhất dựa trên khoảng các Manhattan
  . Duyệt qua tất cả các con ma , nếu khoảng các giữa pacman và ma mà nhỏ hơn khoảng cách an toàn (< 2) thì trả về giá trị ÂM VÔ CÙNG
  . Hàm trả về theo công thức : điểm tích lũy + 1.0 / minFoodDist.
  => Giúp đánh giá : càng gần thức ăn điểm càng cao, nếu trả về ÂM VÔ CÙNG thì giúp pacman chọn action khác để tránh ma .
