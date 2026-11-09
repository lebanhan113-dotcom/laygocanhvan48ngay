# Easy Peasy English – Buddy | GitHub Pages

Website tĩnh tiếng Việt dành cho luyện từ vựng. **Tệp chạy chính là `index.html` ở ngay thư mục gốc của repository.** Mã HTML, CSS và JavaScript nằm cùng một tệp, không yêu cầu Node.js, Vite hay build.

> **CHÚ Ý:** Đây là **bộ máy học thử nghiệm**. Dữ liệu từ vựng 88 mục, hình minh họa và hình Buddy nguyên bản **chưa được cung cấp**; hiện có 10 Unit rỗng. Không ghi đè website Buddy chính thức hoặc công bố đây là bài học đã hoàn chỉnh.

## 1. Đưa lên GitHub bằng giao diện web

1. Tải `Buddy_GitHub_Pages.zip` và **giải nén**. Không tải nguyên file ZIP lên repository rồi mong GitHub tự giải nén.
2. Truy cập https://github.com/new, tạo một repository (ví dụ `buddy-english`). Nếu muốn GitHub Pages miễn phí cho repo riêng, hãy kiểm tra điều kiện tài khoản; repo công khai thường đơn giản nhất.
3. Trong repository, chọn **Add file → Upload files**, kéo thả **toàn bộ nội dung** thư mục `Buddy_GitHub_Pages` sau giải nén, bảo đảm `index.html` xuất hiện ở **gốc repository**, không nằm trong thư mục con.
4. Chọn **Commit changes**.
5. Mở **Settings → Pages → Build and deployment → Source: Deploy from a branch**. Chọn nhánh `main`, thư mục `/(root)` và **Save**.
6. Khi GitHub báo Pages đã triển khai, mở liên kết ở mục Pages. URL thường có dạng `https://TEN_TAI_KHOAN.github.io/buddy-english/` (địa chỉ thật tùy repository).

Bạn có thể thử ứng dụng cục bộ bằng cách mở `index.html` hoặc chạy `python -m http.server 8000` từ thư mục này rồi vào `http://localhost:8000`.

## 2. Đưa dữ liệu Buddy gốc vào đúng cách

Mục tiêu là 10 Unit và 88 mục từ/cụm từ, phân bổ dự kiến: **8, 8, 10, 12, 9, 8, 7, 8, 9, 9**. Không tự đoán từ hoặc dùng hình tạo mới giả làm học liệu gốc.

1. Chuẩn bị danh sách đúng từ website gốc theo mẫu `buddy_10_unit_source_template.json` hoặc `buddy_csv_format.csv`. Với ảnh, dùng URL HTTPS công khai phù hợp, đường dẫn tương đối trong repo, hoặc `data:image/...` để nhúng trực tiếp.
2. Mở website, bấm **Nhập dữ liệu gốc** và nhập JSON hoặc CSV.
3. Bấm **Kiểm tra chất lượng học liệu**, rà soát thiếu nghĩa, IPA, hình ảnh, câu mẫu và đủ 88 mục.
4. Bấm **Xuất website HTML** để nhận file `index.html` mới **đã nhúng dữ liệu**. **Quan trọng:** dữ liệu vừa nhập trong trình duyệt chỉ lưu trên thiết bị của bạn; người xem GitHub Pages sẽ **không tự nhận dữ liệu** cho đến khi bạn thay `index.html` trên repository bằng bản đã xuất.
5. Commit file `index.html` mới lên GitHub. Kiểm tra lại trang trực tuyến sau khi GitHub Pages cập nhật.

## 3. Tính năng và giới hạn

- Học từ → Nghe chọn tranh → Nhìn tranh nhớ từ → Luyện câu → Ôn từ cần học lại.
- Nghe giọng tổng hợp nếu trình duyệt/thiết bị có giọng `en-GB` (nếu không, ứng dụng sẽ báo thiếu giọng phù hợp).
- Bài kiểm tra cuối Unit, trò chơi qua toàn bộ từ khả dụng, lưu tiến độ trên **cùng trình duyệt/thiết bị** bằng `localStorage`.
- Ghi âm và nghe lại nếu người dùng cấp quyền microphone. **Không dùng độ tin cậy của nhận dạng giọng nói để cho điểm phát âm**, không có dịch vụ AI chấm âm vị.
- Microphone thường hoạt động ổn định khi trang được mở qua **HTTPS** (GitHub Pages có HTTPS). Người học cần đồng ý cấp quyền microphone.
- GitHub Pages **không** cung cấp backend, tài khoản, lớp học hay đồng bộ kết quả giữa nhiều thiết bị. Không tải dữ liệu cá nhân nhạy cảm của học sinh lên repository công khai.

## 4. Sửa website

Có thể sửa `index.html` trực tiếp trên GitHub hoặc tải tệp về sửa rồi upload lại. Trang tĩnh này không cần lệnh `npm install` hay `npm run build`.

## 5. Kiểm tra trước khi công bố

Chạy `python scripts/check_site.py` (chỉ dùng thư viện Python chuẩn; công cụ Node.js được dùng nếu có). Kiểm tra các thao tác chính trên điện thoại: danh sách Unit, nhấn nghe, trắc nghiệm hình, ẩn đáp án, chấm kết quả, trò chơi và lưu tiến độ. Khi chưa có dữ liệu gốc, chỉ có thể thử bằng dữ liệu giả lập ngoài bản phát hành.
