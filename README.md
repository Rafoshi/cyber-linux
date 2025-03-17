# Instruções de Gerenciamento de Usuários e Permissões

## Criar um usuário

Para criar um novo usuário no sistema, use o comando:

```bash
sudo adduser usuario_exemplo
```
## Criar um grupo de usuários (opicional)
```bash
sudo groupadd nome_do_grupo
```
## Adiciona ao grupo
```bash
sudo usermod -aG nome_do_grupo nome_do_usuario
```
## Entrar no usuario
```bash
sudo su - usuario_exemplo
```
## Criar pasta para alocar o arquivo .txt
```bash
mkdir pasta_protegida
```
## Cria o arquivo .txt
```bash
echo "Este texto é confidencial" > pasta_protegida/arquivo.txt
```
## Configura as permissões para somente o usuario criador e root ver
```bash
chmod 710 pasta_protegida
chmod 600 pasta_protegida/arquivo.txt
```
## Permite que qualquer um veja
```bash
chmod 777 pasta_protegida
chmod 777 pasta_protegida/arquivo.txt
```
## entrar em outro usuario
```bash
su - novo_usuario
```
## entrar como root
```bash
su
```
## servidor python
Agora voce pode rodar o servidor python (lembre de mudar de usuario mas n use o root)
```bash
python -m http.server 8000
```
ou

```bash
python -m http.server 8000 --directory /home/
```


## relembrar a config de ip

Dentro do linux
```bash
ip -br -c a
```
No Windows

```bash
ipconfig
```
Configurar intefaces de rede no linux

nano
```bash
nano /etc/network/interfaces
```
Vim
```bash
vim /etc/network/interfaces
```

```bash
# Configuração NAT para a interface enp0s3
auto enp0s3
iface enp0s3 inet dhcp

# Configuração NAT para a interface enp0s3
auto enp0s8
iface enp0s8 inet dhcp

# Configuração de Rede Interna para a interface enp0s9
auto enp0s9
iface enp0s9 inet static
    address 192.168.1.2    # Endereço IP fixo para a máquina virtual
    netmask 255.255.255.0   # Máscara de sub-rede
    gateway 192.168.1.1     # Gateway para a rede interna (opcional)

```

##Boa sorte
### Resumo das principais etapas:

1. **Criar usuário**: `sudo adduser usuario_exemplo`
2. **Criar grupo**: `sudo groupadd nome_do_grupo`
3. **Adicionar usuário ao grupo**: `sudo usermod -aG nome_do_grupo nome_do_usuario`
4. **Entrar como usuário**: `sudo su - usuario_exemplo`
5. **Criar pasta**: `mkdir pasta_protegida`
6. **Criar arquivo**: `echo "Texto" > pasta_protegida/arquivo.txt`
7. **Permissões**:
   - **Permissão restrita ao criador**: `chmod 710 pasta_protegida` e `chmod 600 pasta_protegida/arquivo.txt`
   - **Permissão para todos**: `chmod 777 pasta_protegida` e `chmod 777 pasta_protegida/arquivo.txt`
8. **Trocar de usuário**: `su - novo_usuario`
9. **Trocar para root**: `su`
---------
```python
import http.server
import socketserver


class CustomHTTPRequestHandler(http.server.SimpleHTTPRequestHandler):
    def send_error(self, code, message=None, explain=None):
        if code == 404:
            code = 403
        super().send_error(code, message, explain)


PORT = 8000

with socketserver.TCPServer(("", PORT), CustomHTTPRequestHandler) as httpd:
    print(f"Servidor HTTP rodando na porta {PORT}")
    httpd.serve_forever()


```

