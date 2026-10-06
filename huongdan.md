# Hướng dẫn lab Track 1 — Day 20: Product Metrics

Nguồn: [Brief lab trên VLearn](https://vlearn.dev/course/k04-l34-p2-t1/reader?day=D08&part=lab-961eda13-s02-doc), đọc ngày 06/10/2026, gồm các phần 1–11 và màn hình nộp bài/đánh giá.

## 1. Hiểu mục tiêu và đầu ra

Bạn đóng vai PM của **một use case trong dự án đang build**. Bài làm cá nhân, kể cả dự án nhóm. Không cần lập trình. Chuỗi quyết định bắt buộc:

**Core action → Nature/cadence → Metric System + Retention → Product Loop → Tracking.**

Thời gian làm bài: 90 phút. Ưu tiên Phase 1–3; Phase 4 chỉ ghi nhanh ý chính.

| Phase | Thời gian | Đầu ra |
| --- | --- | --- |
| 0 — Chốt phạm vi | 10 phút | Dự án, persona, core job |
| 1 — Core Action | 15 phút | Core Action Card + tự kiểm |
| 2 — Nature & cadence | 15 phút | Action Nature Card + kết luận cadence |
| 3 — Metric System + Retention | 25 phút | Bộ metric + retention đủ 6 thành phần |
| 4 — Loop + Tracking | 15 phút | Loop ít nhất 2 chu kỳ, hypothesis, 4–8 events |
| 5 — Tự soi & nộp | 10 phút | Sửa lỗi, hoàn thiện pack và repo |

## 2. Chuẩn bị

1. Chọn một dự án đang build và một use case chính. Nếu chưa có dự án, brief gợi ý AI Travel Planner, AI Personal Assistant for Students hoặc AI Customer Support Agent.
2. Chuẩn bị deck Day 20 và đồng hồ bấm giờ.
3. Tạo một **tệp Metrics Pack trực quan riêng** bằng FigJam, slide, Notion, HTML hoặc tương đương; copy các bảng dưới đây sang tệp đó rồi tự điền.
4. Ghi họ tên, mã học viên (MHV), dự án lên tệp. Dùng đúng các mục 00–06 sau:

```text
00 — Dự án, persona, core job
01 — Core Action Card + kết quả tự kiểm 5 tiêu chí
02 — Action Nature Card + kết luận cadence
03 — Metric System: activation / engagement / NSM / leading / counter
04 — Retention Definition: 6 thành phần
05 — Product Loop: 2 chu kỳ + metric hypothesis
06 — Tracking nhanh: 4–8 events + ít nhất 2 acceptance criteria
```

Tài liệu cần tra trong deck (theo brief): Nature vs Nurture S21–24; metric từ use case S25–28; Active ≠ Activated S26; cohort retention S29–30; ba mốc so retention S34; Metric Definition Contract S47; case health app S48–51; NSM S6–9; loop S36–43 và case Duolingo S46. Hướng dẫn này được tổng hợp từ brief, chưa kiểm tra nội dung deck riêng.

## 3. Phase 0 — Chốt phạm vi (10 phút)

Điền vào mục **00** của Metrics Pack:

| Mục | Bạn tự điền |
| --- | --- |
| Dự án | [Sản phẩm đang build là gì?] |
| Persona | [Một persona chính của use case này] |
| Core job | [Việc họ muốn hoàn thành, viết bằng lời người dùng] |

Core job phải mô tả nhu cầu/vấn đề. Ví dụ trong brief: người học mất thời gian gom thông tin môn học và vẫn bỏ lỡ deadline. “Cần một AI assistant thông minh” là mô tả tính năng, chưa phải core job.

## 4. Phase 1 — Core Action (15 phút)

### Bước 4.1 — Phân biệt bốn khái niệm (5 phút)

| Khái niệm | Câu hỏi | Bạn tự điền |
| --- | --- | --- |
| Core job | User cố hoàn thành việc gì? | [...] |
| Core action | User làm gì trong sản phẩm để tiến tới giá trị? | [...] |
| Core value | User nhận lợi ích gì? | [...] |
| Core value event | Sự kiện nào chứng minh giá trị đã xảy ra? | [...] |

Action và value event có thể khác nhau: đặt xe là action, chuyến xe hoàn thành mới xác nhận value. AI sinh kết quả chưa chứng minh user đã nhận giá trị.

### Bước 4.2 — Điền Core Action Card (10 phút, gồm tự kiểm)

| Thành phần | Bạn tự điền |
| --- | --- |
| Target user | Ai thực hiện? |
| Core job | Họ muốn hoàn thành việc gì? |
| Core action | Hành vi cụ thể được chọn? |
| Object | Hành vi tác động lên đối tượng nào? |
| Preconditions | Điều kiện cần trước hành vi? |
| Completion rule | Chính xác khi nào hành vi hoàn tất? |
| Core value | Lợi ích user nhận được? |
| Evidence of value | Bằng chứng giá trị đã xảy ra? |
| Candidate event | Event dự kiến để tracking? |

### Bước 4.3 — Tự kiểm và ghi kết quả ở mục 01

| Tiêu chí | Đạt/chưa đạt | Lý do bạn tự viết |
| --- | --- | --- |
| Gần core value: action giúp user tiến gần rõ rệt tới giá trị | [...] | [...] |
| Lặp lại được khi nhu cầu quay lại | [...] | [...] |
| Quan sát được thời điểm hoàn tất | [...] | [...] |
| Có ý nghĩa: tăng hành vi phản ánh sản phẩm tốt hơn | [...] | [...] |
| Team có thể tác động để cải thiện hành vi | [...] | [...] |

Trượt từ 2 tiêu chí thì phải chọn lại. **Gate 1 ở Phase 1 yêu cầu ít nhất 4/5**, đủ actor/object/completion rule và giải thích được vì sao action không chỉ là mở app/hỏi AI. Bảng đánh giá cuối brief lại ghi “qua 5 tiêu chí”; nên hoàn thiện đủ cả 5 trước khi nộp để đáp ứng cả hai cách diễn đạt.

Tránh core action mơ hồ như “engage”, “sử dụng sản phẩm”, hoặc chỉ là đăng nhập, mở app, hỏi AI.

## 5. Phase 2 — Nature & cadence (15 phút)

### Bước 5.1 — Action Nature Card (10 phút)

Điền vào mục **02**:

| Thành phần | Câu hỏi để tự trả lời |
| --- | --- |
| Actor | User, account, team hay object nào thực hiện? |
| Intent | Hành vi bắt đầu từ nhu cầu gì? |
| Trigger | User chủ động, sự kiện ngoài, người khác hay hệ thống kích hoạt? |
| Effort | Mất bao nhiêu thời gian, suy nghĩ, dữ liệu? |
| Value timing | Giá trị đến ngay, trễ, tích lũy hay phụ thuộc người khác? |
| State | Dữ liệu/trạng thái nào được giữ lại sau action? |
| Dependency | Có phụ thuộc nguồn cung, thành viên, approval hay thời điểm? |
| Repeat condition | Điều gì khiến hành vi có lý do xuất hiện lại? |

### Bước 5.2 — Tự kết luận cadence (5 phút)

1. Chọn một dạng hành vi: thói quen thường xuyên, tiến trình tích lũy, theo dự án, giao dịch, workflow của team, phản ứng theo sự kiện hoặc theo chu kỳ.
2. Tự điền câu sau:

> Đối với [persona/unit], core action [hành vi] thường xuất hiện [nhịp] vì [lý do từ nature]. Do đó, nhịp đo phù hợp là [cadence/window] ở cấp [unit].

Không chọn daily/weekly/monthly chỉ vì dashboard hay dùng. Hỏi xem frequency cao hơn có thực sự tạo thêm value không; sản phẩm AI làm xong việc nhanh hơn có thể tốt hơn dùng lâu hơn.

**Gate 2:** kết luận đúng template, có lý do “vì” thuyết phục, nhịp đo phù hợp dạng hành vi. Nature là nhịp nhu cầu tự nhiên; nurture như email/notification chỉ hỗ trợ nhịp đó.

## 6. Phase 3 — Metric System + Retention (25 phút)

### Bước 6.1 — Activation (5 phút)

Ghi ở mục **03**:

| Thành phần | Bạn tự điền |
| --- | --- |
| Start event | Event đánh dấu user bắt đầu |
| Activation event | Event xác nhận core action đầu tiên/first value |
| Time window | Khoảng thời gian cho phép tính từ start event |

Không dùng hoàn tất tour giới thiệu hoặc đăng nhập nếu chưa tạo core value. Brief có cả mô tả activation là lần đầu nhận value và lưu ý activated liên quan lặp đủ hành vi; làm rõ định nghĩa vận hành đang dùng, rồi tra S26 nếu cần phân biệt hai ngưỡng.

### Bước 6.2 — Engagement (3 phút)

Chọn **tối đa 2** góc: frequency (số lần action trong cadence tự nhiên), depth (value mỗi lần), breadth (số workflow/use case được dùng). Ghi cách đo cụ thể cho từng góc bạn chọn.

### Bước 6.3 — Retention Definition (7 phút)

Ghi đủ ở mục **04**:

| Thành phần | Bạn tự điền |
| --- | --- |
| Unit | User/account/team/organization/object được đo |
| Cohort entry | Event đưa unit vào cohort |
| Return event | Core action/value event phải lặp lại |
| Window | Daily/weekly/monthly/project-based/custom bracket cụ thể |
| Threshold | Số lần cần xảy ra trong window |
| Segment | Nhóm đối tượng áp dụng |

Retention phải khớp Phase 2. Không chỉ ghi “D7 retention”; action theo tháng không nên đo D7 theo thói quen. So retention với natural cycle, cohort đúng segment và benchmark category có nguồn; không bịa benchmark hoặc so với một con số cứng.

### Bước 6.4 — North Star, leading và counter (10 phút)

| Metric | Nội dung cần điền |
| --- | --- |
| North Star Metric (NSM) | **Unit of value + quality threshold + frequency** |
| Leading indicators | Tối đa 3, mỗi chỉ số kèm lý do dự báo core action lặp lại |
| Counter-metric | Ít nhất 1, phản ánh điều không được xấu đi khi core action tăng |

NSM phản ánh value user nhận được. Revenue, lượt mở app hoặc số lượt hỏi AI thuần túy chưa đủ. Counter có thể xem chất lượng câu trả lời, chi phí/lượt dùng hoặc tỷ lệ kết quả bị bỏ qua, tùy dự án.

**Gate 3:** activation đủ 3 trường; retention đủ 6 thành phần và khớp cadence; NSM đủ 3 thành phần; có ít nhất 1 counter-metric.

## 7. Phase 4 — Product Loop + Tracking nhanh (15 phút)

### Bước 7.1 — Vẽ loop (khoảng 8 phút)

Ghi ở mục **05**, thể hiện tối thiểu hai chu kỳ:

```text
Natural trigger → Core action → Immediate value → Saved state/investment
→ Next natural trigger → Core action tiếp theo → Repeat value
```

1. Chọn loại loop chính: habit, progress, project, workflow, transaction, event-response hoặc account-level.
2. Trả lời: nếu bỏ notification, user còn lý do gì để quay lại?
3. Tự viết metric hypothesis bắt buộc:

> Nếu loop này hoạt động, metric [metric ở Phase 3] sẽ thay đổi theo hướng [hướng thay đổi] trong [khung thời gian], vì [lý do].

Không khởi đầu loop bằng streak/badge/notification; suy loop từ metric và nhu cầu thật.

### Bước 7.2 — Tracking (khoảng 7 phút)

Ghi **4–8 core events** ở mục **06**, mỗi event đủ 4 trường:

| Tên event (object_action) | Ý nghĩa: điều đã xảy ra | Thời điểm ghi nhận chính xác | Metric Phase 3 sử dụng |
| --- | --- | --- | --- |
| [event_1] | [...] | [...] | [...] |
| [event_2] | [...] | [...] | [...] |
| [event_3] | [...] | [...] | [...] |
| [event_4] | [...] | [...] | [...] |

Thêm hàng nếu cần, tối đa 8 events. Bỏ event không map về metric. Đồng thời kiểm tra mỗi metric có event đủ để tính.

Viết **ít nhất 2 acceptance criteria**, ưu tiên:

1. Event chỉ ghi nhận khi hành vi thực sự hoàn tất, không phải lúc vừa bấm nút.
2. Reload/retry/autosave không tạo bản ghi trùng cùng một hành vi.

Ví dụ minh họa từ brief: `task_completed` chỉ được ghi khi nhiệm vụ chuyển từ chưa hoàn thành sang hoàn thành, gắn với `user_id` và `task_id`; reload không tạo thêm event cho cùng lần chuyển trạng thái. Hãy viết tiêu chí tương ứng với event của dự án mình.

Ngoài giờ, có thể bổ sung identity, object, required properties, loại trừ bot/tài khoản nội bộ và timezone; tra Metric Definition Contract S47. Đây là phần mở rộng không bắt buộc trong 15 phút.

**Gate 4:** loop đủ hai chu kỳ, hypothesis trỏ về metric Phase 3, mọi event map về ít nhất một metric.

## 8. Phase 5 — Tự soi và hoàn thiện (10 phút)

- [ ] Core action thực sự là hành vi tạo value, phân biệt với thao tác UI/output hệ thống.
- [ ] Activation xác nhận core value, không chỉ onboarding/login.
- [ ] Frequency phù hợp nhu cầu thật.
- [ ] Loop có reason to return ngoài notification.
- [ ] Retention window phù hợp cadence của hành vi.
- [ ] Mọi event map về một metric.
- [ ] Mọi metric có event đủ để tính.

Nếu đổi core action/cadence hay quyết định lớn, tự ghi một dòng lý do trong phần **Revision** cuối tệp. Nếu giữ lựa chọn khác quy tắc, giải thích rõ. **Gate 5 ở Phase 5:** đã đối chiếu 7 câu và sửa lỗi hoặc giải thích lựa chọn.

Lưu ý bảng gate cuối brief dùng Gate 5 cho Tracking (4–8 events và ≥2 acceptance criteria), khác tên Gate 5 trong Phase 5. Trước khi nộp cần đáp ứng **cả checklist tự soi lẫn điều kiện Tracking**.

## 9. Quy tắc dùng AI và AI Support Log

Được dùng AI để brainstorm ứng viên core action, phản biện, gợi ý tên event/acceptance criteria, đóng vai khách hàng khó tính.

Bạn phải tự chọn core action, tự viết kết luận cadence, metric hypothesis, rationale và reflection. Không dùng AI bịa số liệu hoặc benchmark không nguồn.

Hoàn thiện `ai-support-log.md` bằng trải nghiệm thật của bạn:

1. AI đã giúp tôi ở đâu?
2. AI sai/hời hợt/đề xuất metric sai nature ở đâu?
3. Tôi đã tự sửa hoặc quyết định lại điều gì?

Việc dùng Codex đọc brief, tạo repo và hướng dẫn cũng nên được khai báo. Không ghi giả một phản biện hoặc quyết định chưa xảy ra.

## 10. Hoàn thiện repo và nộp

Repo làm việc local đặt tại `F:\Vinuni\Track1\Day20`. **Tên repository khi nộp** phải là `Track1_Day20_MHV_HoVaTen` (thay MHV và HoVaTen bằng thông tin thật).

```text
Day20/
├── .git/
├── huongdan.md          # hướng dẫn từng bước này
├── README.md            # thông tin cá nhân, dự án, link Metrics Pack, reflection
└── ai-support-log.md    # khai báo việc dùng AI
```

1. Tự hoàn thành Metrics Pack đủ mục **00–06 (7 mục)**. Brief có dòng “đủ 6 mục (00–06)”; danh sách thực tế gồm 7 mục, nên giữ đầy đủ 00–06.
2. Điền họ tên, MHV, dự án và link Metrics Pack vào README.
3. Cấp quyền xem Metrics Pack và thử link bằng tài khoản khác/chế độ chưa đăng nhập phù hợp.
4. Tự viết điều bạn mang về áp dụng cho dự án thật và hoàn thiện AI Support Log.
5. Lưu thay đổi bằng Git trong PowerShell:

```powershell
Set-Location -LiteralPath 'F:\Vinuni\Track1\Day20'
git status
git add README.md ai-support-log.md huongdan.md
git commit -m "docs: complete Day 20 product metrics lab"
```

Nếu chưa cấu hình tác giả Git, cấu hình tên/email thật cho repo bằng `git config user.name "Tên của bạn"` và `git config user.email "Email của bạn"`, rồi commit lại.

6. Tạo repository cá nhân trên GitHub đúng tên quy định; lấy URL thật rồi thêm remote/push (chỉ thực hiện sau khi đã tạo repo và có quyền truy cập):

```powershell
git remote add origin https://github.com/<tai-khoan>/Track1_Day20_<MHV>_<HoVaTen>.git
git branch -M main
git push -u origin main
```

Lệnh remote là mẫu, phải thay các phần trong dấu `<...>`. Nếu đã có `origin`, kiểm tra bằng `git remote -v` trước khi thay đổi.

7. Trên VLearn mở **Nộp bài và đánh giá Lab**, điền link bài đã nộp (GitHub/Drive/LMS), chọn đánh giá 1–5 sao, rồi xác nhận đã nộp bài. Trang ghi mỗi lab giữ một bài; nộp lại sẽ ghi đè.
8. Hạn hiển thị khi đọc: **06/10/2026 23:59, giờ Việt Nam**. Kiểm tra lại trên trang trước khi nộp.

### Checklist cuối

- [ ] Repository nộp đúng tên `Track1_Day20_MHV_HoVaTen`.
- [ ] README đủ họ tên, MHV, dự án, link có quyền xem và reflection tự viết.
- [ ] Metrics Pack đủ 00–06, chuỗi quyết định dùng lại kết quả các mục trước.
- [ ] Core Action Card đủ trường và tự kiểm 5 tiêu chí.
- [ ] Cadence có lý do từ nature; retention đủ 6 thành phần, khớp cadence.
- [ ] Activation/NSM đủ thành phần; có leading indicators và counter-metric.
- [ ] Loop ít nhất hai chu kỳ, hypothesis nối metric.
- [ ] Tracking có 4–8 events, mỗi event map metric, ít nhất 2 acceptance criteria.
- [ ] Revision có lý do nếu thay đổi lớn; AI Support Log là khai báo thật.
- [ ] Bạn có thể bảo vệ core action, retention và một event bất kỳ khi coach hỏi.

## 11. Trạng thái ban đầu

Repo và tài liệu này chỉ chuẩn bị môi trường cùng hướng dẫn. Các thông tin cá nhân, Metrics Pack, quyết định product, reflection, repo GitHub và thao tác nộp bài cần được hoàn thiện trong quá trình làm lab.
