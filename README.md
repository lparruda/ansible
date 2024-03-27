Comandos Ad-Hoc
ansible -i hosts all -u lroot -k -b -k -m ping

	- -i arquivos de inventário (hosts)
	- -u Usuário
	- -k Para pedir senha
	- -b O comando será executado com elevação de privilégio
	- -K pedir senha para execução com elevação
	- -m O módulo que será executado

Listar os hosts para validação:
ansible all -m ping -u lroot --list-hosts

ansible 10.1.0.13 -m yum -a "name=* state=latest" -b -K -u lroot

Latest para aplicar
Absent para removervim 


Criando usuários:
ansible all -i hosts -u pereira -b -m user -a "name=teste state=present password=teste123"
Removendo usuários:
ansible all -i hosts -u pereira -m user -a "name=teste state=absent"
ansible all -i hosts -u pereira -m user -a "name=teste state=absent" -b -m file -a "path=/home/teste state=absent"
![image](https://github.com/lparruda/ansible/assets/77876497/94ab178a-e0b7-4e61-a38b-bf77c7c361bc)
