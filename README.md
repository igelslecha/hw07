# hw07

**1. Вход в систему без пароля**

*Настроил вход в окно через Oracle VM VirtualBox менеджер в машину одной из предыдущих домашек*

*а) При загрузке машины нажимаю "Е" (edit)*

screen1

*дописал в конце строки начинающейся с linux16  "init=/bin/sh" и нажал сtrl-x*
 
screen2

*перемонтирую для чтения "mount -o remount,rw /" и убеждаюсь, что диск доступен "mount | grep root"*

screen3

*б) При загрузке машины нажимаю "Е" (edit) дописал в конце строки начинающейся с linux16  "rd.break" и нажал сtrl-x*

screen4

*загружаюсь*

screen5

*перемонтирую основной каталог с правами на чтение "mount -o remount,rw /sysroot", делаем основным для работы "chroot /sysroot", меняем пароль на 12345 "passwd root", создаю файл "touch /.autorelabel"*

screen6

*перезагружаюсь и захожу под root "12345"*

screen7

*в) При загрузке машины нажимаю "Е" (edit) заменил в  строке начинающейся с linux16 "ro" на "rw init=/sysroot/bin/sh"*

screen8

*Так как система уже загрузилась с возможностью записи, делаем основным для работы "chroot /sysroot", меняем пароль на 12345 "passwd root", создаю файл "touch /.autorelabel", так же как в предыдущем случае.*

screen9

**2. Запустил систему , проверяю текущее состояние ситемы "vgs" и переименовываю "vgrename centos OtusRoot"**

screen10

*поправил /etc/fstab, /etc/default/grub, /boot/grub2/grub.cfg и пересоздал initrd image, чтобы он знал новое название*

screen11

*Перезагрузился и проверяю новое имя*

screen12

**3. Добавить модуль в initrd**

*Создаю папку /usr/lib/dracut/modules.d/01test, добавляю в неё скрипты из приктики (module-setup.sh и test.sh) и правлю скрипт с пингвином*

screen13

*Пересобираю образ initrd*

screen14

*перезагружаю и проверяю*

screen15
