Playbook Ansible для установки wordpress и всего необходимого ПО (nginx,php,mysql) на CentOS 7 
Playbook создан на CentOS 7

Для работы Ansible необходимо, чтобы на удаленном хосте был установлен Python. В состав CentOS 7 он входит по умолчанию.

Для подключения к удаленному хосту необходимо сгенерировать ssh ключ (ssh-keygen) и передать его на удаленный хост (ssh-copy-id root@hostIP)



После установки ключей можно к выполнить playbook ansible для установки wordpress. 
Playbook зашифрован с помощью ansible-vault, а точнее зашифрована только файл main.yml, содержащий все нужные пароли.

Для выполнения playbook необходимо снять защиту с помощью команды ansible-vault decrypt.
$ ansible-vault decrypt main.yml 
При этом полностью файл полностью расшифровывается

Запуск производится из папки playbook командой:
$ ansible-playbook wordpressPlayBook.yml

После завершения установке необходимо перейти в административную панель Wordpress по ip адресу удаленного хоста, для последующей настройки.

