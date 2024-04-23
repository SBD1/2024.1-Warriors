
# Dicionário de Dados

## Entidade: Personagem

#### A entidade Personagem é a base para outras duas entidades, nela se encontra o id do personagem e o nome.

| Campo          | Tipo    | Descrição                    | Permite valores nulos | Valores permitidos | É chave? |
|----------------|---------|------------------------------|------------------------|---------------------|----------|
| idPersonagem   | Inteiro | Identificador único do personagem | Não                | 1-1000                    | PK      |
| nome           | Texto   | Nome do personagem           | Não                    | a-z, A-Z                   |       |

### Entidade: NPC

#### A entidade NPC armazena a história do npc e também o diálogo que aparecerá no jogo.

| Campo      | Tipo    | Descrição             | Permite valores nulos | Valores permitidos | É chave? |
|------------|---------|-----------------------|------------------------|---------------------|----------|
| historia   | Texto   | História do NPC       | Sim                    | a-z, A-Z                  |       |
| dialogo    | Texto   | Diálogo do NPC        | Não                    | a-z, A-Z                  |       |

### Entidade: Player

#### A entidade Player é o jogador que vai ser jogável, nela se encontra as principais informações, como a classe, level, vida, mana, poder e defesa.

| Campo      | Tipo    | Descrição             | Permite valores nulos | Valores permitidos | É chave? |
|------------|---------|-----------------------|------------------------|---------------------|----------|
| classe     | Texto   | Classe do jogador     | Não                    | a-z, A-Z                   |       |
| level      | Inteiro | Nível do jogador      | Não                    | 1-30                  |       |
| vida       | Inteiro | Pontos de vida        | Não                    | 100-1000                  |       |
| mana       | Inteiro | Pontos de mana        | Não                    | 100-1000                   |       |
| poder      | Inteiro | Poder do jogador      | Não                    | 1-500                   |       |
| defesa     | Inteiro | Defesa do jogador     | Não                    | 1-300                   |       |

## Entidade: Monstro

#### A entidade Monstro é a base para outras duas entidades, nela se encontra o id do monstro, o nome do monstro, vida do monstro, poder do monstro e a experiência que será dropada.

| Campo          | Tipo    | Descrição                          | Permite valores nulos | Valores permitidos | É chave? |
|----------------|---------|------------------------------------|------------------------|---------------------|----------|
| idMonstro      | Inteiro | Identificador único do monstro     | Não                    | 1-1000                    | PK     |
| nomeMonstro    | Texto   | Nome do monstro                    | Não                    | a-z, A-Z                   |       |
| vidaMonstro    | Inteiro | Vida do monstro                    | Não                    | 1-20000                   |       |
| poderMonstro   | Inteiro | Poder do monstro                   | Não                    | 1-200                |       |
| expLiberado    | Inteiro | Experiência liberada ao derrotar   | Não                    | 1-500                  |       |

### Entidade: Comum

#### A entidade Comum é basicamente o monstro comum nela mostra aonde o local que esse monstro será encontrado.

| Campo           | Tipo    | Descrição                        | Permite valores nulos | Valores permitidos | É chave? |
|-----------------|---------|----------------------------------|------------------------|---------------------|----------|
| localEncontrado | Texto   | Local onde o monstro é encontrado| Não                    | a-z, A-Z                   | FK      |

### Entidade: Boss

#### A entidade Boss é o monstro mais poderoso, ou seja, quando o jogador estiver pronto enfrentará ele e ele dropa itens mais poderosos também, nela se encontra a defesa do monstro e o item que será dropado.

| Campo          | Tipo    | Descrição                     | Permite valores nulos | Valores permitidos | É chave? |
|----------------|---------|-------------------------------|------------------------|---------------------|----------|
| defesaMonstro  | Inteiro | Defesa do monstro            | Não                    | 1-200                  |       |
| itemDropado    | Inteiro   | Item dropado pelo monstro    | Sim                    | 1-1000                  |   FK    |

## Entidade: Item

#### A entidade item é basicamente o que o nome fala os itens que poderão ser usados pelo Player, nela se encontra atributos como o id do item, nome, descrição, level mínimo, poder, defesa e vida adicional.

| Campo          | Tipo    | Descrição                          | Permite valores nulos | Valores permitidos | É chave? |
|----------------|---------|------------------------------------|------------------------|---------------------|----------|
| idItem         | Inteiro | Identificador único do item        | Não                    | 1-1000                    | PK      |
| nomeItem       | Texto   | Nome do item                       | Não                    | az, A-Z                  |       |
| descricaoItem  | Texto   | Descrição do item                  | Sim                    | az, A-Z                  |       |
| levelMinimo    | Inteiro | Nível mínimo para usar o item     | Não                    | 1-30                  |       |
| poderItem      | Inteiro | Poder concedido pelo item          | Sim                    | 1-100                   |       |
| defesaItem     | Inteiro | Defesa concedida pelo item         | Sim                    | 1-150                  |       |
| vidaAdicional  | Inteiro | Vida adicional concedida pelo item | Sim                    | 1-200                   |       |

## Entidade: Recompensa

#### A entidade Recompensa é o que será dropado dos monstros quando o Player finalizá-los, nela se encontra o id da recompensa, a experiência dropada e o item dropado.

| Campo        | Tipo    | Descrição                          | Permite valores nulos | Valores permitidos | É chave? |
|--------------|---------|------------------------------------|------------------------|---------------------|----------|
| idRecompensa | Inteiro | Identificador único da recompensa  | Não                    | 1-1000                    | PK      |
| expDropado   | Inteiro | Experiência dropada                | Não                    | 1-2000                   |       |
| itemDropado  | Inteiro   | Item dropado como recompensa       | Sim                    | 1-1000                 |    FK   |

## Entidade: Missão

#### A entidade Missão é aonde está armazenado a missão que o Player terá que fazer durante suas aventuras, nela se encontra o id da missão, a descrição e a experiência da missão.

| Campo          | Tipo    | Descrição                        | Permite valores nulos | Valores permitidos | É chave? |
|----------------|---------|----------------------------------|------------------------|---------------------|----------|
| idMissao       | Inteiro | Identificador único da missão    | Não                    | 1-1000                    | PK      |
| descricaoMissão| Texto   | Descrição da missão              | Não                    | -                   |       |
| expMissao      | Inteiro | Experiência concedida pela missão| Não                    | -                   |       |

## Entidade: Mundo

#### A entidade Mundo é o lugar principal aonde estará os outros locais, nele se encontra o id do mundo, nome e a descrição do mesmo.

| Campo        | Tipo    | Descrição                    | Permite valores nulos | Valores permitidos | É chave? |
|--------------|---------|------------------------------|------------------------|---------------------|----------|
| idMundo      | Inteiro | Identificador único do mundo | Não                    | 1-1000                   | PK      |
| nomeMundo    | Texto   | Nome do mundo                | Não                    | az, A-Z                   |       |
| descricaoMundo| Texto   | Descrição do mundo           | Sim                    | az, A-Z                   |       |

## Entidade: Local

#### A entidade Local é aonde o Player irá passar a sua história, aonde os monstros estarão e outras coisas, nela se encontra o id do local, nome e tamanho do local.

| Campo        | Tipo    | Descrição                    | Permite valores nulos | Valores permitidos | É chave? |
|--------------|---------|------------------------------|------------------------|---------------------|----------|
| idLocal      | Inteiro | Identificador único do local | Não                    | 1-1000                   | PK      |
| nomeLocal    | Texto   | Nome do local                | Não                    | az, A-Z                   |       |
| tamanhoLocal | Texto   | Tamanho do local             | Não                    | az, A-Z                   |       |
