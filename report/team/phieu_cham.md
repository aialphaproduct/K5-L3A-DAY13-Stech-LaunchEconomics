# Chấm điểm nhóm Stech — Lab 13 (L3A · Day 13 · Launch Economics)

- **Form:** Form chấm điểm LAB L3A – Day 13 – H201
- **Đội được chấm:** Stech
- **Đội chấm:** HaiVaKhiem
- **Repo:** https://github.com/aialphaproduct/K5-L3A-DAY13-Stech-LaunchEconomics
- **Bản được chấm:** commit `4da8720` (merge PR #15, 21/11/2026 16:59). Chấm lúc 17:21.

## Điểm theo form

| # | Tiêu chí | Điểm (1–5) |
|---|---|:---:|
| 1 | Mức độ đáp ứng yêu cầu đề: đủ các phần, đúng cấu trúc và định dạng | **4** |
| 2 | Độ chính xác về số liệu, kết quả, lập luận đúng và tính nhất quán | **4** |
| 3 | Chiều sâu phân tích: có insight, giải thích được "tại sao" | **4** |
| 4 | Tính rõ ràng giúp người đọc hiểu được thông điệp chính | **4** |
| 5 | Kết luận và đề xuất: rõ ràng, hành động cụ thể, khả thi | **4** |
| | **Tổng** | **20 / 25** |

---

## 1. Đáp ứng yêu cầu đề: 4/5

**Đạt**
- Đủ sáu file hồ sơ, đúng tên, đúng chỗ (`report/team/`).
- `pilot_plan.yaml` đọc được bằng `yaml.safe_load`. Ngoài dòng chú thích không còn dấu `?`. Đủ các trường (`identifiability`, `interim_looks`, `simulated_inputs`…). Ba luật dừng, cả ba có đủ bốn vế NẾU – TRONG – THÌ – KHÔNG THÌ.
- `ho_so_launch_v0.md` vừa một trang, đủ bảy mục. Mỗi mục có con số, trạng thái và người phụ trách là một vai trò. Dòng cuối là đề xuất "Go có điều kiện".
- Không có từ "production". Không sửa hai file CSV và `lab13_starter.py`.

**Thiếu / lỗi**
- **`src/lab13.py` dừng lỗi ở cuối:** dòng 165 gọi `tinh_co_mau_cp4(reqs)` bên trong khối `if __name__ == '__main__':`, nhưng hai hàm `co_mau_hai_ti_le` và `tinh_co_mau_cp4` lại được định nghĩa *sau* khối đó (dòng 169, 181). Chạy `python3 lab13.py` sẽ in xong phần A và B rồi báo `NameError`, nên phần D1 không bao giờ được in ra. Checklist nộp bài yêu cầu file "chạy hết". *(Mình không chạy code tải về mà xác định lỗi bằng cách đọc code và chạy thử một file mẫu tự viết có cùng cấu trúc.)*
- Code không có phần A4 (chi phí cố định).
- `phieu_cham.md` và `group_report.md` vẫn là mẫu trống.
- Thiếu báo cáo cá nhân của trưởng nhóm Lưu Thanh Mỹ. Trong `TEAM.md`, mục "Đóng góp cụ thể" của Mỹ, Hạnh và Đức còn trống.

## 2. Độ chính xác và nhất quán: 4/5

**Số liệu: khớp đáp án, không lệch.** Mình tự tính lại các số chính và đều trùng với số của nhóm:

| Hạng mục | Số của nhóm | Tự tính lại |
|---|---|---|
| A2 chi phí mỗi việc thành công | 4.472 đ; gấp 16,3× hoá đơn 274,7 đ | 4.472 đ; gấp 16,28× |
| A3 (4 loại) | 2.696 / 8.221 / 22.515 / 10.215 | khớp |
| B3 cả hệ thống (1/2/3 lần) | 7.449.781 / **6.901.220** / 7.037.585 | khớp |
| B4 xem lại 100% | 11.743 đ = 0,98× | 948 ca có lần chạy ok, 48 ca làm lại, token và tool 224.513 đ, 900 việc thành công → 11.743 đ |
| E1 ba chỉ số | 994/1.200 · 48/177 · 51/1.200 | khớp |
| D1 | 1.251 · 3.103 · 859 · m ≥ 299 | khớp |
| Mở lại 7 ngày trong phạm vi; tỉ lệ làm lại | 39/982; 4,9% | khớp |

Phần C: nhãn thống nhất trùng đáp án **20/20**.

**Điểm trừ**
- **Code và bảng không khớp ở B4.** Code ra 11.679 đ vì tính xem lại cho cả 982 ca và chia cho 934 (= 982 − 48, tức coi mọi ca không phải làm lại là thành công). Hai chỗ sai này bù trừ cho nhau. Nhóm có ghi rõ chỗ lệch 0,55% trong bảng, nhưng code vẫn chưa được sửa.
- **Một số con số trong hồ sơ không do `lab13.py` tính ra:** 93.804 đ, 274,7 đ, tỉ lệ thành công và số lần chạy trong A3, tỉ lệ ok theo từng lần thử của quoc_te, 5.865 đ/yêu cầu, và cả A4. Theo RULES, số phải do `lab13.py` tính hoặc tính tay có ghi cách tính. Các số này hiện đến từ script riêng của người kiểm số hoặc từ tài liệu hướng dẫn.
- **Quy trình gắn nhãn chưa độc lập.** `bang_loi.md` và báo cáo của Đức tự ghi rằng bộ nhãn 1 "được điền từ bộ đề xuất có AI hỗ trợ" và "không xác nhận đã diễn ra phiên gắn nhãn cá nhân 8 phút". RULES cấm dùng AI để tạo nhãn lỗi và yêu cầu hai người gắn độc lập. Hai bộ nhãn trùng nhau 100% và trùng đáp án 100%, trong khi đáp án nằm sẵn trong `docs/`. Nhóm trung thực khi tự khai, nhưng con số "đồng thuận 100%" không có giá trị đo lường.

## 3. Chiều sâu phân tích: 4/5

**Mạnh**
- Giải thích được vì sao chi phí gấp 16,3× hoá đơn token: giờ nhân viên chiếm 92,5% tổng chi phí.
- Chứng minh chạy lại không giúp quoc_te bằng tỉ lệ ok theo từng lần thử: 30% → 11,4% → 2,2%.
- B3 chỉ ra giới hạn rẻ nhất cho công ty (2 lần) khác với giới hạn cho chi phí mỗi việc thành công thấp nhất (1 lần), vì giới hạn 1 lần đẩy thêm 85 ca sang nhân viên.
- B4 tính mức hoà vốn: mỗi lần xem lại phải dưới 5,1 phút, hoặc dưới 4,8 phút nếu làm lại mất 15,3 phút. Nhóm cũng phân tích chi phí cố định tăng mạnh khi khối lượng nhỏ.
- Nhóm chấp nhận và ghi rõ đánh đổi: nâng mức chênh lên 6 điểm, và nếu tác động thật chỉ là 5 điểm thì power chỉ còn khoảng 0,64.
- Có phần tự làm thêm: Hạnh phát hiện lỗi A3 trong code nhờ kiểm số độc lập. Đức làm rõ mẫu số và cohort cho từng cách phát hiện lỗi trong bảng khắc phục.

**Hạn chế**
- Phần lớn câu chữ và insight gần như trùng nguyên văn bài mẫu trong tài liệu hướng dẫn: các luật dừng, phần D2, bảng event, bảng rủi ro E2. Nhóm hiểu và dẫn lại đúng, nhưng ít phân tích riêng gắn với bối cảnh LogiX.

## 4. Tính rõ ràng: 4/5

**Mạnh:** hồ sơ một trang dễ đọc, số in đậm, nhãn `[simulated]` gắn nhất quán. `bang_chi_phi.md` có cột "cách tính" cho từng kịch bản. `chi_so.md` có phần đối chiếu từng chỉ số với event dùng để tính.

**Hạn chế:**
- Mục 1 và mục 3 của hồ sơ nhồi 3–4 con số vào một ô (4.472 toàn mẫu, 4.599 trong phạm vi có cộng cố định, 5.784 ở nửa khối lượng, 5.865 cả hệ thống). Người đọc khó biết đâu là con số chính để so với 12.000 đ.
- `group_report.md` trống nên thiếu một bản tóm tắt cho người đọc từ ngoài nhóm.

## 5. Kết luận và đề xuất: 4/5

**Mạnh:** đề xuất "Go có điều kiện", phạm vi chỉ gồm noi_dia và hang_nang với lý do bằng số (0,22× và 0,69×, loại 1,88× và 0,85×). Ba điều kiện đều có người phụ trách. Đề xuất nêu cả những con số bất lợi: power 0,64, và xem lại 100% đẩy chi phí lên 0,98–1,03×.

**Chỗ cần sửa:**
- **Hồ sơ và pilot plan mâu thuẫn về giới hạn chạy lại.** Điều kiện 2 trong hồ sơ đặt giới hạn 2 lần chạy *ngay từ đầu*. Trong `pilot_plan.yaml`, giới hạn 2 lần chỉ là phương án dự phòng khi chi phí vượt 8.000 đ. Ngoài ra, mọi con số chi phí trong hồ sơ đều tính ở mức 3 lần chạy.
- **Luật dừng chi phí có thể kích hoạt ngay.** Nếu những tuần đầu pilot phải xem lại 100%, chi phí mỗi việc thành công là 11.743 đ, vượt ngưỡng 8.000 đ. Như vậy luật dừng 2 sẽ kích hoạt sau 2 tuần. Pilot plan chưa nói tỉ lệ xem lại ban đầu là bao nhiêu.
- **Không ghi ngày bắt đầu pilot.** Có ngày quyết định (2027-01-05) nhưng không có ngày bắt đầu, nên không kiểm được pilot có đủ thời gian để mỗi nhân viên đạt m ≥ 299 yêu cầu hay không. Ước tính: khoảng 30 yêu cầu trong phạm vi mỗi nhân viên mỗi ngày, cần khoảng 10 ngày làm việc ở bước 0.50.
- **Luật dừng an toàn gộp sai loại sự cố.** Luật 1 gộp "≥ 1 ca hoàn trùng" chung với "TRONG 3 ngày liên tiếp". Hoàn tiền trùng nên dừng ngay khi xảy ra, không chờ 3 ngày.
- **Thiếu hai điều kiện quan trọng:** (a) thay phút simulated bằng phút đo thật sau tuần 1, trong khi toàn bộ luận điểm chi phí dựa trên số giả lập; (b) kế hoạch *giảm* tỉ lệ xem lại theo bậc, hiện chỉ có "theo dõi".
- Điều kiện 1 và 2 có hạn kiểm tra là "trước ngày mở rollout 0.10", chưa phải một ngày cụ thể. Điều kiện 3 gộp ba việc khác nhau vào một dòng.

---

## Ô 6 — Ý kiến đóng góp (bản để dán vào form)

> Điểm mạnh: số liệu A–E đều khớp đáp án (A2 4.472 đ, gấp 16,3×; B3: giới hạn 2 lần rẻ nhất, 6.901.220 đ; B4 11.743 đ = 0,98×; D1 1.251/859/m ≥ 299; E1 82,83%/27,12%/4,25%). Nhãn `simulated` gắn nhất quán. Phạm vi pilot được thu hẹp có lý do bằng số. Đề xuất Go có điều kiện có nêu các con số bất lợi (power 0,64; xem lại 100% lên 0,98–1,03×). Hồ sơ một trang rõ ràng.
> Cần sửa trước 23:59: (1) lab13.py gọi tinh_co_mau_cp4 trước khi định nghĩa hàm nên báo NameError, D1 không in ra; cần chuyển hai hàm CP4 lên trên khối `if __name__ == '__main__'`, bổ sung A4 và sửa B4 trong code (948 ca được xem lại, chia 900). (2) phieu_cham.md và group_report.md còn trống; thiếu báo cáo cá nhân của Mỹ; TEAM.md còn trống phần đóng góp. (3) Hồ sơ đặt giới hạn 2 lần chạy từ đầu, còn pilot_plan chỉ dùng khi chi phí vượt 8.000 đ, cần thống nhất. (4) Nếu tuần đầu xem lại 100% thì chi phí 11.743 đ vượt ngưỡng 8.000 đ, luật dừng 2 sẽ kích hoạt; cần ghi rõ tỉ lệ xem lại ban đầu và ngày bắt đầu pilot. (5) Hoàn tiền trùng nên dừng ngay, không chờ 3 ngày. (6) Bộ nhãn 1 dùng AI và không gắn độc lập là trái RULES; nên gắn lại độc lập hoặc ghi rõ hạn chế này trong hồ sơ.
> Câu hỏi cho đội: "Nếu 2 tuần đầu phải xem lại 100% (11.743 đ/việc), luật dừng chi phí 8.000 đ có làm pilot thu hẹp về noi_dia ngay không, và nhóm xử lý thế nào?"

---

## Tham chiếu nhanh: rubric chính thức của repo (để đối chiếu, không thuộc form)

Đây là ước tính phần 70 điểm trợ giảng chấm theo `RUBRIC.md`:

- **C1 (20):** khoảng 18–20. A1 đạt, A2 và A3 khớp, nhưng script dừng lỗi ở cuối.
- **C2 (15):** khoảng 15.
- **C3 (10):** số đạt, nhưng có rủi ro bị trừ vì vi phạm quy định gắn nhãn độc lập.
- **C4 (15):** khoảng 14–15. Số D1 đúng, nhưng code tính D1 không chạy được.
- **C5 (10):** khoảng 10.

Phần 30 điểm hội đồng (C6–C8) do nhóm chấm chéo quyết định.
