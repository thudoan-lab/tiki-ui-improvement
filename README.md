# Tiki UI Improvement

## 1. Giới thiệu
Bài tập cá nhân Chương 1 – môn Phát triển ứng dụng WEB/TMĐT.

Sau khi khảo sát website Tiki, tôi chọn cải tiến **thẻ sản phẩm trong trang kết quả tìm kiếm "iphone"**. Trên Tiki, thẻ sản phẩm chỉ ghi số lượng màu (ví dụ "2 Màu") mà không ghi đó là màu gì, cũng không ghi dung lượng, nên người mua phải bấm vào từng sản phẩm mới biết. Trang này thiết kế lại thẻ sản phẩm để người mua thấy ngay màu sắc, dung lượng và giá trên danh sách.

## 2. Website tham khảo
- Tên website: Tiki
- URL: https://tiki.vn/
- Khu vực đã khảo sát: Trang chủ, Danh mục sản phẩm, Chi tiết sản phẩm, Tìm kiếm, Giỏ hàng

## 3. Chức năng
- Header có logo và ô tìm kiếm, tiêu đề "Kết quả tìm kiếm cho "iphone"".
- Hiển thị 4 sản phẩm mẫu: iPhone 16 Pro Max, iPhone 16, iPhone 15, iPhone 13.
- Mỗi thẻ sản phẩm gồm:
  - Ảnh sản phẩm và nhãn (Chính hãng / Freeship / Giá tốt)
  - Tên sản phẩm (tối đa 2 dòng)
  - Màu sắc: chấm tròn đúng màu kèm tên màu
  - Dung lượng: các ô 128GB / 256GB / 512GB / 1TB
  - Đánh giá sao và số lượng đã bán
  - Giá khuyến mãi, nhãn % giảm và giá gốc gạch ngang
  - Nút "Chọn mua"
- Bố cục thay đổi theo màn hình: điện thoại 2 cột, máy tính bảng 3 cột, máy tính 4 cột.

## 4. Công nghệ
- HTML5
- CSS3 (Flexbox, CSS Grid, Media Query, CSS Variables)

## 5. Cách chạy
- Cách 1: mở file `index.html` bằng trình duyệt.
- Cách 2: xem bản online tại GitHub Pages: https://thudoan-lab.github.io/tiki-ui-improvement/

Cấu trúc thư mục:
```
tiki-ui-improvement/
├── index.html
├── css/
│   └── styles.css
├── images/
│   ├── iphone-16-pro-max.svg
│   ├── iphone-16.svg
│   ├── iphone-15.svg
│   └── iphone-13.svg
├── README.md
└── AI_USAGE.md
```

## 6. Cải tiến đã thực hiện
**So với Tiki:**
- Thay dòng "2 Màu" bằng chấm tròn màu kèm tên màu (ví dụ: Sa Mạc, Tự Nhiên, Đen, Trắng).
- Hiển thị rõ các dung lượng có bán ngay trên thẻ.
- Hiển thị giá gốc gạch ngang cạnh giá khuyến mãi và nhãn % giảm.

**Điều chỉnh sau khi kiểm tra bản AI tạo ra:**
- Đưa tên sản phẩm lên ngay dưới ảnh, trước phần màu và dung lượng. Ở bản ban đầu tên nằm dưới các nút lựa chọn nên bị đẩy xuống giữa thẻ, khó đọc và khó so sánh.
- Thay ảnh giữ chỗ lấy từ placehold.co bằng ảnh sản phẩm lưu trong thư mục `images/`, để ảnh luôn hiển thị mà không phụ thuộc mạng ngoài.

## 7. Hỗ trợ từ AI
Tôi có sử dụng AI (ChatGPT, Gemini, Claude) để hỗ trợ phân tích website, đề xuất phương án giao diện, tạo mã nguồn ban đầu, kiểm tra và chỉnh sửa. Tôi đã đối chiếu kết quả với website Tiki thật, chạy thử trang trên máy tính và điện thoại, và quyết định các điểm cần điều chỉnh. Chi tiết xem file `AI_USAGE.md`.
