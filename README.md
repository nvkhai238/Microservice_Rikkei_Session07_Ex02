# Session 07 - Bài 2: Patient Service dùng Config Server

`patient-service` chỉ giữ tên ứng dụng và địa chỉ Config Server trong
`application.properties`. Cổng chạy và toàn bộ cấu hình PostgreSQL nằm trong
`medical-config-repo/patient-service.properties`.

## Chạy bài

```bash
docker compose up -d

cd config-server
gradle bootRun

# Terminal khác, từ thư mục gốc bài 2
cd patient-service
gradle bootRun
```

Kiểm tra Config Server:

```bash
curl http://localhost:8888/patient-service/default
```

Khi Patient Service khởi động, Hibernate sẽ tạo bảng `patients` trong database
`patient_db`. Nếu PostgreSQL của máy dùng thông tin khác, sửa file cấu hình tập
trung rồi commit thay đổi trước khi chạy lại.

