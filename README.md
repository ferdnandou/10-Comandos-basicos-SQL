# Gerenciamento de Vendas de Cursos

Este projeto contém um script SQL para gerenciar vendas de cursos. O script abrange a criação de um banco de dados, uma tabela para armazenar informações sobre vendas, a inserção de registros, consultas básicas, e operações de atualização e exclusão.

## Estrutura do Projeto

- **script.sql**: Contém o código SQL para a criação do banco de dados, tabela, inserção de dados, consultas, atualizações e exclusões.
- **.gitignore**: Arquivo para ignorar arquivos e pastas que não devem ser rastreados pelo Git.
- **README.md**: Este arquivo de documentação.

## Funcionalidades

- **Criação de Banco de Dados**: Cria um banco de dados chamado `Curso`.
- **Criação de Tabela**: Cria uma tabela `Vendas` para armazenar informações de vendas.
- **Inserção de Dados**: Insere registros na tabela `Vendas`.
- **Consultas SQL**: Recupera dados específicos da tabela `Vendas`.
- **Atualização de Dados**: Altera valores de registros existentes.
- **Exclusão de Dados**: Remove registros específicos ou todos os registros da tabela.

## Como Usar

1. Clone este repositório para a sua máquina local:
    ```bash
    git clone https://github.com/seu-usuario/nome-do-repositorio.git
    ```
2. Navegue até o diretório do projeto:
    ```bash
    cd nome-do-repositorio
    ```
3. Execute o script SQL em um sistema de gerenciamento de banco de dados como MySQL ou MariaDB:
    ```sql
    source script.sql;
    ```

## Exemplo de Uso

O script SQL realiza as seguintes operações:

```sql
-- Criação do banco de dados e seleção
CREATE DATABASE Curso;
USE Curso;

-- Criação da tabela Vendas
CREATE TABLE Vendas(
    ID_Vendas INT,
    Curso VARCHAR(100),
    Aluno VARCHAR(100),
    Estado VARCHAR(100),
    Valor DECIMAL(10,2)
);

-- Inserção de registros
INSERT INTO Vendas(ID_Vendas, Curso, Aluno, Estado, Valor)
VALUES
(1, 'Excel', 'João', 'SP', 100),
(2, 'VBA', 'Lucas', 'RJ', 50),
(3, 'Excel', 'Alice', 'SP', 100),
(4, 'Excel', 'Pedro', 'PE', 100),
(5, 'VBA', 'Amanda', 'BA', 50),
(6, 'Power BI', 'Rita', 'RS', 80),
(7, 'Excel', 'Julia', 'RJ', 100),
(8, 'Power BI', 'Caio', 'SP', 80),
(9, 'Power BI', 'Lara', 'MG', 80),
(10, 'Excel', 'Rogério', 'AC', 100);

-- Consultas e manipulações
SELECT * FROM Vendas;
SELECT Aluno, Curso, Valor FROM Vendas;
SELECT * FROM Vendas ORDER BY Aluno;
SELECT * FROM Vendas WHERE Estado = 'RJ';

-- Atualização de registros
UPDATE Vendas SET Valor = 150 WHERE Curso = 'VBA';

-- Exclusão de registros
DELETE FROM Vendas WHERE ID_Vendas = 10;

-- Limpeza da tabela
TRUNCATE TABLE Vendas;
