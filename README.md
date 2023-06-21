# Demonstração de DAO com JDBC

Neste projeto, é implementada uma camada de acesso a dados para um pequeno sistema de vendedores e departamentos. A aplicação utiliza JDBC para acesso ao banco de dados MySQL.


## JDBC 
O JDBC, que significa Java Database Connectivity, é uma API padrão do Java para acesso a dados. É uma biblioteca incorporada ao Java que nos permite programar o acesso a dados de forma unificada para diferentes bancos de dados relacionais. O JDBC está presente nos pacotes java.sql e javax.sql (este último é uma API suplementar para servidores).

O JDBC depende do conector específico do banco de dados em uso para estabelecer a comunicação com ele. Se não estivermos usando um gerenciador de dependências, é necessário baixar e adicionar o conector como uma biblioteca externa do Java.

Neste exemplo, foram realizadas as seguintes etapas:

 - Criado um arquivo chamado db.properties, contendo os dados de conexão com o banco de dados.
 - Criada uma classe chamada DB, a partir da qual implementaremos a conexão/desconexão com o banco de dados, utilizando os dados informados no arquivo db.properties.
Em nossa aplicação, faremos uso frequente de três classes da API JDBC: Statement, PreparedStatement e ResultSet.

## DAO
O padrão de projeto DAO (Data Access Object) é utilizado para cada entidade do projeto, definindo um objeto responsável pelo acesso aos dados relacionados a essa entidade. Por exemplo, teremos um objeto ClienteDao responsável pelo acesso aos dados dos clientes, um objeto ProdutoDao responsável pelo acesso aos dados dos produtos e assim por diante.

Cada DAO é representado por uma interface. A escolha de uma interface permite que o modo de acesso a dados seja alterado posteriormente ou que sejam usados diferentes bancos de dados. A injeção de dependência é realizada por meio do padrão de projeto Factory nesse exercício. A interface ClienteDAO define os métodos/operações que podem ser realizados com os dados da entidade Cliente. Em seguida, temos uma classe que implementa essa interface e implementa todas as operações definidas por ela. O mesmo padrão se aplica às outras entidades do projeto.
