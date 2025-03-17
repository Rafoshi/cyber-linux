# Instruções de Gerenciamento de Usuários e Permissões

## Criar um usuário

Para criar um novo usuário no sistema, use o comando:

```bash
sudo adduser usuario_exemplo

sudo groupadd nome_do_grupo

sudo usermod -aG nome_do_grupo nome_do_usuario

sudo su - usuario_exemplo

mkdir pasta_protegida

echo "Este texto é confidencial" > pasta_protegida/arquivo.txt

chmod 710 pasta_protegida
chmod 600 pasta_protegida/arquivo.txt


chmod 777 pasta_protegida
chmod 777 pasta_protegida/arquivo.txt

su - novo_usuario

su

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


