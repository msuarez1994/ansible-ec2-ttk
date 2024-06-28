# Despliegue automatizado de TTK con Ansible en instancia EC2
## Pre-requisitos
- Ansible - https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html

## Valores que se deben modificar antes de lanzar el playbook
### Paso 1
En el archivo `ansible.cfg` modificar los valores `remote_user` o `private_key_file` si la ubicación o el nombre de usuario de su llave son diferentes
### Paso 2
En el archivo `docker-ttk-install.yaml` modificar el valor de `API_BASE_URL` e ingresar el nombre del DNS publica o IP publica que está indicado en el resumen de su instancia EC2
### Paso 3
Modificar en el archivo `inventory` e ingresar el nombre del DNS publica o IP publica que está indicado en el resumen de su instancia EC2

## Playbook 
### Validar que la conexion con la instancia EC2 se realizó de manera correcta
```bash
ansible ec2 -m ping
```
### Correr playbook
```bash
ansible-playbook docker-ttk-install.yaml
```