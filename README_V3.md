# Particle Core V3 — gesture, icon focus & sound

## Chạy

Giữ nguyên cấu trúc thư mục `Finalver/img`. Trong thư mục `Finalver`, chạy server local:

```bash
python -m http.server 8000
```

Mở `http://localhost:8000/Version2.html` bằng Chrome hoặc Edge, cấp quyền camera. Cần Internet để tải thư viện Three.js và MediaPipe từ CDN. Tránh mở qua `file://` vì trình duyệt có thể chặn quyền camera/tải ảnh.

## Tương tác

- **Ngón trỏ**: đưa đầu ngón trỏ vào icon; con trỏ ảo sáng lên, icon phóng nhẹ. Khi dùng camera, X được đảo để đồng nhất với preview phản chiếu.
- **Chụm ngón cái + trỏ**: chọn icon (phải nhắm vào icon trước khi chụm). Icon phóng lên và panel tên xuất hiện. Bấm Đóng để bỏ chọn.
- **Nắm tay**: kéo xoay quả cầu. **Hai tay**: thay đổi khoảng cách để zoom.
- **Chuột**: rê để hover, click icon để chọn; kéo để xoay, cuộn để zoom.
- Âm thanh Hover/Select/Close được tạo bằng Web Audio API, có nút tắt và thanh âm lượng. Do chính sách trình duyệt, âm thanh có thể chỉ phát sau một lần click/chạm vào trang.

## Giới hạn cần kiểm thử thực tế

- Bộ chọn được thiết kế cho desktop webcam tiêu chuẩn; độ chính xác phụ thuộc ánh sáng, khoảng cách, chất lượng camera và tốc độ thiết bị.
- Nội dung panel hiện là tên lấy từ filename icon; chưa có kho giải thích/metadata cho các khái niệm.
- Chưa kiểm thử webcam thực tế trong môi trường này; cần kiểm tra và hiệu chỉnh ngưỡng pinch (`.34` / `.52`), smoothing (`.34`), kích thước hit-target, đảo trục X theo camera thực tế.
- Sprite bị các lớp che khuất: bản demo hiện dùng raycast vào sprite, không kiểm tra vật cản/occlusion của hình cầu hạt; ưu tiên đối tượng ở vị trí giao tia gần nhất.
- Âm thanh tự tổng hợp, không cần file âm thanh hoặc dịch vụ bên ngoài.
