# practica_servidordhcp_ansible
Crear un servidor DHCP con Ansible

Preparación del escenario

Crea un escenario en libvirt/kvm (no uses Vagrant) de la siguiente manera:

    Máquina Servidor: Tiene tres tarjetas de red: una que le da acceso a internet (NAT o pública) y dos redes privadas (muy aisladas).
    Máquina nodo_lan1: Un cliente linux conectado a la primera red privada.
    Máquina nodo_lan2: Un cliente linux conectado a la segunda red privada.

Servidor dhcp

Instala un servidor dhcp en el ordenador “servidor” que de servicio a los ordenadores de red local, teniendo en cuenta:

    Por la red privada 1: Reparte configuración en la red 192.168.100.0/24. El tiempo de concesión es de 12 horas.
    Por la red privada 2: Reparte configuración en la red 192.168.200.0/24. El tiempo de concesión es de 1 hora.

Para los dos ámbitos los servidores DNS deben ser el 1.1.1.1 y 1.0.0.1. Piensa que puertas de acceso se deben mandar a cada red.
Router-nat

Configura la máquina “servidor” para que haga router-nat para los clientes de ambas redes.
Funcionamiento del dhcp

Vamos a conectar un cliente windows a una de las redes. Vamos a comprobar que ocurre con la configuración de los clientes en determinadas circunstancias, para ello vamos a poner un tiempo de concesión muy bajo.


Tarea:

Realiza un playbook con ansible que configure de forma automática el servidor, para que haga de servidor DHCP y de router-NAT (no es necesario que se haga la configuración en los clientes). Entrega la URL del repositorio.

