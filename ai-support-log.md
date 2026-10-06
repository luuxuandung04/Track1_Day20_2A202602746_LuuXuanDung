# AI Support Log — Day 20: Product Metrics Lab

**Học viên:** Lưu Xuân Dũng · **MHV:** 2A202602746 · **Dự án:** P-100 — EV After-Sales AI Agent

---

## 1. AI đã giúp tôi ở đâu?

- **Đọc brief và chuẩn bị khung tài liệu ban đầu:** Codex đã hỗ trợ đọc nội dung brief trên nền tảng VLearn, tổng hợp bộ hướng dẫn từng bước chi tiết (`huongdan.md`) và khởi tạo repository local cùng các tệp mẫu (`README.md`, `ai-support-log.md`).
- **Brainstorm ứng viên Core Action và Event Telemetry:** AI hỗ trợ liệt kê các bước trong luồng người dùng để tôi chọn lọc ra core action mang tính cam kết giá trị cao nhất (`confirm_maintenance_booking`) thay vì các hành vi bề mặt.
- **Rà soát tính đầy đủ của các Gate:** AI hỗ trợ kiểm tra chéo xem bài làm đã bao phủ đủ 5 tiêu chí của Core Action, 6 thành phần của Retention Matrix và 3 thành phần của North Star Metric hay chưa.
- **Hiện thực hóa giao diện trực quan (Visual Metrics Pack):** AI hỗ trợ viết mã HTML/CSS hiện đại, responsive và tối ưu print stylesheet cho tệp `metrics-pack.html` để tạo thành một bản Metrics Pack trực quan, chuyên nghiệp phục vụ việc trình bày và nộp bài.

---

## 2. AI sai, hời hợt hoặc đề xuất metric sai nature ở đâu?

- **Đề xuất metric sai lệch nghiêm trọng bản chất tự nhiên (Nature of Behavior):**  
  Khi được hỏi về hệ thống chỉ số cho sản phẩm AI Agent, AI ban đầu có xu hướng rập khuôn đưa ra các metric quen thuộc của sản phẩm SaaS hoặc mạng xã hội như: *Daily Active Users (DAU), Weekly Active Users (WAU), Tỷ lệ người dùng mở app mỗi 7 ngày (D7 Retention), và Số câu prompt hỏi bot mỗi tuần*.  
  Đây là một đề xuất hời hợt và hoàn toàn sai lệch bản chất tự nhiên của nghiệp vụ chăm sóc xe hơi: Xe ô tô điện lăn bánh theo số km thực tế và chỉ cần bảo dưỡng định kỳ mỗi 12.000 km (~6–12 tháng một lần). Khách hàng không có nhu cầu và không thể mang xe đi bảo dưỡng mỗi tuần. Việc áp đặt DAU/WAU hay ép người dùng vào app chat hàng tuần sẽ biến sản phẩm thành một công cụ spam notification phiền toái, phá hủy niềm tin thương hiệu.
- **Đề xuất North Star Metric hời hợt, thiếu điều kiện chất lượng:**  
  AI ban đầu gợi ý NSM là *"Tổng số lượt đặt lịch bảo dưỡng thành công trên tháng (Total Monthly Bookings)"*. Đây là một Vanity Metric thuần túy về số lượng. Nếu AI tư vấn sai hoặc cố tình "báo giá rẻ ảo" để người dùng đặt lịch, nhưng khi đến xưởng chi phí thực tế bị đội lên gấp đôi dẫn đến khách hàng bức xúc cãi vã, thì số lượng booking tăng lên thực chất là một sự thất bại về mặt giá trị.
- **Gợi ý Tracking Event bắt sai thời điểm (UI-level click thay vì backend confirmation):**  
  AI gợi ý đặt event tracking tại sự kiện nhấp chuột của người dùng (`button_booking_clicked`). Đây là lỗi kỹ thuật phổ biến: người dùng có thể bấm nhầm nút, mạng bị mất kết nối, hoặc backend trả về lỗi quota xưởng đầy mà event vẫn bị tính, làm sai lệch hoàn toàn dữ liệu funnel chuyển đổi.

---

## 3. Tôi đã tự sửa hoặc quyết định lại điều gì?

- **Tự quyết định Cadence và nhịp đo Retention chuẩn xác:**  
  Tôi đã kiên quyết bác bỏ toàn bộ các chỉ số DAU/WAU; tự xác lập nhịp đo phù hợp là **Semi-annual / Annual window (khung 6 tháng và 12 tháng)** ở cấp độ Phương tiện (Vehicle / VIN) gắn với điều kiện thực tế là xe phải lăn bánh tích lũy đủ $\ge 10.000\text{ km}$.
- **Tự chuẩn hóa công thức North Star Metric đủ 3 thành phần gắn với chất lượng minh bạch:**  
  Tôi đã cấu trúc lại NSM thành: **Monthly Completed Accurate-Cost Maintenances (Số lượt xe hoàn tất bảo dưỡng định kỳ đúng hạn và khớp dự toán chi phí mỗi tháng)**. Tôi đưa tiêu chí chất lượng bắt buộc là: *Chênh lệch chi phí thực tế tại xưởng so với dự toán ban đầu của AI phải $\le 5\%$ và không có khiếu nại phát sinh*, đảm bảo NSM phản ánh giá trị chân thực cho cả Chủ xe, Xưởng dịch vụ và Nền tảng P-100.
- **Tự thiết lập 2 Counter-Metrics để kiềm tỏa rủi ro nghiệp vụ:**  
  Tôi tự đưa vào `cost_variance_rate` (tỷ lệ chênh lệch chi phí thực tế vs dự toán) và `cancellation_and_no_show_rate` (tỷ lệ hủy lịch / vắng mặt) để ngăn chặn việc chạy theo số lượng mà đánh mất chất lượng dịch vụ.
- **Tự xây dựng 2 Acceptance Criteria kỹ thuật gắn liền với kiến trúc backend thật của P-100:**  
  Dựa trên kinh nghiệm trực tiếp code và test luồng booking ở backend P-100, tôi yêu cầu event `maintenance_booking_submitted` chỉ được bắn ra khi API `POST /api/v1/bookings` phản hồi `201 Created` và commit thành công với `operation_key`; đồng thời quy định cơ chế Idempotent tracking cho event `service_maintenance_completed` để ngăn chặn trùng lặp dữ liệu khi client reload trang hoặc polling trạng thái.
