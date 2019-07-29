# Как скрыть меню grub  

1. Создайте скрипт 31_hold_shift в /etc/grub.d/  
2. Скопируйте в него следубщий код:  
```
#! /bin/sh
set -e

# grub-mkconfig helper script.
# Copyright (C) 2006,2007,2008,2009  Free Software Foundation, Inc.
# Copyright (C) 2013 Hugo Osvaldo Barrera

prefix="/usr"
exec_prefix="${prefix}"
datarootdir="${prefix}/share"

export TEXTDOMAIN=grub
export TEXTDOMAINDIR="${datarootdir}/locale"

. "${datarootdir}/grub/grub-mkconfig_lib"

found_other_os=

if [ "x${GRUB_HIDDEN_TIMEOUT_QUIET}" = "xtrue" ] ; then
  verbose=
else
  verbose=" --verbose"
fi

cat <<EOF
if [ "x\${timeout}" != "x-1" ]; then
  if keystatus; then
    if keystatus --shift; then
      set timeout=-1
    else
      set timeout=0
    fi
  else
    if sleep$verbose --interruptible 3 ; then
      set timeout=0
    fi
  fi
fi
EOF
```  
3. Сконфигурируйте grub. Обычно, это делается следующий образом:  
``` sudo grub-mkconfig -o /boot/grub/grub.cfg```  
4. Теперь, чтобы открыть меню grub при загрузке, нужно зажимать shift.
