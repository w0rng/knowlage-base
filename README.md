# Файлы настроек для sublime. Утилиты.

# F.A.Q.
Q: Что это?
A: Это настройки моих программ. А так же небольшие скриптики.

Q: Зачем это?
A: Чтобы не настраивать каждый раз все руками.

Q: ...
A: Вдохновлено [Relrin](https://github.com/Relrin/dotfiles)



# Установка sublime

1) Скопируйте файлы из sublime/Packages в ~/.config/sublime-text-3/Packages
```bash
git clone https://github.com/a-abram/dotfiles ~/Downloads/
cd ~/Downloads/
cp -r ~/Downloads/dotfiles/sublime/Packages/* ~/.config/sublime-text-3/Packages/
```

2) Установите пакеты из списка [requirements.txt](https://raw.githubusercontent.com/a-abram/dotfiles/master/sublime/requirements.txt) при помощи [PackageControl](https://packagecontrol.io/)

3) Перезапустите sublime. Если что-то сломалось, прошу прощения.


# Установка скриптов

1) Сделайте скрипты исполняемыми, скопируйте в папку /usr/bin/ (для этого могут потребоваться права суперпользователя)
```bash
git clone https://github.com/a-abram/dotfiles ~/Downloads/
cd ~/Downloads/
chmod +x dotfiles/scripts/*
cp -r dotfiles/scripts/* ~/usr/bin/
```

2) Наслаждайтесь


# Описание скриптов

**imgur-screenshot** - В моем дистрибутиве нет нормальной программы для создания снимков области экрана. Поэтому мне пришлось честно найти и скопировать данный скрипт себе.
**np** - маленький скрипт, создающий все необхожимые файлы для нового, пустого проекта.