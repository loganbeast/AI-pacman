# AI-pacman

### Question 1 (6 points): Value Iteration

- Hàm EvaluationFunction giúp ta tính toán điểm dựa trên khoảng cách tương đối giữa thức ăn và ma. Từ đó hàm getAction() dựa vào giá trị trẻ về để đánh giá đưa ra action phù hợp nhất.
- Giải thích code:
  . Gán giá trị minFoodDist =DƯƠNG VÔ CÙNG
  . Duyệt qua tất cả thức ăn hiện có để tìm ra khoảng các đến thức ăn nhỏ nhất dựa trên khoảng các Manhattan
  . Duyệt qua tất cả các con ma , nếu khoảng các giữa pacman và ma mà nhỏ hơn khoảng cách an toàn (< 2) thì trả về giá trị ÂM VÔ CÙNG
  . Hàm trả về theo công thức : điểm tích lũy + 1.0 / minFoodDist.
  => Giúp đánh giá : càng gần thức ăn điểm càng cao, nếu trả về ÂM VÔ CÙNG thì giúp pacman chọn action khác để tránh ma .

### Question 2 (1 point): Bridge Crossing Analysis

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

### Question 3 (5 points): Policies

- Tương tự câu 2 nhưng sử dụng thuật toán các tham số alpha, beta để tăng hiệu suất cho Pacman => giảm số lần phải gọi đệ quy ở các nhánh k cần thiết đi qua.

### Question 4 (5 points): Q-Learning

- Trong Expectimax Agent sẽ giả định là các tác tử Ma không phải lúc nào cũng chọn lựa chọn tốt nhất để gây bất lợi cho Pacman. Cách cài đặt sẽ hơi khác so với getAction() của Minimax 1 chút tuy nhiên hàm maxvalue() vẫn giữ nguyên. Hàm minvalue() sẽ đổi tên thành expvalue(). Giá trị trả về của những lần đệ quy hàm expectimax() là giá trị trung bình (tổng giá trị trả về của các hàm / số action của Gh).

### Question 5 (3 points): Epsilon Greedy

- Hàm betterEvaluationFunction()): Kế thừa các thiết kế của hàm evaluationFunction() ở câu 1. Bên cạnh đó sẽ có thêm yếu tố
  capsLeft = len(currentGameState.getCapsules()) là "thức ăn đặc biệt" mà Pacman ăn vào thì sẽ làm cho Ghost sợ và có thể bị tiêu diệt.

### Question 6 (1 point): Bridge Crossing Revisited
### Question 7 (1 point): Q-Learning and Pacman
### Question 8 (3 points): Approximate Q-Learning