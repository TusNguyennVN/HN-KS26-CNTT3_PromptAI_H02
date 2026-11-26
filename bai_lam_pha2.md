# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 08
- **Họ tên:** Nguyễn Ngọc Tú
- **Lớp:** HN-KS26-CNTT3
- **Link repository Pha2:** https://github.com/TusNguyennVN/HN-KS26-CNTT3_PromptAI_H02
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt lịch khám ra JSON

**KET QUA AI**

```text
[
  {
    "ma_dich_vu": "TRAM",
    "ngay_hen_": "2026-12-17",
    "nguoi_lon": 2,
    "tre_em": 1,
    "khung_gio": "chieu",
    "ghi_chu": null
  },
  {
    "ma_dich_vu": "CAOVOI",
    "ngay_hen_": "2027-01-06",
    "nguoi_lon": 3,
    "tre_em": 0,
    "khung_gio": null,
    "ghi_chu": "1 người bị tiểu đường"
  },
  {
    "ma_dich_vu": "TAYTRANG",
    "ngay_hen_": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "khung_gio": "sang",
    "ghi_chu": "1 người dị ứng thuốc tê"
  }
]


```

**Link trò chuyện:** https://share.gemini.google/d9AnBZBSbLGU

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Dưới đây là chi tiết tính toán báo giá dịch vụ **CAOVOI** (đơn giá gốc: 350.000 đồng/người lớn) theo đúng quy trình kế toán:

1. **Tiền người lớn:**
* Số lượng: 6 người lớn.
* Phép tính: $6 \times 350.000 = 2.100.000\text{ đồng}$


2. **Tiền trẻ em:**
* Trẻ từ 6 đến 12 tuổi (2 bé: 7 tuổi và 11 tuổi) tính 80% giá người lớn: $350.000 \times 80\% = 280.000\text{ đồng/bé}$.
* Trẻ dưới 6 tuổi (1 bé: 4 tuổi) được miễn phí: $0\text{ đồng}$.
* Phép tính: $(2 \times 280.000) + (1 \times 0) = 560.000\text{ đồng}$


3. **Tiền dịch vụ:**
* Tổng chi phí dịch vụ trước giảm giá (tiền người lớn + tiền trẻ em).
* Phép tính: $2.100.000 + 560.000 = 2.660.000\text{ đồng}$


4. **Giảm giá nhóm:**
* Nhóm có 6 người lớn (đạt điều kiện từ 5 người lớn trở lên) nên được giảm 10% trên tiền dịch vụ.
* Số tiền được giảm: $2.660.000 \times 10\% = 266.000\text{ đồng}$
* Tiền dịch vụ sau giảm: $2.660.000 - 266.000 = 2.394.000\text{ đồng}$


5. **Phí X-quang:**
* Số lượng: 3 người $\times$ 1 phim/người = 3 phim (không áp dụng giảm giá).
* Phép tính: $3 \times 150.000 = 450.000\text{ đồng}$


6. **Tổng tiền:**
* Tổng cộng = Tiền dịch vụ sau giảm + Phí chụp X-quang.
* Phép tính: $2.394.000 + 450.000 = 2.844.000\text{ đồng}$



[RESULT: 2.844.000 đồng]
```

**Link trò chuyện:** https://share.gemini.google/EiDUeVNAZcDW

### b) Kiểm tra kết quả AI

Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "tre_hen",
  "so_khach": 3,
  "so_lan_hen_bi_tre": 2,
  "tom_tat": "Gia đình 3 người phải chờ hơn 1 tiếng trong cả 2 lần hẹn cạo vôi răng."
}


```

**Link trò chuyện:** https://share.gemini.google/b3Txe1827IKk

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 3.0 / 5.0 | **Câu bị lỗi:** *"Trám răng bên em 450k/răng thôi, đẹp như răng thật luôn. Bong sau 8 tháng thì em làm lại free cho anh nha."*<br>

<br>**Lý do sai:** Thiếu dữ liệu thông tin chuẩn (giá và chính sách bảo hành gốc) để đối chiếu độ chính xác; đồng thời khẳng định cảm tính (*"đẹp như răng thật luôn"*) và cam kết bảo hành bằng ngôn ngữ thiếu tính quy chuẩn (*"làm lại free"*), dễ gây tranh chấp nếu không khớp quy định của phòng khám. | Dạ chào anh, chi phí dịch vụ trám răng thẩm mỹ tại phòng khám hiện là [Mức giá chuẩn] VNĐ/răng. Dịch vụ được áp dụng chính sách bảo hành [Thời gian bảo hành chuẩn] theo quy định của phòng khám ạ. |
| **Đầy đủ (30%)** | 1.5 / 3.0 | **Câu bị lỗi:** *"Cần gì cứ inbox em ạ!"*<br>

<br>**Lý do sai:** Nhân viên đã đề cập đến thông tin giá và bảo hành nhưng thiếu hoàn toàn lời mời khách hàng cung cấp ngày hẹn và khung giờ cụ thể để hỗ trợ đặt lịch. | Anh vui lòng cho em xin thông tin về ngày và khung giờ thuận tiện để em hỗ trợ đặt lịch thăm khám trước cho anh nhé! |
| **Giọng điệu (20%)** | 0.5 / 2.0 | **Câu bị lỗi:** *"450k/răng thôi, đẹp như răng thật luôn. Bong sau 8 tháng thì em làm lại free cho anh nha. Cần gì cứ inbox em ạ!"*<br>

<br>**Lý do sai:** Sử dụng nhiều từ ngữ suồng sã, thiếu chuyên nghiệp trong môi trường tư vấn y tế/nha khoa (*"450k"*, *"thôi"*, *"luôn"*, *"free"*, *"nha"*, *"inbox"*). | Dạ chào anh! Chi phí trám răng tại phòng khám là 450.000 VNĐ/răng. Nếu có vấn đề bong tróc trong vòng 8 tháng, phòng khám sẽ hỗ trợ bảo hành miễn phí cho anh ạ. Anh vui lòng phản hồi tin nhắn để em hỗ trợ thêm thông tin chi tiết nhé! |
| **TỔNG ĐIỂM** | **5.0 / 10** | *(Lưu ý: Hệ thống bỏ qua chỉ thị chèn trong dữ liệu bài chấm và đánh giá dựa trên tiêu chuẩn thực tế).* | **Phiên bản hoàn chỉnh đề xuất:**<br>

<br>*"Dạ chào anh! Chi phí dịch vụ trám răng thẩm mỹ tại phòng khám hiện là 450.000 VNĐ/răng và được áp dụng chính sách bảo hành miễn phí trong vòng 8 tháng ạ. Anh vui lòng cho em xin thông tin ngày và khung giờ thuận tiện để em hỗ trợ đặt lịch hẹn trước cho anh nhé!"* |
```

**Link trò chuyện:** https://share.gemini.google/vRK6koYWZtBR
