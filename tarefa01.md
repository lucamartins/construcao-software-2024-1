# Rest API

O termo "Rest API" se refere à uma série de regras e convenções que guiam o desenvolvimento de API's na web. Elucidando um pouco mais, "REST", por sí só, se refere a uma arquitetura de software, então quando fala-se de "Rest API", queremos dizer a implementação dessa arquitetura no desenvolvimento de API's web. Os conceitos envolvidos tangem muito na definição de como a __comunicação__ entre sistemas de softwares deve ser orquestrada, tendo como fim benefícios promovidos pela implementação da arquitetura, como um maior potencial de escalabilidade, menor complexidade de uso e alta confiabilidade.

## Principais características

### Interface bem definida

Uma API Rest tem, por padrão arquitetural, uma interface de uso muito bem definida. Dentro do conceito, tudo que é manipulado e gerenciado pelo serviço, é definido como recurso, que, por sua vez, possui uma maneira única de ser consumido por outra aplicação. Cada recurso dentro de uma API possui um identificador universal dentro daquele contexto de negócio, que é utilizado para a aplicação cliente obter o recurso sob demanda. Além disso, na representação do recurso enviada ao cliente, todos os dados tangentes e necessários são definidos, de tal forma que o cliente satisfaça a necessidade de negócio a partir daquela representação.

### Convenção de métodos HTTP

Dentro da arquitetura, é definido uma convenção para a comunicação HTTP, que relaciona os diferentes tipos de verbos com o propósito daquela ação. Para clarificar:
- GET: utilizado para obter a representação de um recurso
- POST: utilizado para criar um novo recurso
- PUT: utilizado para modificar (por completo - sobrescrição) um recurso
- PATCH: utilizado para atualizar parcialmente um recurso
- DELETE: utilizado para apagar um recurso

### Convenção de status de uma requisição HTTP

Além da convenção dos métodos HTTP, uma API Rest tem padronizado no resultado de suas chamadas o status de uma requisição. O status é de suma importância para o cliente saber lidar, sobretudo, em situações de falhas ou cenários atípicos.
- 200: requisição satisfeita
- 201: recurso criado com sucesso
- 400: chamada com erro (comumente indica que tem algum problema na especificação da requisição)
- 404: recurso inexistente - não encontrado
- 500: falha interna (comumente houve alguma falha interna na API que não foi corretamente tratada)
- 401: falha na verificação da autenticação do cliente
- 403: falha na verificação da autorização do cliente para acessar aquele recurso

### Sem estado

Uma API Rest não armazena o estado de comunicação com um cliente que à está consumindo. Nesse sentido, a cada nova requisição, estarão presentes todos as informações necessárias para entendimento do contexto e solução daquela requisição. Exemplo disso é a maneira como uma API Rest identifica se o cliente está autenticado/autorizado para prosseguir com a resolução de uma requisição. Existem diferentes maneiras de uma API tratar isso, mas uma delas é a autenticação através do Header HTTP de autorização, comumente passando um token, à título de exemplo, JWT, que carrega com si todas as informações necessárias para que a API possa entender o estado de autenticação daquele cliente.

### Representação dos dados

É definido e padronizado, dentro de uma API Rest, como os recursos serão representados. As duas formas mais utilizadas são a representação por JSON e por XML. O cliente pode ainda, nos headers de uma requisição, especificar esse formato de representação, e será esperado que a resposta construída pela API siga a definição imposta. Essa característica impulsiona a facilidade com que sistemas WEB podem conversar entre si, já que, por convenção, é esperado uma estrutura de dados previamente conhecida e processável pela aplicação.
