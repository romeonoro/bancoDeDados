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
>
###	Modelagem Física
>
###	Linguagem SQL
>
###	Data Definition Language (DDL)
>
###	Data Manipulation Language (DML)
>
###	Boas práticas em modelagem de banco de dados
>

## 2️⃣ Responda as questões

# Todos os clientes armazenados no sistema:
	SELECT *
	FROM Clientes;	



# Exiba os veículos que tenham final 3 no número da placa.
SELECT *
FROM Veiculos
WHERE Placa LIKE '%3';


# Mostre os clientes que residem no RS e que não possuam telefone.
SELECT *
FROM Clientes
WHERE Estado = 'RS'
AND Telefone IS NULL;


# Exiba o código dos clientes que alugaram veículos por mais de 90 dias.
SELECT DISTINCT CodigoCliente
FROM ContratosAluguel
WHERE DATEDIFF(dia_inicio, dia_fim) > 90;


# Quantos veículos há cadastrados no sistema.
SELECT COUNT(*)
FROM Veiculos;


# Mostre o veículo alugado por Alexandre Zamberlan.
SELECT *
FROM Veiculos V
JOIN ContratosAluguel CA ON V.IDVeiculo = CA.IDVeiculo
JOIN Clientes C ON CA.CodigoCliente = C.CodigoCliente
WHERE C.NomeCliente = 'Alexandre Zamberlan';


# Mostre os clientes e os escritórios associados no contrato de aluguel.
SELECT C.*, E.NomeEscritorio
FROM Clientes C
JOIN ContratosAluguel CA ON C.CodigoCliente = CA.CodigoCliente
JOIN Escritorios E ON CA.IDEscritorio = E.IDEscritorio;


