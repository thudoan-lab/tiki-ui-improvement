# AI Usage Log

## 1. Công cụ AI
| Công cụ | Dùng cho |
| --- | --- |
| ChatGPT | Nhiệm vụ 2: phân tích 5 khu vực của website Tiki |
| Gemini | Nhiệm vụ 3: đề xuất phương án giao diện và tạo mã nguồn HTML/CSS ban đầu |
| Claude | Hỗ trợ tham khảo ý tưởng, giải thích mã nguồn, đề xuất và hỗ trợ chỉnh sửa giao diện trong quá trình thực hiện.

## 2. Mục đích sử dụng
- Lập khung phân tích giao diện cho 5 khu vực: trang chủ, danh mục, chi tiết sản phẩm, tìm kiếm, giỏ hàng.
- Hỗ trợ phân tích chức năng, bố cục, ưu điểm và hạn chế của 5 khu vực trên website Tiki.
- Tham khảo các phương án cải tiến giao diện thẻ sản phẩm, tập trung vào cách hiển thị màu sắc, dung lượng và thông tin giá.
- Hỗ trợ tạo và chỉnh sửa mã nguồn HTML5, CSS3 cho giao diện mẫu.
- Hỗ trợ giải thích các thành phần HTML/CSS và gợi ý cách kiểm tra giao diện trên máy tính, điện thoại.

## 3. Prompt đã sử dụng

**Prompt 1 – Phân tích website (ChatGPT)**
> Bạn là chuyên gia phân tích nghiệp vụ và thiết kế trải nghiệm người dùng cho website thương mại điện tử. Tôi đang khảo sát website Tiki: https://tiki.vn/. Hãy lập bảng phân tích 5 khu vực: trang chủ, danh mục sản phẩm, chi tiết sản phẩm, tìm kiếm và giỏ hàng. Với mỗi khu vực, hãy nêu mục đích chức năng, thành phần giao diện cần có, điểm thuận tiện đối với khách hàng, một vấn đề có thể phát sinh và một đề xuất cải tiến. Không khẳng định những tính năng chưa được kiểm chứng. Phân biệt rõ nhận xét dựa trên quan sát và đề xuất của AI.

**Prompt 2 – Đề xuất giao diện (Gemini)**
> Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử bằng HTML5 và CSS3. Tôi muốn cải tiến khu vực: thẻ sản phẩm trong trang kết quả tìm kiếm "iphone" trên Tiki. Hiện thẻ chỉ ghi "2 Màu" mà không ghi màu gì, không ghi dung lượng, nên khách phải bấm vào từng sản phẩm mới biết. Đối tượng sử dụng: khách hàng mua sắm trực tuyến tại Việt Nam. Hãy đề xuất: 1. Bố cục giao diện. 2. Các thành phần HTML cần sử dụng. 3. Cách tổ chức CSS. 4. Cách hiển thị trên máy tính và điện thoại. 5. Những điểm cần kiểm tra về khả năng sử dụng. Trước tiên, hãy giải thích phương án thiết kế. Chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu.

**Prompt 3 – Tạo mã nguồn (Gemini)**
> Dựa trên phương án đã thống nhất, hãy tạo một trang giao diện thương mại điện tử bằng HTML5 và CSS3. Yêu cầu: giao diện có tiêu đề và khu vực sản phẩm; có tối thiểu 4 sản phẩm mẫu; mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác; bố cục phù hợp với màn hình máy tính và điện thoại; mã HTML có cấu trúc rõ ràng; CSS được tách thành file riêng; không sử dụng backend hoặc cơ sở dữ liệu; không đưa thư viện hoặc thành phần không cần thiết vào dự án. Giải thích cách chạy trang web và những phần tôi cần kiểm tra.

## 4. Kết quả AI đề xuất
- **ChatGPT:** bảng phân tích 5 khu vực, tách riêng nhận xét và đề xuất. Nội dung còn chung chung, có một số nhận xét chưa đúng với Tiki (xem mục 5).
- **Gemini:** trang `index.html` và `css/styles.css` gồm header có ô tìm kiếm, lưới 4 thẻ sản phẩm (2 cột trên điện thoại, 3 cột trên máy tính bảng, 4 cột trên máy tính). Mỗi thẻ có nút màu (chấm tròn + tên màu), ô dung lượng, tên, sao, số đã bán, giá khuyến mãi, giá gốc gạch ngang và nút "Chọn mua". Ảnh dùng ảnh giữ chỗ từ placehold.co.

## 5. Kiểm tra và điều chỉnh
**Đối chiếu kết quả ChatGPT với Tiki:**
- Loại bỏ nhận xét "trang chi tiết khó thấy chính sách đổi trả, thời gian giao": thực tế nhãn "30 ngày đổi trả" nằm cạnh tên sản phẩm, thông tin giao hàng nằm ngay dưới giá.
- Loại bỏ đề xuất bổ sung bộ lọc thương hiệu, đánh giá, thuộc tính: Tiki đã có sẵn.
- Loại bỏ nhận định tìm kiếm không xử lý được lỗi chính tả: gõ "iphon", "tai nge" vẫn ra kết quả đúng.

**Chỉnh sửa mã nguồn của Gemini** (mỗi lần sửa có một commit riêng):
1. `Move product name above variant options` – đưa thẻ `h2` (tên sản phẩm) lên ngay dưới ảnh ở cả 4 thẻ. Lý do: ở bản ban đầu tên nằm dưới các nút màu và dung lượng; sản phẩm nhiều màu thì tên bị đẩy xuống giữa thẻ, tên các thẻ cùng hàng không thẳng nhau.
2. `Add local product images for each card` – thay ảnh giữ chỗ từ placehold.co bằng 4 ảnh minh hoạ trong thư mục `images/`, màu đúng với lựa chọn màu mặc định của từng thẻ. Lý do: ảnh cũ chỉ là ô xám có chữ và phụ thuộc mạng ngoài. Ảnh minh hoạ được vẽ riêng để tránh dùng ảnh có bản quyền.

Đã kiểm tra trên Chrome (DevTools) ở kích thước máy tính và điện thoại: trang mở được, ảnh và nội dung hiển thị đủ, không bị tràn ngang, nút "Chọn mua" của các thẻ thẳng hàng.

## 6. Phần hiểu và có thể giải thích
- `display: grid` + `grid-template-columns: repeat(2, 1fr)`: chia lưới sản phẩm thành 2 cột bằng nhau trên điện thoại.
- `@media (min-width: 768px)` và `@media (min-width: 1024px)`: khi màn hình rộng hơn thì đổi lưới sang 3 cột rồi 4 cột (viết theo kiểu mobile-first).
- `display: flex; flex-direction: column` của `.product-card__body`: các phần trong thẻ xếp từ trên xuống theo đúng thứ tự viết trong HTML, nên đưa `h2` lên trước thì tên hiện ngay dưới ảnh.
- `margin-top: auto` của `.product-card__footer`: đẩy khối giá và nút xuống đáy thẻ, nên nút "Chọn mua" của các thẻ luôn thẳng hàng.
- Thẻ `<del>` cho giá gốc gạch ngang, thẻ `<ins>` cho giá khuyến mãi.
- Thuộc tính `src` của `<img>` dùng đường dẫn tương đối `images/...` để ảnh chạy được cả trên máy lẫn trên GitHub Pages; `alt` ghi tên sản phẩm để vẫn biết là máy gì khi ảnh lỗi.
