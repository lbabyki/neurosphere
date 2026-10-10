# V3 Minimal Patch — giữ nguyên con trỏ và pinch

Nền tảng: V3 do người dùng cung cấp. Không thay đổi `updateFingerCursor`, `hideFingerCursor`, các ngưỡng pinch 0.34 / 0.52, thuật toán hover / raycast, logic POINT/FIST/ZOOM.

Chỉ bổ sung:
1. Focus icon dựa theo camera, giới hạn tọa độ hiển thị để icon trong lõi không bay khỏi màn hình.
2. Khi chọn icon: hiện tên; chọn lại cùng icon: mở/thu thông tin khái niệm. Dữ liệu mô tả chuẩn bị cho các tên phổ biến; tên chưa có dùng chú thích mặc định.
3. Giữ mở năm ngón trong ~520 ms để bỏ chọn và đóng panel. Nút Đóng và Escape cũng có tác dụng.

Chạy: tại thư mục Finalver `python -m http.server 8000`, mở http://localhost:8000/Version2.html.

Lưu ý: Đã kiểm tra cú pháp JS, chưa kiểm thử webcam thực tế. Nếu góc nhìn/độ zoom cực đoan gặp bất thường, cần kiểm tra trên trình duyệt với camera thật.
