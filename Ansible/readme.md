# Configuración de Ansible

Instalaremos estos dos servicios,
<ul>
  <li>Apache</li>
  <li>Munin</li>
  <ul>
    <li>Munin-Master</li>
    <li>Munin-Node</li>
  </ul>
</ul>

PRIMER PASO. instalación del servidor web en mi caso Apache
------------------------
### Instalamos el servidor web en el munin_web:

Dentro de la carpeta Ansible ponemos este comando en nuestra consola: 


``ansible-playbook -i hosts install_apache.yml``


Luego que la instalacion este hecha, revisamos en el puerto 0.0.0.0:80 y nos mostrará el index de Apache, luego cambie el index por este:

<img src="https://github.com/Edwinlopez02/munin_install/blob/master/imagen/imagen.png">

SEGUNDO PASO. Instalacion de Munin
------------------------
### Intalamos Munin en el munin_node_web:

Dentro de la carpeta Ansible ponemos este comando en nuestra consola para que ansible instale los playbooks teniendo en cuenta los hosts asignados de munin node:


``ansible-playbook -i hosts install_munin_node.yml``


### Intalamos Munin en el munin_master_web

Dentro de la carpeta Ansible ponemos este comando en nuestra consola para que ansible instale los playbooks teniendo en cuenta los hosts asignados de munin-master:

``ansible-playbook -i hosts install_munin_master.yml``
