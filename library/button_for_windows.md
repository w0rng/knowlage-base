# Специальная кнопка для загрузки Windows
Windows будет загружаться при зажатом shift. Если его не зажимать, то будет грузиться Linux.

1. Сделать все по инструкции [Как скрыть меню grub](https://github.com/a-abram/KnowlageBase/blob/master/library/hide_menu_grub.md), однако строчку `set timeout=-1` заменить на следующее:  
```
    insmod chain 
    insmod ntfs 
    set root=(hd0,1) 
    chainloader +1
    boot
```  
Где `(hd0,1)` - раздел с Windows (0 диск т.е. sda, 1 раздел)  
2. Сконфигурируйте grub. Обычно, это делается следующий образом:  
```sudo grub-mkconfig -o /boot/grub/grub.cfg```  
3. Теперь, чтобы запустить Windows, нужно зажимать shift, а чтобы запустить Linux, делать ничего не надо.
