# Install ibus-Unikey or ibus-Bamboo on Kali Linux 2021
 ## 1. Cài Đặt:
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

## 2. Cấu Hình:
- Kiểm Tra Xem Shell Đang Dùng Là Gì: bash, zsh, fish,...

  `$ echo $0`
- Nếu là bash thì thêm đoạn sau vào file ~/.bashrc, zsh thì thêm đoạn sau vào ~/.zshrc,... Do shell trên Kali Linux Là zsh nên sẽ thêm vào file ~/.zshrc:

  `$ vim ~/.zshrc`
     ``````
     GTK_IM_MODULE="ibus"
     QT_IM_MODULE="ibus"
     XMODIFIERS="@im=ibus"
     QT4_IM_MODULE="ibus"
     CLUTTER_IM_MODULE="ibus"
     GLFW_IM_MODULE="ibus"
     ``````

  `$ reboot`
- Kiểm tra biến môi trường đã ăn cấu hình sau khi reboot hay chưa:

`$ env | grep "IM_MODULE\|XMODIFIERS"`
- Kết quả trả về sẽ có dạng như sau:

      `
      GTK_IM_MODULE=xim
      QT_IM_MODULE=ibus
      XMODIFIERS=@im=ibus
      QT4_IM_MODULE=ibus
      CLUTTER_IM_MODULE=ibus
      GLFW_IM_MODULE=ibus
      `
