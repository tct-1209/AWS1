---
title: "Worklog Tuần 8"
date: 2026-07-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

# Worklog Tuần 8: Kết nối mạng nâng cao với VPC Peering và Transit Gateway

**Thời gian thực hiện:** 08/06/2026 - 14/06/2026

## 1. Mục tiêu tuần

- Nắm mô hình VPC Peering để kết nối hai VPC.
- Tìm hiểu Transit Gateway như trung tâm kết nối nhiều VPC.
- Biết cách cập nhật route table và kiểm thử kết nối giữa các máy chủ.

## 2. Chi tiết công việc triển khai

| Thứ | Thời gian | Nội dung công việc |
| --- | --- | --- |
| Thứ 2 | 08/06/2026 | Tìm hiểu VPC Peering, giới hạn, luồng traffic và trường hợp sử dụng. |
| Thứ 3 | 09/06/2026 | Nghiên cứu Cross-Peer DNS Resolution và tác động đến việc phân giải tên miền nội bộ. |
| Thứ 4 | 10/06/2026 | Tìm hiểu Transit Gateway Attachment và cách nhiều VPC kết nối về một điểm trung tâm. |
| Thứ 5 | 11/06/2026 | Đọc cách cập nhật route table ở từng VPC để cho phép traffic đi qua peering/gateway. |
| Thứ 6 | 12/06/2026 | Tổng hợp cách kiểm tra kết nối bằng ping, private IP, route table và Security Group. |

## 3. Kết quả đạt được

- Hiểu sự khác nhau giữa VPC Peering và Transit Gateway.
- Biết các bước định tuyến traffic giữa nhiều VPC.
- Cải thiện khả năng debug lỗi kết nối mạng nội bộ AWS.

## 4. Nguồn tài liệu tham khảo

| Nguồn | Đường dẫn | Nội dung tham khảo |
| --- | --- | --- |
| 000019 - VPC Peering | [https://000019.awsstudygroup.com/](https://000019.awsstudygroup.com/) | VPC peering and DNS |
| 000020 - AWS Transit Gateway | [https://000020.awsstudygroup.com/](https://000020.awsstudygroup.com/) | Transit Gateway and attachments |
| 000010 - Route 53 Resolver | [https://000010.awsstudygroup.com/](https://000010.awsstudygroup.com/) | Hybrid DNS concepts |
