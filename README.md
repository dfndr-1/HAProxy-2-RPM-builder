# Сборка RPM HAProxy самой свежей версии из ветки 2.1 (для CentOS 7)

Для сборки пакета выполните следующие действия под обычным пользователем:

## Установка:

    sudo yum groupinstall 'Development Tools'

    cd /opt
    git clone https://github.com/philyuchkoff/HAProxy-2-RPM-builder.git
    cd ./HAProxy-2-RPM-builder
    git checkout master
    make
    
Собранный RPM будет лежать в 

    /opt/HAProxy-2-RPM-builder/rpmbuild/RPMS/x86_64/
    
## Проверка

После установки пакета можно проверить:

    haproxy -v

    HA-Proxy version 2.1.3 2020/02/12 - https://haproxy.org/
    Status: stable branch - will stop receiving fixes around Q1 2021.
    Known bugs: http://www.haproxy.org/bugs/bugs-2.1.3.html
    
## Если что-то не работает
То первым делом проверьте

    sestatus
    
Если он в enabled - отключите: откройте /etc/selinux/config и установите SELINUX в disabled

    

## С удовольствием приму все замечания

Если вам пригодилась эта штука - можно в качестве благодарности купить мне кофе! :) Но это совершенно не обязательно!

<a href="https://www.buymeacoffee.com/philyuchkoff" target="_blank"><img src="http://public.jc21.com/github/by-me-a-coffee.png" alt="Buy Me A Coffee" style="height: 51px !important;width: 217px !important;" ></a>
