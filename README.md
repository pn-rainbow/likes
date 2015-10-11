# CMIT Engineerim 

## Кратко о python
Есть хороший ресурс с простыми короткими квестами на английском языке:
[https://www.dataquest.io](DataQuest), первый трек -- **Python Programming**.





## Разработка с виртуальной машиной

### Linux Specific

На компе необходимы Virtualbox, Vagrant, Ansible

[https://www.virtualbox.org/](Virtualbox)

[https://www.vagrantup.com/](Vagrant)

[http://docs.ansible.com/ansible/intro_installation.html](Ansible)
_Можно через пакетный менеджер `apt-get`, `brew` и `pip`_

После установки вагранта, желательно поставить плагин `vagrant-cachier`,
в консоли в произвольной папке запустить следующую комманду
```
vagrant plugin install vagrant-cachier
```

### Windows specific

Для использования Linux-инструментов под Windows необходимо поставить [https://www.cygwin.com/](Cygwin).
При установке стоит указать следующие пакеты:
```
python python-paramiko python-crypto gcc-g++ wget openssh python-setuptools
```

Теперь можно работать в `Cygwin64 Terminal`.
Возможно при установке какого-нибудь из пакетов он попросит поставить Microsoft Visual C++ Runtime:

http://aka.ms/vcpython27


Есть другой вариант -- поставить [http://babun.github.io/](Babun). Это хорошая сборка Cygwin с менеджером пакетов `pact`.






## Запускаем VM

Теперь можно зайти в папку `local-vm/` и выполнить команду в консоли
```
vagrant up
```

Она скачает образ, указанный в `Vagrantfile` и настроит сеть. 
Чтобы подключиться по ssh к запущенной виртуалке, в этой же папке выполните: 
```
vagrant ssh
```

Возможно выпадет ошибка, если вы удаляли машину и ставили заново. 
fingerprint'ы не совпадут, и вам придется почистить файл `~/.ssh/known_hosts`, а точнее удалить строчку с нужным сервером или айпишником.

Если все прошло хорошо, вы подключились к виртуальной машине под пользователем `vagrant`. 


## Deploy
Теперь можно развернуть окружение, для этого в домашней рабочей системе в папке `/devops` выполним команду
```
ansible-playbook -i inventory deploy.yml 
```

Эта команда поставит все необходимые пакеты в виртуальную машину.


Подробное руководство по (http://docs.ansible.com/ansible/intro.html)[Ansible доступно тут].
Хотя бы одному члену команду стоит изучить введение и `playbooks`.
Остальным это потребуется только при необходимости. В целом система заточена на легкое написание инструкций.
Единственная сложность -- спроектировать инструкции так, чтобы это было переиспользуемо и удобно.



### TODO

1. Nginx devops
1. Code upload
1. Cygwin instructions




