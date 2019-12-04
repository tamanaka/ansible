Playbook Ansible для установки wordpress и всего необходимого ПО (nginx,php,mysql) на CentOS 7 
Playbook создан на CentOS 7

Для работы Ansible необходимо, чтобы на удаленном хосте был установлен Python. В состав CentOS 7 он входит по умолчанию. В противном случае он будет установлен автоматически

Для подключения к удаленному хосту необходимо сгенерировать ssh ключ (ssh-keygen) и передать его на удаленный хост (ssh-copy-id root@hostIP)


После установки ключей можно  выполнить playbook ansible для установки wordpress. 
Playbook зашифрован с помощью ansible-vault, а точнее зашифрованы строки с паролями в файле playbooks/vars/main.yml.

Для выполнения playbook необходимо знать ключ или иметь файл с ключом или знать его

Запуск производится из папки /etc/ansible/ командой:
$ansible-playbook playbooks/wordpressPlayBook.yml -i hosts --vault-password-file vault.key

где vault.key -  файл с ключом в открытом виде.

Так же можно использовать команду, где необходимо ввести пароль
$ansible-playbook playbooks/wordpressPlayBook.yml -i hosts --ask-vault-pass

После завершения установке необходимо перейти в административную панель Wordpress по ip адресу удаленного хоста, для последующей настройки.

