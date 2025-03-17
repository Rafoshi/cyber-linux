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


