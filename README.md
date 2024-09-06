Hướng dẫn cài đặt node Elixir Testnet V3

Tham gia cộng đồng Elixir:

Discord dự án: https://discord.gg/VT4xvrs9
X: https://x.com/elixir
Docs dự án: https://docs.elixir.xyz/running-an-elixir-validator
Tham gia cộng đồng Node Miner:

Discord Node Miner: https://discord.gg/44B8pt4tSM
Các lệnh sử dụng trong video:
bash
```
# Cập nhật và nâng cấp hệ thống
sudo apt update
sudo apt upgrade -y

# Cài đặt các gói cần thiết
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

# Thêm key và repository của Docker
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Cập nhật lại danh sách gói và cài đặt Docker
sudo apt update
sudo apt install docker-ce -y

# Kiểm tra trạng thái của Docker
sudo systemctl status docker

# Thêm người dùng vào nhóm Docker
sudo usermod -aG docker $USER

# Chạy thử Docker
docker run hello-world

# Chỉnh sửa quyền và khởi động lại Docker
sudo chown root:docker /var/run/docker.sock
sudo systemctl restart docker
docker run hello-world

# Chạy node Elixir Testnet V3
docker run -d \
  --env-file ~/worker1/validator.env \
  --name elixir_worker1 \
  --platform linux/amd64 \
  --restart unless-stopped \
  -p 17696:17690 \
  elixirprotocol/validator:v3

docker run -d \
  --env-file ~/worker2/validator.env \
  --name elixir_worker2 \
  --platform linux/amd64 \
  --restart unless-stopped \
  -p 17697:17690 \
  elixirprotocol/validator:v3
```
Link một số sàn giao dịch dành cho các bạn người mới:

Binance: https://t.co/27zkGLNNMR
Bybit: https://t.co/GJtrEgeezb
Kucoin: https://t.co/RzeBEpni1v
Okx: https://t.co/VFwr3RZazp
Mexc: https://t.co/qfFjzlaU2c
Donate for me:

ETH-USDT-USDC: 0x9eb472eb5314e874dd4d642e6bb833c6b1296272
BTC: bc1pz5jcrtkg22rd3t6gnaxmc3fcgfkm98rz4dl84txesded20s4y0fsn0rggt
Hãy chắc chắn bạn đã tham gia Discord của dự án và theo dõi kênh X của Elixir để cập nhật những thông tin mới nhất. Nếu có bất kỳ câu hỏi nào, hãy để lại bình luận bên dưới!
