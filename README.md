# Track 1 — Day 20: Product Metrics Lab

- **Họ tên:** Lưu Xuân Dũng
- **Mã học viên (MHV):** 2A202602746
- **Dự án chọn làm:** P-100 — EV After-Sales AI Agent (Hệ thống hỗ trợ chăm sóc sau bán & lập kế hoạch bảo dưỡng xe điện VinFast)
- **Link Metrics Pack:**
  - 🌐 **Bản giao diện trực quan Visual UI (HTML):** [metrics-pack.html](metrics-pack.html) *(Xem trực quan bằng trình duyệt với biểu đồ, thẻ card, trạng thái Gate)*
  - 📄 **Bản tài liệu Markdown đầy đủ:** [metrics-pack.md](metrics-pack.md)
- **Tên repository khi nộp:** `Track1_Day20_2A202602746_LuuXuanDung`

---

## Làm bài

Đã hoàn thành toàn bộ chuỗi quyết định sản phẩm bắt buộc từ Phase 0 đến Phase 5 trong Metrics Pack cá nhân:
`Core action → Nature/cadence → Metric System + Retention → Product Loop → Telemetry Tracking`.

- **00 — Dự án, persona, core job:** Xác định Persona Anh Nam (Chủ xe VF 8 chạy 1.500 km/tháng) và Core Job xóa tan nỗi sợ bị mập mờ chi phí và lãng phí thời gian chờ đợi tại xưởng.
- **01 — Core Action Card + tự kiểm 5 tiêu chí:** Chọn core action `Xác nhận kế hoạch và đặt lịch bảo dưỡng định kỳ` (`confirm_maintenance_booking`), vượt qua toàn bộ 5/5 tiêu chí của Gate 1.
- **02 — Action Nature Card + kết luận cadence:** Phân tích bản chất hành vi theo mốc ODO 12.000 km (~6–12 tháng), kết luận nhịp đo Semi-annual / Annual window ở cấp phương tiện (Vehicle/Owner).
- **03 — Metric System:** Định nghĩa Activation (Active ≠ Activated), 2 góc Engagement (Depth & Frequency), North Star Metric (NSM) chuẩn 3 thành phần kèm 3 Leading Indicators và 2 Counter-metrics nghiêm ngặt.
- **04 — Retention Definition:** Định nghĩa ma trận Retention đủ 6 thành phần (Unit, Cohort entry, Return event, Window, Threshold, Segment).
- **05 — Product Loop:** Thiết kế Milestone & Vehicle Progress Loop qua 2 chu kỳ (mốc 12k và 24k km), trả lời thuyết phục lý do quay lại ngoài notification, kèm metric hypothesis.
- **06 — Tracking nhanh:** Đặc tả 7 Core Events chuẩn cấu trúc `object_action` kèm 2 Acceptance Criteria kỹ thuật chống bắt sớm UI và chống trùng lặp dữ liệu do reload.

---

## Điều tôi mang về áp dụng cho dự án thật

Trải qua bài lab này với tư cách là người trực tiếp tham gia phát triển giao diện Chủ xe và kết nối API backend cho dự án P-100, tôi đúc kết được 3 bài học và quyết định kỹ thuật sâu sắc để áp dụng ngay vào dự án:

### 1. Phân biệt sống còn giữa AI "hội thoại" và AI "tạo giá trị nghiệp vụ"
Trước đây trong quá trình build MVP P-100, đội ngũ rất dễ bị cuốn vào các chỉ số vanity xung quanh AI chatbot: số lượt gửi tin nhắn, thời gian trong phiên chat, số lượt tra cứu RAG cẩm nang xe. Tuy nhiên, nhìn từ góc độ Product Metrics, **người dùng không mở app để trò chuyện giải trí với AI; họ cần chiếc xe ô tô của mình được bảo dưỡng an toàn, đúng hạn và không bị "chém giá"**.  
AI trong P-100 thực chất là một lớp điều phối thông minh (Orchestrator): nó phân tích ODO, bóc tách bảng giá minh bạch và sắp xếp lịch xưởng. Do đó, Core Action và North Star Metric phải gắn chặt với hành vi giao dịch và kết quả vật lý thực tế: **Lượt xe hoàn tất bảo dưỡng định kỳ đúng hạn và khớp dự toán chi phí**.

### 2. Nguyên tắc "Nature vs Nurture" cứu sản phẩm khỏi cạm bẫy Spam Notification
Bảo dưỡng ô tô là nghiệp vụ có chu kỳ tự nhiên thấp (low-frequency, 6–12 tháng một lần) nhưng giá trị cam kết rất cao (high-stakes). Nếu áp dụng một cách máy móc tư duy của các ứng dụng mạng xã hội hay SaaS (đo DAU, WAU, D7 retention), sản phẩm sẽ rơi vào cái bẫy "nuôi dưỡng cưỡng ép": gửi notification liên tục, tạo streak/gamification vô nghĩa khiến chủ xe cảm thấy bị làm phiền và xóa app.  
Bài học lớn nhất là: **Phải tôn trọng bản chất tự nhiên (nature) của hành vi**. Chiếc xe lăn bánh ngoài đời thực và đồng hồ ODO trên màn hình taplo chính là Natural Trigger mạnh nhất. Nhiệm vụ của phần mềm là trở thành nơi lưu trữ dữ liệu có giá trị tích lũy (Sổ bảo dưỡng điện tử, lịch sử pin), để khi chiếc xe đến mốc, người dùng tự nhiên có lý do vững chắc nhất để quay lại.

### 3. Chuẩn hóa kiến trúc Telemetry Tracking ngay ở tầng Backend Service P-100
Trong kiến trúc backend của P-100 (`src/services/booking_service.py` và `src/agents/tools/`), tôi sẽ áp dụng trực tiếp 2 Acceptance Criteria của bài lab:
- Không bao giờ phát telemetry event ở sự kiện nhấp chuột trên giao diện (UI click), mà chỉ phát sự kiện khi transaction backend đã commit thành công vào PostgreSQL kèm theo `operation_key` và `booking_id`.
- Tích hợp Counter-Metric `cost_variance_rate` (độ lệch chi phí thực tế so với AI dự toán) vào hệ thống logging. Bất cứ khi nào chi phí thực tế tại xưởng lệch quá 5% so với dự toán ban đầu mà AI đã cam kết với khách hàng, hệ thống sẽ tự động gắn cờ cảnh báo (flag audit) để rà soát quy trình xưởng dịch vụ, bảo vệ tuyệt đối uy tín và sự minh bạch của thương hiệu.

---

## Revision & Rationale

- **Revision 1 (Từ chối chỉ số DAU/WAU & lượt chat AI):** Đã kiên quyết loại bỏ ý tưởng dùng DAU và số câu prompt chat với AI làm metric chính; thay thế bằng nhịp đo Semi-annual / Annual gắn liền với tiến trình tăng ODO 12.000 km của xe.
- **Revision 2 (Bổ sung ràng buộc chất lượng chi phí vào North Star Metric):** Bác bỏ định nghĩa NSM chỉ đơn thuần là "Tổng số booking". Bổ sung thêm điều kiện chất lượng bắt buộc: *Dự toán chi phí chính xác (sai lệch ≤ 5%) và không có khiếu nại phát sinh*, biến NSM thành chỉ số phản ánh giá trị chân thực cho cả Chủ xe, Xưởng và Nền tảng.
