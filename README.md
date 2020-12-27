# linux5

### Задание
Практика с LVM. Создание логических томов  

### Выполнение
1. Смотрим текущее состояние  
![](https://sun9-25.userapi.com/impg/71AmDzyZvkNoJ0cyQHbhzzpBS4SM5gLFXspr5Q/4ZQc1svkAkU.jpg?size=590x505&quality=96&proxy=1&sign=147553277a2f32dc556f296446e69677&type=album)  
2. Добавляем диск как PV:  
![](https://sun9-16.userapi.com/impg/wk1WKSriOWWM5JZRVBJ_R_20gQooH5JYmwa29Q/6fir5t9cqfM.jpg?size=632x580&quality=96&proxy=1&sign=7e50ede88e5b65f8afd5355a4d199005&type=album)  
3. Создаём VG на базе PV:  
![](https://sun9-39.userapi.com/impg/J--6kybwxbAVbSNtuxR5MqiE9yCz9zqFiLHQIw/-NjEyVRSMF8.jpg?size=603x593&quality=96&proxy=1&sign=4bdbbaea5ed7bae0ee9352e375d1a357&type=album)  
4. Создаём LV на базе VG:    
![](https://sun9-11.userapi.com/impg/OTrx_dsXyhLfWi7Gs6HMXtcLoAP26W2w0ptxIg/G2DA5LMxE_w.jpg?size=758x414&quality=96&proxy=1&sign=e08291ac7b86c6fba74ee31df46e97b8&type=album)  
5. Создаём файловую систему, монтируем её и проверяем:  
![](https://sun9-41.userapi.com/impg/-w6MCKaN8gMp8Xy14AyZaTuVMqqM_ATOFzw4cQ/draiGMKYTzM.jpg?size=821x379&quality=96&proxy=1&sign=17a7ee0eb755b47525e4919fb8374963&type=album)  
полный лог команды mount:  
```
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
udev on /dev type devtmpfs (rw,nosuid,noexec,relatime,size=987308k,nr_inodes=246827,mode=755)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,noexec,relatime,size=203556k,mode=755)
/dev/sda5 on / type ext4 (rw,relatime,errors=remount-ro)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev)
tmpfs on /run/lock type tmpfs (rw,nosuid,nodev,noexec,relatime,size=5120k)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,mode=755)
cgroup2 on /sys/fs/cgroup/unified type cgroup2 (rw,nosuid,nodev,noexec,relatime,nsdelegate)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
none on /sys/fs/bpf type bpf (rw,nosuid,nodev,noexec,relatime,mode=700)
cgroup on /sys/fs/cgroup/pids type cgroup (rw,nosuid,nodev,noexec,relatime,pids)
cgroup on /sys/fs/cgroup/net_cls,net_prio type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls,net_prio)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/rdma type cgroup (rw,nosuid,nodev,noexec,relatime,rdma)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpu,cpuacct)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=28,pgrp=1,timeout=0,minproto=5,maxproto=5,direct,pipe_ino=13593)
mqueue on /dev/mqueue type mqueue (rw,nosuid,nodev,noexec,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,pagesize=2M)
debugfs on /sys/kernel/debug type debugfs (rw,nosuid,nodev,noexec,relatime)
tracefs on /sys/kernel/tracing type tracefs (rw,nosuid,nodev,noexec,relatime)
fusectl on /sys/fs/fuse/connections type fusectl (rw,nosuid,nodev,noexec,relatime)
configfs on /sys/kernel/config type configfs (rw,nosuid,nodev,noexec,relatime)
/var/lib/snapd/snaps/core18_1880.snap on /snap/core18/1880 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gnome-3-34-1804_36.snap on /snap/gnome-3-34-1804/36 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/gtk-common-themes_1506.snap on /snap/gtk-common-themes/1506 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/snap-store_467.snap on /snap/snap-store/467 type squashfs (ro,nodev,relatime,x-gdu.hide)
/var/lib/snapd/snaps/snapd_8542.snap on /snap/snapd/8542 type squashfs (ro,nodev,relatime,x-gdu.hide)
/dev/sda1 on /boot/efi type vfat (rw,relatime,fmask=0077,dmask=0077,codepage=437,iocharset=iso8859-1,shortname=mixed,errors=remount-ro)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,size=203552k,mode=700,uid=1000,gid=1000)
gvfsd-fuse on /run/user/1000/gvfs type fuse.gvfsd-fuse (rw,nosuid,nodev,relatime,user_id=1000,group_id=1000)
/dev/sr0 on /media/ivan/VBox_GAs_6.1.14 type iso9660 (ro,nosuid,nodev,relatime,nojoliet,check=s,map=n,blocksize=2048,uid=1000,gid=1000,dmode=500,fmode=400,uhelper=udisks2)
/dev/mapper/mai-first on /mnt type ext4 (rw,relatime)
```
6. Создаём файл на весь размер точки монтирования:  
![](https://sun9-15.userapi.com/impg/stq6xkesaDEj_cxDlp_bn9YlB0Pjr5MMZRL45w/e0eSCGqkOHw.jpg?size=804x446&quality=96&proxy=1&sign=038380756ee4ca1b873ec27a88f5ef92&type=album)  
7. Расширяем LV за счёт нового PV в VG:  
![](https://sun9-58.userapi.com/impg/pNLY8y5DCKQKcmE6iz7WckPTZUxeqcD6-6aPrA/W1wGiqBMYws.jpg?size=801x522&quality=96&proxy=1&sign=bc3a3a68b3adaf9ff965051121018cb6&type=album)  
![](https://sun9-12.userapi.com/impg/NIhiGMsf_dey0BQrYfgeKLLPXuXiLK5q1qXF9A/1sFaNS87yEg.jpg?size=808x330&quality=96&proxy=1&sign=6ca5b537806aed5afb79b124d6b39845&type=album)  
8. Чуда не произошло, поэтому расширяем файловую систему:  
![](https://sun9-64.userapi.com/impg/4XURFI2Sp3pFgZ1iI6MpuKkXWALdEtgaSa4iYw/lKXUD1ARA6M.jpg?size=809x430&quality=96&proxy=1&sign=904010bc1d733fbcf68ccb5848bfbb6e&type=album)  
9. Уменьшаем файловую систему и LV:  
![](https://sun9-56.userapi.com/impg/FEVzkFqQHP0znrraAGI_rmtmUqenc3dH-mVaMg/CtaIuX9lpEw.jpg?size=808x470&quality=96&proxy=1&sign=87e0963dc29da8fc2622984c9428a9ac&type=album)  
![](https://sun9-43.userapi.com/impg/fGkKC7IqNNpEeWWB8jcnsq0r6Nkf9A5A4XxyDw/Uavw4b44H_M.jpg?size=765x297&quality=96&proxy=1&sign=2954e35f95bb752e03021d979eb128b6&type=album)  
10. Создаём несколько файлов и делаем снимок:  
![](https://sun9-63.userapi.com/impg/NVMYjNx9sKmSqwDFzM81wMJPZ9WeP8Yr6CoxaQ/eGLzrvgikhU.jpg?size=760x467&quality=96&proxy=1&sign=a6a955ffcacfe49eb7d87cc0c215b347&type=album)  
11. Удаляем несколько файлов:  
![](https://sun9-11.userapi.com/impg/JC-pdNUYt2nMrcIMYqQ46t_EEN3cpMCuSuG_Ug/r78F98qH2Go.jpg?size=448x54&quality=96&proxy=1&sign=32c259583cfc8dac9613303ba734622a&type=album)  
12. Монтируем снимок и проверяем, что файлы там есть. Отмонтируем.  
![](https://sun9-23.userapi.com/impg/4z4Gb67YzrqxYRrBBbnjEOMoLoA6k3li6Pu-og/wb2dae9dWYQ.jpg?size=518x76&quality=96&proxy=1&sign=0391e838476568f532a111ce8ca740f6&type=album)  
13. Отмонтируем файловую систему и производим слияние. Проверяем, что файлы на месте.  
![](https://sun9-13.userapi.com/impg/T45KshUooyo_4AGE6oRGJZniEMUmxKvmr4QSRw/Hs4COxW7G28.jpg?size=546x164&quality=96&proxy=1&sign=86d04705cd293f8ef3be659575096f17&type=album)  
14. Добавляем ещё PV, VG и создаём LV-зеркало.  
![](https://sun9-44.userapi.com/impg/UaOsRGguXjYXMd-aC0jmn5mwxElEGy-hyuQ2tA/TFmeeHnFGXY.jpg?size=621x172&quality=96&proxy=1&sign=6850c400c97327089eb9fcc7d17551f0&type=album)  
15. Наблюдаем синхронизацию.  
![](https://sun9-35.userapi.com/impg/7H7WWlLCfCUO81CVvD8y4zcffjWfxo5VrbfV5g/-jcDNhn5_5M.jpg?size=854x526&quality=96&proxy=1&sign=0b801079ffb7acf811d1a99ddb539ec1&type=album)  
