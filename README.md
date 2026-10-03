Раздел 1 "Создание пользователя" 
useradd -u 1234 -m -G students user1, chage -M 90 user1

Раздел 2. "Мониторинг файлов и процессов"
2.1. find / -perm -4000 -type f -ls (результаты записаны в files-suid.out)
2.2	ps -eo pid,ruid,euid,comm | awk '$2 != 0 && $3 == 0' (результаты записаны ps-monitor.out)

Раздел 3. "Изучение механизма set-UID"	
chmod u+s /home/user1/cat (результаты записаны в stat.out)

Раздел 4. "Изучение механизма привилегий"
setcap cap_chown+ep /home/user1/chown	

Раздел 5. "Изучение механизма sudo"
visudo -f /etc/sudoers 
в sudoers добавлена строка user1 ALL=(root) NOPASSWD: /usr/bin/timedatectl set-time *, /usr/bin/timedatectl set-ntp *

Раздел 6. Скриншот комнадной строки с бухгалтерским шифром
Снимок экрана (PrtSc),  mv в папку	mephi-screenshot.png
