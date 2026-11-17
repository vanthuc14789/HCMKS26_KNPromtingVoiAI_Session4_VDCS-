---


---

<h1 id="báo-cáo-thiết-kế-giải-pháp-prompting-nâng-cao-logic--chuỗi"><strong>BÁO CÁO: THIẾT KẾ GIẢI PHÁP PROMPTING NÂNG CAO (LOGIC &amp; CHUỖI)</strong></h1>
<h2 id="bước-1-thiết-kế-giải-pháp-io"><strong>1. Bước 1: Thiết kế giải pháp (I/O)</strong></h2>
<p><strong>Tên giải pháp:</strong> Tự động hóa quy trình kiểm tra và xử lý đơn hàng tại cửa hàng.</p>
<p><strong>Mục tiêu:</strong> Sử dụng AI để kiểm tra thông tin đơn hàng, phát hiện lỗi và phân loại trạng thái đơn hàng.</p>
<p><strong>Input (Dữ liệu đầu vào):</strong></p>
<ul>
<li>
<p>Mã đơn hàng.</p>
</li>
<li>
<p>Tên khách hàng.</p>
</li>
<li>
<p>gi Tên sản phẩm.</p>
</li>
<li>
<p>Số lượng sản phẩm.</p>
</li>
<li>
<p>Đơn giá.</p>
</li>
<li>
<p>Địa chỉ giao hàng.</p>
</li>
<li>
<p>Số điện thoại khách hàng.</p>
</li>
</ul>
<p><strong>Output (Kết quả đầu ra):</strong></p>
<ul>
<li>
<p>Thông tin đơn hàng đã được kiểm tra.</p>
</li>
<li>
<p>Tổng tiền đơn hàng.</p>
</li>
<li>
<p>Trạng thái đơn hàng.</p>
</li>
<li>
<p>Danh sách lỗi nếu có.</p>
</li>
<li>
<p>Đề xuất cách xử lý.</p>
</li>
</ul>
<h2 id="bước-2-viết-prompt-hoàn-chỉnh"><strong>2. Bước 2: Viết Prompt hoàn chỉnh</strong></h2>
<p><strong>Prompt thực thi:</strong></p>
<h1 id="vai-trò">VAI TRÒ</h1>
<p>Bạn là nhân viên AI hỗ trợ quản lý đơn hàng cho cửa hàng.</p>
<h1 id="nhiệm-vụ">NHIỆM VỤ</h1>
<p>Kiểm tra thông tin đơn hàng và tự động phân loại trạng thái xử lý.</p>
<h1 id="quy-trình-xử-lý-prompt-chaining">QUY TRÌNH XỬ LÝ (PROMPT CHAINING)</h1>
<p><strong>Bước 1: Kiểm tra dữ liệu</strong></p>
<ul>
<li>
<p>Kiểm tra mã đơn hàng, tên khách hàng, sản phẩm và số lượng.</p>
</li>
<li>
<p>Nếu thiếu thông tin, đánh dấu “Thiếu dữ liệu”.</p>
</li>
<li>
<p>Nếu số lượng hoặc đơn giá không hợp lệ, đánh dấu “Dữ liệu sai”.</p>
</li>
</ul>
<p><strong>Bước 2: Tính toán</strong></p>
<ul>
<li>
<p>Nếu dữ liệu hợp lệ, tính tổng tiền = Số lượng × Đơn giá.</p>
</li>
<li>
<p>Kiểm tra lại kết quả tính toán.</p>
</li>
</ul>
<p><strong>Bước 3: Phân loại</strong></p>
<ul>
<li>
<p>Nếu dữ liệu đầy đủ và hợp lệ: “Hợp lệ”.</p>
</li>
<li>
<p>Nếu thiếu thông tin: “Cần bổ sung”.</p>
</li>
<li>
<p>Nếu dữ liệu sai: “Cần kiểm tra”.</p>
</li>
</ul>
<p><strong>Bước 4: Tổng hợp kết quả</strong><br>
Trả về kết quả theo đúng định dạng bên dưới.</p>
<h1 id="xử-lý-lỗi-và-đứt-gãy">XỬ LÝ LỖI VÀ ĐỨT GÃY</h1>
<ul>
<li>
<p>Không tự ý tạo thông tin còn thiếu.</p>
</li>
<li>
<p>Nếu dữ liệu bị trống, yêu cầu người dùng bổ sung.</p>
</li>
<li>
<p>Nếu dữ liệu mâu thuẫn, thông báo rõ nội dung cần xác nhận.</p>
</li>
<li>
<p>Nếu quá trình xử lý bị gián đoạn, tiếp tục từ bước chưa hoàn thành.</p>
</li>
<li>
<p>Giữ lại dữ liệu và kết quả các bước trước, không xử lý lại từ đầu nếu không cần thiết.</p>
</li>
</ul>
<h1 id="định-dạng-output">ĐỊNH DẠNG OUTPUT</h1>
<ul>
<li>
<p>Mã đơn hàng:</p>
</li>
<li>
<p>Tên khách hàng:</p>
</li>
<li>
<p>Sản phẩm:</p>
</li>
<li>
<p>Số lượng:</p>
</li>
<li>
<p>Đơn giá:</p>
</li>
<li>
<p>Tổng tiền:</p>
</li>
<li>
<p>Trạng thái:</p>
</li>
<li>
<p>Lỗi phát hiện:</p>
</li>
<li>
<p>Hướng xử lý:</p>
</li>
</ul>
<p>Chỉ kết luận đơn hàng hợp lệ khi tất cả thông tin bắt buộc đều đầy đủ và chính xác.</p>
<h2 id="bước-3-chạy-thử-prompt"><strong>3. Bước 3: Chạy thử Prompt</strong></h2>
<p><strong>Dữ liệu đầu vào thử nghiệm:</strong></p>
<ul>
<li>
<p>Mã đơn hàng: DH001</p>
</li>
<li>
<p>Tên khách hàng: Nguyễn Văn A</p>
</li>
<li>
<p>Sản phẩm: Chuột máy tính</p>
</li>
<li>
<p>Số lượng: 2</p>
</li>
<li>
<p>Đơn giá: 150.000 VNĐ</p>
</li>
<li>
<p>Địa chỉ: TP. Hồ Chí Minh</p>
</li>
<li>
<p>Số điện thoại: 0901234567</p>
</li>
</ul>
<p><strong>Kết quả phản hồi của AI:</strong></p>
<h1 id="kết-quả-kiểm-tra-đơn-hàng">KẾT QUẢ KIỂM TRA ĐƠN HÀNG</h1>
<ul>
<li>
<p>Mã đơn hàng: DH001</p>
</li>
<li>
<p>Tên khách hàng: Nguyễn Văn A</p>
</li>
<li>
<p>Sản phẩm: Chuột máy tính</p>
</li>
<li>
<p>Số lượng: 2</p>
</li>
<li>
<p>Đơn giá: 150.000 VNĐ</p>
</li>
<li>
<p>Tổng tiền: 300.000 VNĐ</p>
</li>
<li>
<p>Trạng thái: Hợp lệ</p>
</li>
<li>
<p>Lỗi phát hiện: Không có.</p>
</li>
<li>
<p>Hướng xử lý: Chuyển đơn hàng sang bước chuẩn bị giao hàng.</p>
</li>
</ul>
<p><strong>Kết luận:</strong> Đơn hàng có đầy đủ thông tin, số lượng và đơn giá hợp lệ. Có thể tiếp tục xử lý.</p>
<h2 id="bước-4-kiểm-tra-trường-hợp-dữ-liệu-lỗi"><strong>4. Bước 4: Kiểm tra trường hợp dữ liệu lỗi</strong></h2>
<p><strong>Dữ liệu thử nghiệm:</strong> Số lượng sản phẩm bị bỏ trống.</p>
<p><strong>Kết quả AI:</strong></p>
<ul>
<li>
<p>Mã đơn hàng: DH002</p>
</li>
<li>
<p>Sản phẩm: Bàn phím máy tính</p>
</li>
<li>
<p>Số lượng: Chưa cung cấp</p>
</li>
<li>
<p>Tổng tiền: Chưa thể tính.</p>
</li>
<li>
<p>Trạng thái: Cần bổ sung.</p>
</li>
<li>
<p>Lỗi phát hiện: Thiếu số lượng sản phẩm.</p>
</li>
<li>
<p>Hướng xử lý: Yêu cầu khách hàng cung cấp số lượng trước khi tiếp tục.</p>
</li>
</ul>

