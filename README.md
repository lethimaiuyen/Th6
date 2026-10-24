# Đấu trường Tin học 6 KNTT – game thi đấu trực tiếp

Game dùng Node.js thuần, không cần cài thư viện. Có mã PIN 6 số, giáo viên nhấn Bắt đầu một lần, sau đó câu hỏi tự chạy, bảng xếp hạng trực tiếp, rút ngẫu nhiên 20 câu (12 trắc nghiệm + 8 trả lời ngắn), chấm điểm theo tốc độ và chuỗi trả lời đúng, lời giải sau từng câu.

## Chạy trên máy tính

1. Cài Node.js 18 trở lên.
2. Mở terminal trong thư mục này và chạy `npm start`.
3. Mở `http://localhost:3000` trên máy giáo viên.

Để học sinh tham gia từ thiết bị khác, cần đưa server lên một dịch vụ chạy Node.js công khai (ví dụ Render hoặc Railway). **Không thể chỉ tải riêng HTML lên Google Drive hoặc GitHub Pages**, vì cần máy chủ giữ trạng thái phòng và phát sự kiện trực tiếp. Sau khi triển khai, giáo viên và học sinh dùng chung địa chỉ website và nhập PIN hiển thị.

## Triển khai trên Render

1. Tạo repository GitHub chứa toàn bộ thư mục này.
2. Render → New Web Service → chọn repository.
3. Build command: để trống hoặc `npm install`; Start command: `npm start`.
4. Dùng URL HTTPS Render cấp để tạo phòng và tham gia. Dùng một instance để bảo đảm dữ liệu phòng đồng nhất.

## Lưu ý

- Phòng và điểm chỉ lưu trong RAM; khởi động lại máy chủ sẽ mất dữ liệu.
- Hiện chưa có đăng nhập giáo viên, bảo vệ chống gian lận nâng cao, hoặc đồng bộ Google Sheets.
- Tự luận chấm theo đáp án/từ khóa nên có thể không công nhận câu diễn đạt tương đương. Giáo viên cần xem lại nội dung câu hỏi và đáp án trước khi dùng chính thức.
- Nên chạy thử với vài học sinh trước buổi học.

## Chế độ tự động

Giáo viên tạo phòng, học sinh vào bằng PIN, giáo viên nhấn Bắt đầu. Hệ thống tự chạy mỗi câu trắc nghiệm 25 giây, mỗi câu trả lời ngắn 50 giây, tự hiện đáp án và lời giải trong 8 giây, rồi tự chuyển câu. Bảng xếp hạng cập nhật liên tục. Giáo viên có thể kết thúc câu sớm hoặc chuyển câu ngay. Sau câu cuối, game tự kết thúc.
