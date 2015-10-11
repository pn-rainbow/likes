# CMIT Engineerim 

## Разработка с виртуальной машиной


### Linux Specific:

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






