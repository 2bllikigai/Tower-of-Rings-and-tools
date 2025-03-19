Tower of Rings and tools
Overview
Tower of Rings and tools là một trò chơi giải đố được phát triển bằng Python và sử dụng thư viện Pygame để tạo giao diện đồ họa. Trong trò chơi này, người chơi cần sắp xếp các vòng màu trên các cột sao cho mỗi cột chỉ chứa các vòng cùng màu. Trò chơi hỗ trợ hai chế độ chơi: chơi tay (kéo và thả) và tự động giải bằng thuật toán A*.

Features
Chế độ chơi tay: Người chơi có thể kéo và thả các vòng màu từ cột này sang cột khác.
Chế độ tự động (Solve): Sử dụng thuật toán A* để tìm đường đi tối ưu và hiển thị từng bước di chuyển.
Giới hạn bước: Người chơi có tối đa 50 bước để hoàn thành trò chơi.
Hiển thị số bước: Số bước đã thực hiện và giới hạn bước được hiển thị trên giao diện đồ họa (ví dụ: "Moves: 5/50").
Lịch sử di chuyển: Các bước di chuyển được in ra terminal với định dạng "Step X: Pole A -> Pole B".
Thông báo kết thúc: Hiển thị "You Win!" khi thắng hoặc "Game Over! Move Limit Reached!" khi vượt quá số bước tối đa.
Requirements
Python: Phiên bản 3.6 trở lên.
Pygame: Thư viện Pygame để tạo giao diện đồ họa.
Installation
Cài đặt Python:
Tải và cài đặt Python từ trang chính thức. Đảm bảo thêm Python vào PATH trong quá trình cài đặt.
Cài đặt Pygame:
Mở terminal (Command Prompt, PowerShell, hoặc terminal khác) và chạy lệnh sau:
pip install pygame
Tải mã nguồn:
Sao chép mã nguồn của trò chơi vào một tệp có tên ring_sorting_game.py. Bạn có thể lưu tệp này vào bất kỳ thư mục nào, ví dụ: C:/ring_sorting_game.py.
How to Play
Running the Game
Mở terminal và di chuyển đến thư mục chứa tệp ring_sorting_game.py. Ví dụ:
cd C:\
Chạy trò chơi bằng lệnh:
python ring_sorting_game.py
Game Rules
Trò chơi có 6 cột (A, B, C, D, E, F):
4 cột ban đầu (A, B, C, D) chứa 4 vòng màu mỗi cột, với các màu hỗn hợp (red, pink, purple, brown).
2 cột (E, F) trống, dùng làm cột trung gian để di chuyển.
Mục tiêu: Sắp xếp sao cho 4 cột chứa toàn bộ vòng của cùng một màu (mỗi cột 4 vòng), và 2 cột trung gian trống.
Quy tắc di chuyển:
Chỉ được di chuyển các vòng cùng màu ở trên cùng của cột.
Các vòng cùng màu phải di chuyển cùng lúc.
Có thể di chuyển sang cột trống hoặc cột có vòng cùng màu ở trên cùng.
Mỗi cột chứa tối đa 4 vòng.
Giới hạn bước: Người chơi có tối đa 50 bước để hoàn thành trò chơi.
Controls
Chơi tay:
Nhấp chuột trái vào cột để chọn các vòng màu trên cùng.
Kéo và thả vào cột đích để di chuyển.
Nút bấm:
Reset: Đặt lại trò chơi về trạng thái ban đầu.
Solve: Sử dụng thuật toán A* để tự động giải trò chơi và hiển thị từng bước.
Quit: Thoát khỏi trò chơi.
Display
Trên giao diện đồ họa:
Số bước đã thực hiện và giới hạn bước được hiển thị ở góc trên bên phải (ví dụ: "Moves: 5/50").
Thông báo "You Win!" khi hoàn thành trò chơi.
Thông báo "Game Over! Move Limit Reached!" nếu vượt quá 50 bước.
Trên terminal:
Lịch sử di chuyển được in ra sau mỗi nước đi, với định dạng:
Move History:
Step 1: Pole A -> Pole E
Step 2: Pole B -> Pole F
Code Structure
Main File: ring_sorting_game.py
Chứa toàn bộ mã nguồn của trò chơi, bao gồm giao diện đồ họa, logic trò chơi, và thuật toán A*.
Key Functions:
draw_poles(): Vẽ các cột trên giao diện.
draw_rings(): Vẽ các vòng màu trên các cột.
draw_move_count(): Hiển thị số bước đã thực hiện và giới hạn bước.
print_moves(): In lịch sử di chuyển ra terminal.
is_goal(): Kiểm tra trạng thái mục tiêu.
heuristic(): Hàm heuristic cho thuật toán A*.
successors(): Tạo các trạng thái tiếp theo từ trạng thái hiện tại.
a_star(): Thuật toán A* để tìm đường đi tối ưu.
main(): Hàm chính điều khiển trò chơi.
Algorithm
Trò chơi sử dụng thuật toán A* để tìm đường đi tối ưu từ trạng thái ban đầu đến trạng thái mục tiêu:

Heuristic: Số cột chưa được sắp xếp (4 - số cột có 4 vòng cùng màu).
Trạng thái: Được biểu diễn bằng danh sách các cột, mỗi cột là danh sách các vòng màu. Để sử dụng trong A*, trạng thái được chuyển thành tuple để có thể băm được.
Chi phí: Mỗi bước di chuyển có chi phí là 1.
Future Improvements
Thêm giao diện chọn mức độ khó (dễ, trung bình, khó) với các trạng thái ban đầu khác nhau.
Thêm âm thanh và hiệu ứng hình ảnh khi di chuyển vòng.
Hiển thị lịch sử di chuyển trên giao diện đồ họa (nếu cần).
Lưu trữ điểm số cao nhất và số bước tối thiểu để hoàn thành trò chơi.
License
This project is licensed under the MIT License. Feel free to use, modify, and distribute the code as you see fit.

Contact
If you have any questions or suggestions, please feel free to reach out!
