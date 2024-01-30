# TÌM HIỂU VỀ ALERTMANAGER.

## I. GIỚI THIỆU.
Alertmanager xử lý cảnh báo được gửi bởi ứng dụng như là Prometheus server. Nó có các cơ chế Grouping, inhibition, silence


- Grouping: Phân loại cảnh báo có các tính chất tương tự với nhau. 
- Inhibition: là một khái niệm về việc chặn thông báo cho một số cảnh báo nhất định nếu các cảnh báo khác đã được kích hoạt.
- Silence: Silence là một cách đơn giản để tắt cảnh báo trong một thời gian nhất định.
- High avability: Alertmanager hỗ trợ cấu hình để tạo một cluster với độ khả dụng cao.



## II. CÁCH VIẾT RULE CHO ALERT MANAGER.

RULE LÀ THỨ CẦN THIẾT ĐỂ BIẾT NHỮNG THỨ GÌ SẼ ĐƯỢC CẢNH BÁO. 

VÍ DỤ: SERVER TẮT  THÌ SẼ CẢNH BÁO, SERVER QUÁ TẢI CŨNG CẢNH BÁO...


RULE ĐƯỢC VIẾT TRONG. `vi /etc/prometheus/alert.rules.yml` TẠI SERVER CHỨA PROMETHEUS NHA.

cat <<EOF > /etc/prometheus/alert.rules.yml

groups:
  - name: example
    rules:
      - alert: TÊN CẢNH BÁO
        expr: ĐIỀU KIỆN CỦA CẢNH BÁO( VÍ DỤ up==0) THƯỜNG LIÊN KẾT VỚI QUERRY CỦA PROMETHEUS.
        for: 5m
        labels:
          severity: warning #LOẠI CẢNH BÁO
        annotations:
          summary: "High CPU Load"
          description: "NỘI DUNG GỬI TRONG CẢNH BÁO. VÍ DỤ: ĐÂY LÀ CẢNH BÁO VÌ 1 CON INSTANT BỊ DOWN" 

EOF













