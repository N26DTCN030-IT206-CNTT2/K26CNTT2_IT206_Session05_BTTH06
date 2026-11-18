# Phần 1: Bộ Prompt Chaining (Tích hợp CoT & Context Management)
## Prompt 1: Phân tích Tính khả thi & Khung Lịch trình (Chain-of-Thought)
Vai trò: Chuyên gia Quản lý Sự kiện Sinh viên.
Dữ liệu gốc: Sự kiện "AI Innovation Day" | Quy mô: 150 SV | Thời gian: 1 ngày | Ngân sách: Tối đa 15.000.000đ | Nhân sự: 10 người | Mục tiêu: Hiểu & trải nghiệm AI trong học tập, công việc.
Yêu cầu: Suy luận từng bước (Chain-of-Thought):
1. Đánh giá tính khả thi của 150 SV với 15 triệu đồng (tính chi phí bình quân/người) và tỷ lệ 10 nhân sự điều phối (1 nhân sự/15 SV).
2. Thiết kế lịch trình chi tiết trong 1 ngày (Sáng/Chiều) đảm bảo có cả lý thuyết và khu vực trải nghiệm AI thực tế.
Ràng buộc: Không thay đổi dữ liệu gốc. Đặt tên đầu ra là [OUTPUT_1].

## Prompt 2: Dự toán Ngân sách & Phân công Nhân sự (Prompt Chaining)
Vai trò: Trưởng ban Hậu cần & Tài chính.
Ngữ cảnh đầu vào: Dữ liệu gốc + [OUTPUT_1: Dán kết quả Prompt 1 vào đây].
Yêu cầu: Suy luận từng bước để phân bổ nguồn lực khớp với lịch trình ở [OUTPUT_1]:
1. Lập bảng dự toán ngân sách chi tiết (Hạng mục | Đơn giá | Số lượng | Thành tiền). Tổng bắt buộc ≤ 15.000.000đ (có quỹ dự phòng).
2. Lập bảng phân công nhiệm vụ cụ thể cho đúng 10 nhân sự theo từng giai đoạn (Trước - Trong - Sau sự kiện).
Ràng buộc: Bắt buộc kiểm tra phép cộng tổng tiền để không vượt trần 15 triệu. Đặt tên đầu ra là [OUTPUT_2].

## Prompt 3: Kế hoạch Truyền thông & Tóm tắt Ngữ cảnh (Context Management)
Plaintext
Vai trò: Trưởng ban Truyền thông & Điều phối Dự án.
Ngữ cảnh đầu vào: Dữ liệu gốc + [OUTPUT_1] + [OUTPUT_2: Dán kết quả Prompt 2 vào đây].
Yêu cầu:
1. Xây dựng kế hoạch truyền thông trước sự kiện (2 tuần) nhằm thu hút đủ 150 sinh viên đăng ký, chi phí nằm trong ngân sách truyền thông ở [OUTPUT_2].
2. Tạo một khối [CONTEXT_SUMMARY] cô đọng (dưới 200 từ) khóa chặt toàn bộ thông số, lịch trình, ngân sách và nhân sự để mang sang hội thoại mới mà không bị đứt gãy ngữ cảnh.

## Prompt 4: Kiểm tra Tính thống nhất & Hiệu chỉnh Rủi ro (CoT Audit)
Plaintext
Vai trò: Kiểm toán viên Chất lượng Sự kiện (QA).
Ngữ cảnh đầu vào: [CONTEXT_SUMMARY] + Toàn bộ [OUTPUT_1, 2, 3].
Yêu cầu: Dùng Chain-of-Thought rà soát chéo các hạng mục để phát hiện xung đột (ví dụ: lịch trình có hoạt động nhưng ngân sách thiếu tiền, hoặc nhân sự bị quá tải giờ cao điểm).
Xuất Báo cáo kiểm tra và đề xuất phương án hiệu chỉnh ngay lập tức.



