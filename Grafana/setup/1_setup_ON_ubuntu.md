# SETUP GRAFANA IN UBUNTU.


## BƯỚC 1: TẠO REPO

`sudo apt-get install -y software-properties-common`: install khóa

`sudo wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -`: thêm khóa

`sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"`: thêm repo vào nguồn.

## BƯỚC 2: CÀI ĐẶT VÀ KHỞI ĐỘNG.


`sudo apt-get update`: update hệ thống.

`sudo apt-get install grafana`: íntall grafara.

`sudo systemctl start grafana-server`: khởi động grafara

`sudo systemctl enable grafana-server`: khởi động cùng hệ thống


## BƯỚC 3: MỞ PORT FIREWALL NẾU CẦN.

```
firewall-cmd --zone=public --add-port=3000/tcp --permanent
firewall-cmd --reload

```

## BƯỚC 4: VÀO TRÌNH DUYỆT WEB.

VÀO TRÌNH DUYỆT WEB.

`http://localhost:3000`: truy cập vào grafara

`http://địa chỉ ip:3000`: truy cập vào grafara


MẬT KHẨU QUY ĐỊNH: admin-admin

SCRIPT:


```

#!/bin/bash

# Cập nhật danh sách gói
sudo apt-get update

# Cài đặt các gói cần thiết
sudo apt-get install -y software-properties-common
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"

# Thêm khóa GPG của Grafana
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -

# Cập nhật lại danh sách gói
sudo apt-get update

# Cài đặt Grafana
sudo apt-get install -y grafana

# Khởi động dịch vụ Grafana
sudo systemctl start grafana-server

# Kích hoạt tự động khởi động cùng hệ thống
sudo systemctl enable grafana-server

echo "Cài đặt Grafana hoàn tất. Truy cập http://localhost:3000 để sử dụng."

```


## II. SETUP 


