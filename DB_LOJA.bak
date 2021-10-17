CREATE DATABASE Loja;

USE Loja;

/*1 CRIANDO AS TABELAS */
CREATE TABLE IF NOT EXISTS Produto(
cdproduto INT AUTO_INCREMENT,
descricao text (80),
PRIMARY KEY (cdproduto)
);

CREATE TABLE IF NOT EXISTS Estoque (
cdproduto INT (5),
qtdeMin INT (3),
qtdeMax INT (3),
qtdeAtual INT (3),
PRIMARY KEY (cdproduto),
CONSTRAINT fk_cdproduto FOREIGN KEY(cdproduto) REFERENCES produto(cdproduto)
);

CREATE TABLE IF NOT EXISTS Cliente (
idCliente BIGINT AUTO_INCREMENT,
nome TEXT (40),
celular TEXT (11),
PRIMARY KEY (idCliente)
);

CREATE TABLE IF NOT EXISTS nota (
idnota BIGINT AUTO_INCREMENT,
nro TEXT (10),
idcliente BIGINT,
dtvenda DATE,
PRIMARY KEY (idnota),
CONSTRAINT fk_idcliente FOREIGN KEY (idCliente) REFERENCES cliente(idCliente)
);

CREATE TABLE IF NOT EXISTS Nota_log(
id BIGINT AUTO_INCREMENT,
idnota BIGINT,
nro TEXT (10),
idcliente BIGINT,
dtvenda DATE,
DtHora_evento DATETIME,
PRIMARY KEY (id)
);

CREATE TABLE IF NOT EXISTS itensnota (
id BIGINT AUTO_INCREMENT,
idnota BIGINT,
cdproduto INT (5),
vlUnitario DECIMAL (10,2),
Qtde DECIMAL (4,1),
PRIMARY KEY (Id),
CONSTRAINT fk_idnota FOREIGN KEY (idnota) REFERENCES nota(idnota)  
CONSTRAINT fk_idnota FOREIGN KEY (cdproduto) REFERENCES produto(codproduto)   
);

CREATE TABLE IF NOT EXISTS ItensVenda (
	Venda		INT,
	Produto	VARCHAR(3),
	Quantidade	INT
);
/*1 INSERINDO DADOS PARA TESTE*/
INSERT INTO Cliente VALUES (default,'Emerson',51999999999);
INSERT INTO Cliente VALUES (default,'Barcelos',51888888888);
INSERT INTO nota VALUES (default,'12345',1,'2021-06-01');
INSERT INTO nota VALUES (default,'12367',2,'2021-07-02');

/*1 CRIANDO UM TRIGGER
CREATE TRIGGER tr_deletelog AFTER DELETE
ON nota
FOR EACH ROW
INSERT INTO nota_log (idnota,nro,idcliente,dtvenda,DtHora_evento) 
VALUES (old.idnota,old.Nro,OLD.idcliente,OLD.Dtvenda,NOW());

/*2 APÓS A CRIAÇÃO DA TRIGGER, A CADA EXCLUSÃO DE REGISTRO DA TABELA NOTA, SERÁ FEITO UM REGISTRO NA TABELA
NOTA_LOG COM TODOS OS DADOS APAGADOS E COM INFORMAÇÃO DE DATA E HORA ATUAL DO SERVIDOR.*/
