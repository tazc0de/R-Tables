# Plantamp

<svg id="Camada_1" data-name="Camada 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1920 1080"><defs><style>.cls-1{fill:#00a994;}.cls-2{fill:#a4e786;}.cls-3{font-size:188.95px;font-family:VayuSans-SemiBold, Vayu Sans;font-weight:600;}.cls-4{letter-spacing:-0.08em;}</style></defs><title>Sem título-1</title><path class="cls-1" d="M520,797H421c.11-2.49-1.44-4.39-2.43-6.45q-27-56-54.11-111.92C346,640.5,338.55,600.46,343.87,558.3c6.87-54.32,30.42-100.2,72-135.76,48.68-41.61,96.11-84.44,139-132.09,1.51-1.68,3.67-2.93,4.09-5.45h1c9.49,12.62,19.12,25.13,28.43,37.87,25.86,35.38,46.92,73.29,60.16,115.26-1.87.67-3.7,1.46-5.61,2-19.44,5.26-38.81,10.85-58.36,15.65-95.54,23.43-164.43,110.38-162.91,211,.6,39.32.08,78.65.14,118,0,3.59-1.62,9.13.81,10.33,3.09,1.54,6.46-2.94,9.51-5a1063.51,1063.51,0,0,0,133.1-109.34c60.92-58.61,114.72-123,158.39-195.58a767.84,767.84,0,0,0,44.94-87.49c1.21.91,1.18,2.31,1.44,3.6,1.82,9.13,3.61,18.28,5.49,27.4,10.38,50.29,14.36,100.87,5.48,151.8C764.62,674.39,713,739.86,623.19,774c-31.79,12.08-64.91,18.34-98.73,21.2C522.92,795.29,520.56,794.21,520,797Z"/><path class="cls-2" d="M648.59,438.13c17.21-4.34,34-10.11,50.78-15.76,21.69-7.28,43.08-15.4,64.31-23.93,1.46-.58,3-2.49,4.92-.8a767.84,767.84,0,0,1-44.94,87.49c-43.67,72.58-97.47,137-158.39,195.58a1063.51,1063.51,0,0,1-133.1,109.34c-3.05,2.1-6.42,6.58-9.51,5-2.43-1.2-.8-6.74-.81-10.33-.06-39.33.46-78.66-.14-118-1.52-100.64,67.37-187.59,162.91-211,19.55-4.8,38.92-10.39,58.36-15.65C644.89,439.59,646.72,438.8,648.59,438.13Z"/><text class="cls-3" transform="translate(845.54 662.97)">PLAN<tspan class="cls-4" x="411.71" y="0">T</tspan><tspan x="504.48" y="0">AMP</tspan></text></svg>

## Administração do Web Server

O web server Plantamp disponibiliza uma interface para administração.<br>
Para acessá-la, clique no endereço: https://plantamp.herokuapp.com/admin.<br>
<br>Efetue o login com as suas credenciais de acesso. Após o login, você será redirecionado para a interface de administração do sistema `1`.



### `• 1` Módulos de Administração 

Módulos disponibilizados: Groups `1.1`, Users `1.2` e Sequences `1.3`.

#### ► `1.1` Módulo Groups

O módulo Groups é usado para criação de grupos de permissões, também chamados de cargos, no web server. Os cargos determinam quais recursos de administração do web server um determinado usuário interno tem acesso. 

#### ► `1.2` Módulo Users

O módulo Users é usado para o gerenciamento dos usuários internos do web server. Dentre as ações de gerenciamento estão: criação de novas contas de usuário e alteração de suas respectivas permissões. 

#### ► `1.3` Módulo Sequences

O módulo Sequences é usado para atualização das sequência de peptídeos do webserver. Através desse módulo é possível adicionar novos peptídeos ao banco de dados e editar as informações dos peptídeos pré-armazenados através de uma interface intuitiva. O módulo também disponibiliza um importador e um exportador de dados. 

### `• 2` Importador de Dados

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
