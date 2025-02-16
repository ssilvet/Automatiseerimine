# Automatiseerimine
Vagrant

õppematerjal:
https://muudel.karjane.net
külalisligipääsu parool:
hammasratas
 
Teil on vaja luua uus Vagrantfile nii, et luuakse järgnevalt kirjeldatud keskkond. Leidke ise Vagrant Cloudis https://app.vagrantup.com/boxes/search õiged virtuaalmasina imaged õigete versioonidega):
 
NB! Virtualboxi võrgu nimeks kasutage ansible_lab asemel ansible_sinunimi
 
1. Debian 12 virtuaalmasin nimega (nii linuxi hostinimi, virtualboxi vm nimi,
kui vagranti nimi) sinunimi-dockerhost
privaatvõrgu ip 10.10.10.130/25
RAM 8 GB
CPU 4 tuuma
 
2. Debian 12 virtuaalmasin nimega (nii linuxi hostinimi, virtualboxi vm nimi,
kui vagranti nimi) sinunimi-ansible
privaatvõrgu ip 10.10.10.131/25
 
3. Ubuntu 24.04 virtuaalmasin nimega (nii linuxi hostinimi, virtualboxi vm nimi, kui vagranti nimi) sinunimi-ubuntu
privaatvõrgu ip 10.10.10.132/25
 
4. Centos Stream 9 virtuaalmasin nimega (nii linuxi hostinimi, virtualboxi vm nimi, kui vagranti nimi) sinunimi-centos
privaatvõrgu ip 10.10.10.133/25
 
5. OpenSUSE Leap virtuaalmasin nimega (nii linuxi hostinimi, virtualboxi vm nimi, kui vagranti nimi) sinunimi-opensuse
privaatvõrgu ip 10.10.10.134/25
 
 
Paigaldage kõigisse virtuaalmasinatesse kohe paigalduse ajal paketid snmpd, tmux, mc, wget, tree ja git
Paigaldage sinunimi-ansible masinasse paigalduse ajal paketid Ansible, sshpass, yamllint ja ansible-lint.
Paigaldage sinunimi-dockerhost masinasse kohe paigalduse ajal kõik Dockeri kasutamiseks vajalikud paketid.
 
Ansible inventory grupid:
Linux - Kõik masinad
Debian - Ainult debianid
Centos - ...
Ubuntu - ...
Opensuse - ...
 
Looge Ansible play, mis kontrollib, kas kõik masinad on püsti ja vastavad ja mis on nende OS versioon.
 
Looge Ansible play, mis kontrollib, kas kogu eelnevalt Vagranti abil paigaldatud tarkvara on masinates olemas ja kui pole siis raporteerib ning paigaldab.
