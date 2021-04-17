# Install ibus-Unikey or ibus-Bamboo on Kali Linux 2021
 ## 1. Cài Đặt
  ### *1.1. Cài Đặt ibus-Unikey (Lựa Chọn Cách Này Để Cài Đặt)*
``` 
   $ sudo apt-get install ibus-unikey ibus-gtk3
Or $ sudo apt-get install --install-recommends ibus
   $ reboot
```   
   
  ### *1.2. Cài Đặt ibus-Bamboo (Cách Này Để Tham Khảo. Cài Xong Cũng Không Gõ Được)*
  
        $ sudo add-apt-repository ppa:bamboo-engine/ibus-bamboo
        $ sudo apt-get update
        $ sudo apt-get install ibus-bamboo ibus-gtk3
     Or $ sudo apt-get install --install-recommends ibus
        $ reboot

## 2. Cấu Hình
### Cách 1: Sửa Biến Môi Trường (Khuyến Nghị Sử Dụng Cách Này)
- Kiểm Tra Xem Shell Đang Dùng Là Gì: bash, zsh, fish,... bằng command sau:

  `$ echo $0`
- Nếu là bash thì thêm đoạn sau vào file ~/.bashrc, zsh thì thêm đoạn sau vào file ~/.zshrc,... Do shell trên Kali Linux Là zsh nên sẽ thêm vào file ~/.zshrc:

  `$ vim ~/.zshrc`
     ``````
     export GTK_IM_MODULE="ibus"
     export QT_IM_MODULE="ibus"
     export XMODIFIERS="@im=ibus"
     export QT4_IM_MODULE="ibus"
     export CLUTTER_IM_MODULE="ibus"
     export GLFW_IM_MODULE="ibus"
     ``````

  `$ reboot`
- Kiểm tra biến môi trường đã ăn cấu hình sau khi reboot hay chưa:

     `$ env | grep "IM_MODULE\|XMODIFIERS"`
     
- Kết quả trả về sẽ có dạng ví dụ như sau:

      GTK_IM_MODULE=xim
      QT_IM_MODULE=ibus
      XMODIFIERS=@im=ibus
      QT4_IM_MODULE=ibus
      CLUTTER_IM_MODULE=ibus
      GLFW_IM_MODULE=ibus
### Cách 2: Command Line
- Chạy lệnh sau để import config:

  `$ im-config -n ibus`

## 3. Add Bộ Gõ Unikey Vào Setting Trên Hệ Thống
- Chạy command sau:
   `$ ibus-setup`
- Change default Input Method sang ibus bằng command sau:
   `$ im-config
- Mở Settings trên hệ thống, add bộ gõ ibus-Unikey vào

- Sau đó reboot lại:
   `$ reboot
   
## 4. Tài Liệu Tham Khảo
- https://anonyviet.com/huong-dan-cai-bo-go-tieng-viet-tren-kali-linux/
- https://github.com/BambooEngine/ibus-bamboo
- https://github.com/BambooEngine/ibus-bamboo/issues/107
- https://blogchiasekienthuc.com/linux/cach-cai-dat-bo-go-tieng-viet-tren-ubuntu.html
- https://forums.kali.org/archive/index.php/t-45576.html
- https://github.com/BambooEngine/ibus-bamboo/wiki/Kh%C3%B4ng-g%C3%B5-%C4%91%C6%B0%E1%BB%A3c-ti%E1%BA%BFng-vi%E1%BB%87t-tr%C3%AAn-ph%E1%BA%A7n-m%E1%BB%81m-%60abc-xyz%60
