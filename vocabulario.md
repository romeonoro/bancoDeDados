# 🎲 Trabalho Final de Projeto de Banco de Dados

## 1️⃣ Significado das expressões abaixo

###	SGBD
> Sistema Gerenciador de Banco de Dados é um software projetado para permitir a criação, manipulação e administração de bancos de dados. Esses sistemas são essenciais para organizar grandes quantidades de dados de forma eficiente e segura, fornecendo uma interface entre usuários e o próprio banco de dados.

###	🔒 Restrições em Banco de Dados
> Restrições em bancos de dados são regras que definem as condições ou limitações impostas aos dados armazenados, garantindo a integridade, consistência e validade dos mesmos. Elas são aplicadas para assegurar que apenas dados corretos e apropriados sejam inseridos e mantidos no banco de dados. 

###	🔗 Modelo Relacional
> É um modelo de dados utilizado para organizar informações em bancos de dados de forma estruturada e relacionada.


###	🌐 Modelagem Conceitual
> Processo de representar os requisitos e as entidades principais de um sistema de informação de forma abstrata e independente de qualquer implementação técnica específica. É uma etapa crucial no desenvolvimento de sistemas de informação, pois visa capturar e definir as entidades de negócio, seus relacionamentos e as regras de negócio subjacentes.
 
 
###	Modelagem Lógica
> Transformação do modelo conceitual em um modelo de dados específico para um SGBD, considerando os detalhes de implementação.

###	Modelagem Física
> Implementação do modelo lógico em um SGBD específico, definindo detalhes como tipos de dados, índices, estruturas de armazenamento físico, etc.

###	Linguagem SQL
> Linguagem padrão para consultar e manipular bancos de dados relacionais.

###	Data Definition Language (DDL)
> Parte da SQL que permite definir e modificar a estrutura de objetos em um banco de dados, como tabelas e índices.

###	Data Manipulation Language (DML)
> Parte da SQL usada para manipular os dados dentro de objetos do banco de dados, como inserir, atualizar, deletar registros.

###	Boas práticas em modelagem de banco de dados
>


## 2️⃣ Responda as questões

# Todos os clientes armazenados no sistema:
	SELECT * FROM cliente;	

# Exiba os veículos que tenham final 3 no número da placa.
	SELECT * FROM veiculo WHERE placa LIKE '%3';

# Mostre os clientes que residem no RS e que não possuam telefone.
	SELECT * FROM cliente WHERE uf_cnh = 'RS' AND telefone IS NULL;

# Exiba o código dos clientes que alugaram veículos por mais de 90 dias.
	SELECT id_cliente FROM contrato_aluguel WHERE duracao > 90;

# Quantos veículos há cadastrados no sistema.
	SELECT COUNT(*) AS total_veiculos FROM veiculo;
 
# Mostre o veículo alugado por Alexandre Zamberlan.
	SELECT v.* 
	FROM veiculo v
	JOIN contrato_aluguel ca ON v.id_veiculo = ca.id_veiculo
	JOIN cliente c ON ca.id_cliente = c.id_cliente
	WHERE c.nome = 'Alexandre Zamberlan';

# Mostre os clientes e os escritórios associados no contrato de aluguel.
	SELECT c.nome AS cliente, e.nome AS escritorio
	FROM contrato_aluguel ca
	JOIN cliente c ON ca.id_cliente = c.id_cliente
	JOIN escritorio e ON ca.id_escritorio = e.id_escritorio;
