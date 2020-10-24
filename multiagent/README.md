# AI-pacman

### Question 1 (4 points): Reflex Agent

- Hàm EvaluationFunction giúp ta tính toán điểm dựa trên khoảng cách tương đối giữa thức ăn và ma. Từ đó hàm getAction() dựa vào giá trị trẻ về để đánh giá đưa ra action phù hợp nhất.
- Giải thích code:
  . Gán giá trị minFoodDist =DƯƠNG VÔ CÙNG
  . Duyệt qua tất cả thức ăn hiện có để tìm ra khoảng các đến thức ăn nhỏ nhất dựa trên khoảng các Manhattan
  . Duyệt qua tất cả các con ma , nếu khoảng các giữa pacman và ma mà nhỏ hơn khoảng cách an toàn (< 2) thì trả về giá trị ÂM VÔ CÙNG
  . Hàm trả về theo công thức : điểm tích lũy + 1.0 / minFoodDist.
  => Giúp đánh giá : càng gần thức ăn điểm càng cao, nếu trả về ÂM VÔ CÙNG thì giúp pacman chọn action khác để tránh ma .

### Question 2 (5 points): Minimax

- The pseudocode for the depth limited minimax algorithm :

```
function minimax(node, depth, maximizingPlayer) is
    if depth = 0 or node is a terminal node then
        return the heuristic value of node
    if maximizingPlayer then
        value := −∞
        for each child of node do
            value := max(value, minimax(child, depth − 1, FALSE))
        return value
    else (* minimizing player *)
        value := +∞
        for each child of node do
            value := min(value, minimax(child, depth − 1, TRUE))
        return value
```

- Giải thích code :
  - agent_index = 0 : pacman , agent_index >= 1 : ghost
  - Input nhận vào (trạng thái game hiện tại, agent_index,độ sâu)
  - Output trả về :
    Nếu đã duyệt hết chiều sâ hay ở trạng thái game win hoặc lose thì return về giá trị static evaluation
    Nếu agent = 0 ( là pacman) thì chạy hàm maxval (đê quỵ)
    Nếu agent >= 1 ( là ghost) thì chay hàm minval (đệ quy)
  - Hàm maxval viết cho pacmac trả về action có giá trị hàm evaluation lớn nhất
  - Hàm min viết cho ghost trả về action có giá trị hàm evaluation nhỏ nhất
  - Tại hàm getAction ta sẽ chạy hàm maxval cho pacmac .

### Question 3 (5 points): Alpha-Beta Pruning

- Tương tự câu 2 nhưng sử dụng thuật toán cắt tỉa alpha, beta để làm.

### Question 4 (5 points): Expectimax

### Question 5 (6 points): Evaluation Function
