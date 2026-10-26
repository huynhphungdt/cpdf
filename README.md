# CPDF — Google Apps Script

Web app mobile-first để chọn nhiều ảnh trên điện thoại, sắp xếp, xoay, xóa và ghép thành một tệp PDF.

## Đặc điểm

- Ảnh và PDF được xử lý hoàn toàn trong trình duyệt; không tải lên Drive hay máy chủ.
- Hỗ trợ nhiều ảnh, kéo thả bằng chuột hoặc cảm ứng.
- Xuất A4, Letter hoặc khổ vừa với ảnh; có tùy chọn lề.
- Ảnh lớn được thu nhỏ tối đa 2.400 px để hạn chế bộ nhớ trên điện thoại.
- Dùng `pdf-lib` và `SortableJS` qua CDN.

## Triển khai bằng Apps Script

### Cách 1: Apps Script Editor

1. Mở [script.google.com](https://script.google.com) và tạo dự án mới.
2. Thay nội dung `Code.gs` bằng tệp `Code.gs` trong thư mục này.
3. Tạo tệp HTML tên `Index`, rồi dán nội dung `Index.html`.
4. Trong **Project Settings**, bật hiển thị tệp manifest và thay nội dung bằng `appsscript.json` nếu cần.
5. Chọn **Deploy → New deployment → Web app**.
6. Chọn **Execute as: Me** và quyền truy cập phù hợp. Với ứng dụng công khai, chọn **Anyone**.
7. Bấm **Deploy**, cấp quyền và mở URL `/exec` trên điện thoại.

### Cách 2: clasp

```bash
npm install -g @google/clasp
clasp login
clasp create --type webapp --title "CPDF"
clasp push
clasp deploy --description "CPDF v1"
```

Lệnh `clasp create` sẽ tạo `.clasp.json` gắn thư mục này với dự án Apps Script của bạn.

## Lưu ý

- Cần có Internet lúc mở trang để tải hai thư viện từ CDN.
- HEIC chỉ hoạt động nếu trình duyệt/điện thoại có thể giải mã định dạng đó.
- Với rất nhiều ảnh độ phân giải cao, nên chia thành vài lượt để tránh hết bộ nhớ trình duyệt.
