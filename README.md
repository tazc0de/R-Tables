# Plantamp

## Administração do Web Server

O web server Plantamp disponibiliza uma interface para administração.<br>
Para acessá-la, clique no endereço: https://plantamp.herokuapp.com/admin.<br>
Efetue o login com as suas credenciais de acesso. Após o login, você será redirecionado para a interface de administração do sistema `1`.



### `• 1` Módulos de Administração 

Módulos disponibilizados: Groups `1.1`, Users `1.2` e Sequences `1.3`.

#### ► `1.1` Módulo Groups

O módulo Groups é usado para criação de grupos de permissões, também chamados de cargos, no web server. Os cargos determinam quais recursos de administração do web server um determinado usuário interno tem acesso. 

#### ► `1.2` Módulo Users

O módulo Users é usado para o gerenciamento dos usuários internos do web server. Dentre as ações de gerenciamento estão: criação de novas contas de usuário e alteração de suas respectivas permissões. 

#### ► `1.3` Módulo Sequences

O módulo Sequences é usado para atualização das sequência de peptídeos do webserver. Através desse módulo é possível adicionar novos peptídeos ao banco de dados e editar as informações dos peptídeos pré-armazenados através de uma interface intuitiva. O módulo também disponibiliza um importador e um exportador de dados. 

### `• 2`Importador de Dados

O importador possibilita carregar planilhas de dados inteiras para o banco de dados. Para tanto, a planilha deve apresentar os seguintes campos: name, sequence, organism, activity, validation, uniprot, pdb, reference e pubmed. Uma ilustração do padrão planilha pode ser visualizado abaixo.

| name | sequence | organism | activity | validation | uniprot | pdb | pubmed | reference |
|------|----------|----------|----------|------------|---------|-----|--------|-----------|
|      |          |          |          |            |         |     |        |           |

Além disso, um modelo de importação pode ser encontrado neste repositório. 


### `• 3` Organização dos Dados

Os dados armazenados no banco de peptídeos seguem uma organização específica que precisa ser mantida. Para tanto, quaisquer atualizações do banco de dados precisam assegurar o cumprimento das especificações apresentadas na tabela abaixo. As especificações de organização de dados apresentada na tabela servem tanto para atualização do banco via interface gráfica quanto via importador de dados. 

A tabela apresenta os campos que precisam ser preenchidos manualmente para armazenar novos peptídeos no banco de dados. Além disso, informa a obrigatoriedade de preenchimento de cada campo, seu respectivo tipo e valores aceitos. Por fim, apresenta um exemplo ilustrativo de como os dados devem ser organizados seguindo as especificações apresentadas. 


| Campo      | Obrigatório | Tipo do Campo | Valores Aceitos                                                                                     | Exemplo                           |
|------------|-------------|---------------|-----------------------------------------------------------------------------------------------------|-----------------------------------|
| name       |     Sim     | Monovalorado  |                                                  --                                                 | Gymnin                            |
| sequence   |     Sim     | Monovalorado  |                                                  --                                                 | KTCENLADDY                        |
| organism   |     Sim     | Multivalorado |                                                  --                                                 | Gymnocladus chinensis             |
| activity   |     Sim     | Multivalorado | Antibacterial<br>Antifungal<br>Antiparasitic<br>Antitumour<br>Antiviral<br>Insecticida<br>Not found | Antifungal, Antitumour, Antiviral |
| validation |     Sim     | Monovalorado  |                         Experimentally Validated<br>Predicted<br>Not found                          | Experimentally Validated          |
| uniprot    |     Não     | Multivalorado |                                           --<br>Not found                                           | P84200, P84201                    |
| pdb        |     Não     | Multivalorado |                                           --<br>Not found                                           | Not found                         |
| referenceª |     Sim     | Multivalorado |                                                  --                                                 | referência1##referência2          |
| pubmedª    | Sim         | Multivalorado | --<br>Not Available                                                                                 | pubmed1##pubmed2                  |

<sup>¹ Campos não obrigatórios são preenchidos por padrão com "Not found".</sup><br>
<sup>² Campos "Monovalorados" armazenam um único valor, enquanto campos "Multivalorados" podem armazenar mais de um valor. Nesse caso, os valores devem ser separados por vírgula. A exeção são os campos "reference" e "pubmed", nos quais seus valores devem ser seprados por "##".</sup><br>
<sup>ª Os campos "reference" e "pubmed" estão associados de maneira que a primeira referência se associa com o primeiro pubmed id, a segunda referência se associa com o segundo pubmed id, e assim sucessivamente. Portanto, os dois campos devem sempre armazenar o mesmo número de valores.</sup>
