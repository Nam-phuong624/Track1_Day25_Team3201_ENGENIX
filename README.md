# Track 1 - Day 25 — AI Team Lab

- **Team:** H3201 (Nhóm 3201)
- **Thành viên (4 người):**
  1. **Chử Trần Phương Nam** (`2A202602675`) — Tech Lead & Kỹ sư AI CAD/Geometry (Trưởng nhóm phụ trách repo)
  2. **Tô Anh Đức** — AI Product Manager & Điều phối dự án (Product Lead)
  3. **Phùng Gia Khánh** (`2A202602585`) — AI Evaluation & Takeoff Quality Lead
  4. **Phan Duy Thành** (`2A202602930`) — Product Operations & CAD Pipeline Lead
- **Tên dự án:** Hệ thống AI bóc tách bản vẽ công trình và lập dự toán sơn (ENGENIX — P-059)
- **Mã dự án & thư mục nguồn:** `P-059`
- **Link ứng dụng trực tiếp (Live Web App):** https://c4-app-059.vercel.app/
- **Link mã nguồn dự án (GitHub Repository):** https://github.com/AI20K-Build-Phase-Cohort-4/P-059

---

## 📦 Bài nộp chính thức

* **Tệp PDF 4 trang hoàn chỉnh:** [`Day25_AI-Team-Lab_Team3201.pdf`](./Day25_AI-Team-Lab_Team3201.pdf)
* **Tệp HTML nguồn dàn trang in ấn chuẩn A4:** [`Day25_AI-Team-Lab_Team3201.html`](./Day25_AI-Team-Lab_Team3201.html)

---

## 📑 Tóm Tắt 4 Artefact Cốt Lõi Của Lab (Dự án ENGENIX — P-059)

### Trang 1 — Stakeholder Map & Strategy (1 Chủ nhà thầu + 6 Kỹ sư sử dụng phần mềm)
* **Bản đồ Stakeholder (Influence $\times$ Interest):** Xác định 7 stakeholder thực tế trong doanh nghiệp tổng thầu:
  1. **Trần Đình Đông (Chủ nhà thầu / TGĐ):** Champion (Influence Cao $\times$ Quyết tâm CĐS). Nắm tổng quan 15+ dự án, tối ưu chi phí và tăng tốc độ đấu thầu.
  2. **Phạm Minh Tuấn (Kỹ sư QS Lead):** Supporter. Quản lý đội bóc tách, ủng hộ có điều kiện (yêu cầu kiểm soát HITL).
  3. **Đỗ Thị Hương (Kỹ sư QS thâm niên):** Blocker. Quen bóc tay AutoCAD 10 năm, nghi ngại AI sai số và e ngại mất việc.
  4. **Lê Hoàng Nam (Kỹ sư QS trẻ):** Champion cấp cơ sở. Hào hứng công nghệ, muốn AI giải phóng khỏi overtime đo nét vẽ.
  5. **Vũ Đức Trọng (Kỹ sư Hiện trường & MEP):** Bystander. Quan tâm kiểm tra xung đột dầm giật cấp và hộp kỹ thuật.
  6. **Nguyễn Thị Mai (Kỹ sư Đấu thầu gấp):** Supporter. Áp lực nộp thầu 48h, cần xuất nhanh bảng BOQ sơ bộ.
  7. **Trần Quốc Bảo (Kiểm soát chi phí & Thẩm tra):** Blocker/Gatekeeper. Khắt khe, yêu cầu Deep Link audit trail trỏ về nét vẽ CAD.
* **4 Stakeholder ưu tiên & Hành động 1–2 tuần:**
  * **Trần Đình Đông (Champion — Chủ nhà thầu):** Trình bày demo Dashboard đa dự án trước 16h thứ Năm; đề xuất thí điểm Shadow Run 3 tuần.
  * **Nguyễn Thị Mai (Supporter — Kỹ sư Đấu thầu):** Cài tài khoản thử nghiệm trước thứ Ba; cùng Mai bóc tách thử 1 gói thầu gấp vào thứ Tư.
  * **Đỗ Thị Hương (Blocker — Kỹ sư QS thâm niên):** Làm việc trực tiếp 1-1 vào thứ Sáu; hướng dẫn công cụ kéo chỉnh polygon thủ công để hóa giải tâm lý e ngại.
  * **Trần Quốc Bảo (Blocker — Kiểm soát chi phí):** Trình diễn tính năng "Deep Link Audit Trail" và báo cáo sai số $\le 1.4\%$ vào thứ Hai.

### Trang 2 — Pitch & RACI Matrix
* **Pitch "Conclusion First" (Gửi Trần Đình Đông — Chủ nhà thầu):** Đề xuất phê duyệt Shadow Run 3 tuần cho đội ngũ 6 kỹ sư trên 2 dự án (Sky Garden & Lotus Tower) từ 01/11, cắt giảm 80% thời gian bóc tách từ 24h xuống 3h/tầng, loại bỏ thất thoát 5–7% vật tư sơn, kiểm soát sai số $1.4\%$. Small Ask: Workshop 45 phút chiều thứ Sáu chạy thử cùng 6 kỹ sư.
* **Phản biện chí mạng & Cách xử lý:**
  * *Phản biện:* Bản vẽ CAD thực tế lộn xộn, nhiều nét hở; nếu AI làm sai hoặc 6 kỹ sư không dùng thì lãng phí tiền đầu tư.
  * *Xử lý bằng chứng:* Giải thuật Shapely tự vá khe hở $50$mm, AI Verification Center cảnh báo 31+ lỗi; nguyên tắc Human-in-the-loop bắt buộc kỹ sư duyệt từng phòng.
* **RACI Matrix:** 6 công việc trọng yếu, đảm bảo **mỗi hàng chỉ có duy nhất 1 Accountable (A)**:
  1. Khảo sát luồng làm việc & TCVN của 6 kỹ sư: **Tô Anh Đức (A)**, Duy Thành (R)
  2. Thuật toán Bóc tách CAD & Dashboard Dự án: **Phương Nam (A/R)**, Duy Thành (R)
  3. Bộ Golden CAD Benchmark (20 bản vẽ): **Gia Khánh (A)**, Duy Thành (R)
  4. Kiểm thử Sai số & Đào tạo 6 Kỹ sư: **Gia Khánh (A)**, Duy Thành (R), 6 Kỹ sư (R)
  5. Thử nghiệm Shadow Run trên 2 dự án: **Tô Anh Đức (A)**, Duy Thành (R), 6 Kỹ sư (R)
  6. Quyết định Áp dụng Toàn Doanh nghiệp & Ký HĐ: **Trần Đình Đông (A)**, Tô Anh Đức (R)

### Trang 3 — AI Team Design
* **Cấu trúc đã chọn:** **Embedded AI Team** — phù hợp tinh gọn cho nhóm 4 người làm việc trực tiếp với đội ngũ 6 kỹ sư dự toán, feedback loop $< 24$h.
* **Core Roles (4 thành viên):** AI Product Manager (Tô Anh Đức), Tech Lead & CAD Geometry Engineer (Phương Nam), AI Evaluation Lead (Gia Khánh), Product Ops & CAD Pipeline Specialist (Duy Thành).
* **Priority Resourcing:**
  * *Domain Định mức Xây dựng & TCVN:* **Partner** với Kỹ sư QS trưởng Phạm Minh Tuấn — chi phí 0đ, độ sát thực hiện trường 100%.
  * *Hệ thống Đo lường Sai số Bóc tách CAD Tự động:* **Internal Upskilling** cho Gia Khánh (L1 $\rightarrow$ L2) xây dựng bộ Golden CAD Test Suite 20 bản vẽ.
  * *Chuyển đổi DWG sang DXF:* **Outsource / Tooling Partner** (Tích hợp ODA File Converter SDK chạy headless với Xvfb).
* **Squad Goal:** *"Team H3201 của chúng tôi sở hữu module AI CAD Extraction & Paint Estimator (ENGENIX) và chịu trách nhiệm đưa thời gian bóc tách dự toán sơn của đội ngũ 6 kỹ sư từ 24 giờ xuống dưới 4 giờ/tầng với sai số khối lượng bóc tách $\le \pm 3\%$ và tỷ lệ phát hiện lỗi bản vẽ $\ge 95\%$ trong vòng 60 ngày tới."*

### Trang 4 — Team Health & Growth Plan
* **Team Health Score (1–5):** Chất lượng AI (3.13) | Tiến độ (4.25) | Tinh thần (4.63) | Tốc độ sản phẩm (3.25). Nút thắt lớn nhất là kiểm tra chất lượng bóc tách CAD thủ công bằng mắt làm chậm nhịp release.
* **Nâng cấp Competency:** Phùng Gia Khánh (AI Evaluation Lead) từ **L1 (AI Literate)** lên **L2 (AI Practitioner)** ở mảng *Automated CAD Geometry Evals & Quantity Takeoff Benchmarking*.
* **Growth Plan 30 ngày (3 hành động cụ thể):**
  1. *Chất lượng AI:* Xây dựng bộ Golden CAD Test Suite gồm 20 mặt bằng thực tế và script tự động tính sai số khối lượng $\le \pm 3\%$ trước mỗi commit (Gia Khánh — Hạn: Ngày 14 / 27-10).
  2. *Tốc độ sản phẩm:* Xây dựng module tự động vá lỗi hình học (Auto-snap geometry & gap filling $\le 50$mm), giảm 80% cảnh báo giả cho kỹ sư (Phương Nam — Hạn: Ngày 21 / 03-11).
  3. *Lệch nhịp người dùng:* Tổ chức phiên làm việc định kỳ hàng tuần 30 phút "Thứ Sáu cùng Đội ngũ Kỹ sư Dự toán" với Kỹ sư Tuấn và 5 kỹ sư để đối chiếu kết quả bóc tách thực tế (Tô Anh Đức — Hạn: Thứ Sáu hàng tuần).

---

## 🏆 Bảng Đối Soát 6 Cổng Đánh Giá (Gate Rubric Verification)

| Cổng kiểm tra (Gate) | Tiêu chí đạt | Kết quả nhóm H3201 (Dự án ENGENIX) | Trạng thái |
| :--- | :--- | :--- | :---: |
| **Gate 0: Scope** | Cùng 1 dự án, 1 mục tiêu đo được, 1 owner tổng hợp rõ ràng. | Dự án AI bóc tách bản vẽ & dự toán sơn (P-059), mục tiêu pilot 2 dự án của nhà thầu, Phương Nam phụ trách repo. | ✅ **ĐẠT (PASS)** |
| **Gate 1: Stakeholder** | $\ge 6$ stakeholder cụ thể, map 2x2, có stance thực tế, 4 hành động cụ thể. | 7 stakeholder cụ thể (1 Chủ nhà thầu Trần Đình Đông + 6 Kỹ sư với các góc nhìn phân hóa), 4 action có deadline. | ✅ **ĐẠT (PASS)** |
| **Gate 2: Pitch & RACI** | Pitch Conclusion First + Evidence + Small Ask; 1 phản biện + xử lý; RACI có 1 A/hàng. | Pitch Chủ thầu Trần Đình Đông (Shadow Run cho 6 kỹ sư, sai số 1.4%), RACI 6 việc đúng 1 A. | ✅ **ĐẠT (PASS)** |
| **Gate 3: AI Team** | Architecture có lý do; Core roles phù hợp; Resourcing Hire/Outsource/Partner; Squad goal chuẩn. | Embedded model; 4 core roles; resourced qua Partner (QS Lead) & Internal Upskilling; Squad goal định lượng chuẩn. | ✅ **ĐẠT (PASS)** |
| **Gate 4: Team Health** | Đủ 4 khía cạnh; vấn đề ưu tiên; Competency L1 $\rightarrow$ L2; 3 action có Owner + Deadline + Pass signal. | Đánh giá 4 khía cạnh; nâng cấp Gia Khánh L1 $\rightarrow$ L2 mảng CAD Evals; 3 action cụ thể có pass signal định lượng. | ✅ **ĐẠT (PASS)** |
| **Gate 5: Nộp bài** | Repo chuẩn cấu trúc, README đầy đủ, tệp PDF chính xác $\le 4$ trang. | Repo đúng format `Track1_Day25_H3201_Engenix`, README hoàn chỉnh, PDF đúng 4 trang không tràn dòng. | ✅ **ĐẠT (PASS)** |
