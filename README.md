# ValeriyTuev_infra
##Homework 4
Using command like "ssh someinternalhost" is possible if we add config file to ssh folder. Config file should consist:
host someinternalhost
	hostname 10.142.0.2
	user valeriy.tuev
	proxyjump valeriy.tuev@35.204.145.192
	identityfile ~/.ssh/id_rsa

*IP adresses for Travis check*
bastion_IP = 35.204.145.192
someinternalhost_IP = 10.142.0.2


##Homework 5

testapp_IP = 35.204.172.151
testapp_port = 9292

Выполнено основное задание: закомиттил скрипты install_ruby.sh, 
install_mongodb.sh и deploy.sh. 

Дополнительное задание: закомиттил скрипт startup-script.sh, для 
добавления к команде в gcloud. Команда для создания, используя скрипт:
gcloud compute instances create reddit-app\ 
--boot-disk-size=10GB \
--image-family ubuntu-1604-lts \
--image-project=ubuntu-os-cloud \
--machine-type=g1-small \
--tags puma-server \
--restart-on-failure \
--metadata-from-file startup-script=%PATH%\startup-script.sh


**Дополнительное задание
Создать правило firewall из консоли. Для тестового приложения команда 
выглядит так:
gcloud beta compute firewall-rules create default-puma-server\ 
--action allow \
--target-tags puma-server \
--source-ranges 0.0.0.0/0 \
--rules tcp:9292

**Как запустить проект
Копируем себе скрипт startup-script.sh, запускаем команду для создания 
VM, указав путь к скрипту, команда дана выше.

**Как проверить работоспособность
Смотрим в консоли адрес получившейся машины и идем по ссылке. У меня 
выглядит так:
http://35.204.172.151:9292

**PR checklist
Выставил label с номером ДЗ
Выставил label c темой ДЗ
