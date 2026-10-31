# FerryGo — phiên bản Visual Studio Code + Admin server riêng

## Kiến trúc
- Customer server: http://localhost:3000
- Admin server: http://localhost:4000
- Shared API/data server: http://localhost:5000
- Database demo: data/db.json

## Chạy bằng Visual Studio Code
Cài Node.js LTS trước.

Mở thư mục bằng VS Code. Mở 3 terminal:

Terminal 1:
`node api/server.js`

Terminal 2:
`node customer/server.js`

Terminal 3:
`node admin/server.js`

Sau đó:
- Khách: http://localhost:3000
- Admin: http://localhost:4000
- API: http://localhost:5000/api/state

Tài khoản:
- Khách: user@ferrygo.local
- Admin: admin@ferrygo.local

Mật khẩu trong bản demo không dùng backend password; login chỉ mô phỏng theo email. Có thể nâng cấp JWT/bcrypt khi làm bản triển khai thật.

## Chức năng nổi bật
Admin hủy chuyến -> server cập nhật trip cancelled -> tự động hủy tất cả ticket của chuyến và đánh dấu refunded -> ghi activity log. Khách và Admin dùng hai máy chủ frontend riêng nhưng cùng API/data.
