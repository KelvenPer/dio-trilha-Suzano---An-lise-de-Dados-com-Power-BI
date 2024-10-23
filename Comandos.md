CREATE DATABASE firstExample;
USE firstExample;

create table periodicos (
id INT AUTO_INCREMENT PRIMARY KEY,     # o auto increment ele sempre adiciona um valor ao meu ID ao adicionar um novo valor na tabela
nome_periodico varchar(100),
issn INT, 
id_editora INT
);

CREATE TABLE editora(
id INTEGER AUTO_INCREMENT,
nome_editora VARCHAR(120) UNIQUE,    #unique serve para nao repetir dados entre as tabelas
pais VARCHAR(5),
PRIMARY KEY(id)
);


ALTER TABLE periodicos ADD CONSTRAINT fk_editora_periodico FOREIGN KEY (id_editora) REFERENCES editora(id); # na linha abaixo vamos criar uma relação entre ID da tabela editora com o ID da tabela periodicos 

INSERT INTO editora(nome_editora, pais) VALUES ('IEEE', 'EUA'), ('DataScienceMagazine', 'EUA');
INSERT INTO editora(nome_editora, pais) VALUES ('Bancroft', 'EUA'), ('AK Press', 'EUA')

INSERT INTO periodicos (nome_periodico, issn, id_editora) VALUES('Speciel Issue', '15485687', '1')
INSERT INTO periodicos (nome_periodico, issn, id_editora) VALUES('Speciel Issue', '15485687', '5')   # aqui vemos o fk e constraint sendo usada porque ela permite nao colocar dados que nao exite dentro da tabela 
INSERT INTO periodicos (nome_periodico, issn, id_editora) VALUES('Speciel Issue_2', '16985745', '4')   # agora o valor é inserido corretamente


