# Polygon-ZKEVM

Cấu hính khuyến cáo:

    4 core
    16gb ram
    100ssd
    
1/ Nâng cấp hệ thống:

    sudo apt update && sudo apt upgrade -y
    
2/ Cài đặt Package cần thiết:

    sudo apt install pkg-config curl tmux git unzip build-essential libssl-dev -y
    
    apt install docker compose -y
    
3/ Set thông tin:

    ZKEVM_NET=testnet
    ZKEVM_DIR=./ZKEVM
    ZKEVM_CONFIG_DIR=./ZKEVM_CONFIG
    
Tạo thư mục ZK config:

    mkdir $ZKEVM_CONFIG_DIR
    
Tải bộ nguồn và giải nén vào các thư mục:

    curl -L https://github.com/0xPolygonHermez/zkevm-node/releases/latest/download/$ZKEVM_NET.zip > $ZKEVM_NET.zip && unzip -o $ZKEVM_NET.zip -d $ZKEVM_DIR && rm $ZKEVM_NET.zip
    
    cp $ZKEVM_DIR/$ZKEVM_NET/example.env $ZKEVM_CONFIG_DIR/.env
    
Mở file .env:

    nano $ZKEVM_CONFIG_DIR/.env
    
Thay đổi thông tin:

    "http://your.L1node.url" => thành link dòng 2 tài khoản ALchemy
    
Chạy node:

    sudo docker compose --env-file $ZKEVM_CONFIG_DIR/.env -f $ZKEVM_DIR/$ZKEVM_NET/docker-compose.yml up -d
  
Chúc các bạn thành công!

    Chanel: https://t.me/RunnodeVietNamese
    Youtube: https://www.youtube.com/@nodevalidatorvietnam
    Twitter: https://twitter.com/NodeValidatorVN
