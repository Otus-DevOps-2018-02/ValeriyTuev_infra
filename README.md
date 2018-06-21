# ValeriyTuev_infra
ValeriyTuev Infra repository
Homework 6
Using command like "ssh someinternalhost" is possible if we add config file to ssh folder. Config file should consist:
host someinternalhost
	hostname 10.142.0.2
	user valeriy.tuev
	proxyjump valeriy.tuev@35.204.145.192
	identityfile ~/.ssh/id_rsa

bastion_ip = 35.204.145.192
someinternalhost_ip = 10.142.0.2
