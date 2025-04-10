# IAM

responsavel por gerenciar/organizar acessos/usuarios na AWS, como criar usuarios, grupos, gerenciar/dar permissoesa a usuarios e grupos.

- IAM eh um servico da aws global, ou seja nao precisamos selecionar uma determinada regiao para usar o servico.

## Usuarios

- podemos especificar os servicos que cada usuario pode ou nao ter acesso.

## Grupos
- um grupo eh composto por usuarios mas nao pode conter outros grupos
- um usuario nao precisa pertencer a um grupo (nao eh uma boa pratica)
- um usuario pode pertencer a um ou mais grupos.

## Politicas
- podemos definir politicas, ou seja um user pode ter acesso ao s3 mas nao pode apagar ou criar arquivos.
- politicas sao definidas por json

## Funcoes (roles)

As funções, ou roles, estão ligadas principalmente aos serviços da AWS. Elas são usadas quando queremos que um serviço da AWS acesse outro serviço com segurança.

Por exemplo, se quisermos que o RDS escreva ou leia dados de um bucket S3, precisamos criar uma função (role) com as permissões necessárias, e atribuí-la ao serviço responsável.

Características:
Roles não estão ligadas a usuários específicos.

São assumidas temporariamente, ou seja, um serviço assume uma role apenas durante o tempo necessário para executar uma tarefa.

Permitem delegar permissões de forma segura, seguindo o princípio do menor privilégio.


## Mecanismos de seguranca

**politica de senhas:**
1 - definir uma senha forte para evitar comprometar nossa conta/aplicacoes na aws
2 - podemos definir/solicitar para que a senha contenha x caracteries, se precisa ser maisculo ou nao, se permite numeros ou caracteries especiais
3 - podemos permitir ou nao que o usuario mude sua senha
4 - podemos criar a regra que a senha expire depois de x dias e que nao permita reutilizar uma senha anteriormente ja usada.

**MFA:**
 
 o MFA eh um recurso de autenticacao de 2 fatores, ou seja senha + um codigo/token 'aleatoria' enviado para um app, assim garantindo + seguranca.

 1 - MFA virtual : como o google authenticator
 2 - chave de seguranca fisica (como se fosse um pen drive)
 3 - token fisico (como os de bancos)

 ## Formas de acesso

 Podemos acessar a AWS de 3 maneiras:

 1 - AWS console (interface web) onde usammos senha + mfa
 2 - AWS CLI (linha de comando) onde usamos as chaves de acesso
 3 - AWS sdk (software da aws) onde usamos as chaves de acesso

 **bonus*:* tambem podemos usar o cli dentro da nuvem, atraves da cloudShell

 Chaves de acessos sao gerados na aws console, cada usuario gerencia a sua, uso intransferivel.

## Boas praticas IAM

- nao usar a conta root(somente quando criar)
- casa usuario deve ter seu acesso, jamais compartilhe
- ter uma boa politica de senha
- usar MFA


## Resumo Questoes

1 - IAM eh utilizado para Controlar acesso a serviços e recursos da AWS
2 - Todo usuario criado (fora o root) nao podem fazer nada sem que as permissoes sejam dadas
3 - dentro do IAM o recurso de grupo que permite agrupar permissoes para facilitar o gerenciamento de acessos
4 - Devemos usar a Role quando damos um acesso provisorio para um usuario
5 - Policy eh um conjunto de regras que definem permissoes


# EC2


