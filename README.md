# Teste de Programação - Etiquetas de Entrega

## Objetivo:
O objetivo deste teste é desenvolver um sistema que permita a um vendedor de e-commerce e marketplace criar etiquetas de entrega e selecionar a transportadora desejada para cada pedido. Atualmente, o sistema existente não oferece essa opção, enviando automaticamente as etiquetas para a primeira transportadora cadastrada.

## Problema:
O sistema atual não permite ao vendedor selecionar uma transportadora ao criar uma etiqueta de entrega. Como resultado, todas as etiquetas são enviadas apenas para a primeira transportadora cadastrada.

## Solução Proposta:
Para resolver esse problema, será desenvolvido um novo sistema que ofereça a funcionalidade de seleção de transportadora durante a criação da etiqueta de entrega. O vendedor terá a liberdade de escolher a transportadora desejada para cada pedido, melhorando a flexibilidade e eficiência do processo de envio.


## Tecnologias Utilizadas

- Linguagem de Programação: PHP, Laravel
- Banco de Dados: MySQL

## Estrutura do Banco de Dados

A seguir, estão exemplos de SQL para criar as tabelas necessárias no banco de dados:

```sql
-- Tabela: Vendedores
CREATE TABLE Vendedores (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    endereco VARCHAR(200),
    email VARCHAR(100),
    telefone VARCHAR(20)
);

-- Tabela: Transportadoras
CREATE TABLE Transportadoras (
    id INT PRIMARY KEY,
    nome VARCHAR(100),
    endereco VARCHAR(200),
    email VARCHAR(100),
    telefone VARCHAR(20)
);

-- Tabela: EtiquetasEntrega
CREATE TABLE EtiquetasEntrega (
    id INT PRIMARY KEY,
    vendedor_id INT,
    transportadora_id INT,
    pedido_id INT,
    data_envio DATE,
    FOREIGN KEY (vendedor_id) REFERENCES Vendedores(id),
    FOREIGN KEY (transportadora_id) REFERENCES Transportadoras(id)
);

-- Tabela: Pedidos
CREATE TABLE Pedidos (
    id INT PRIMARY KEY,
    vendedor_id INT,
    produto VARCHAR(100),
    quantidade INT,
    valor_total DECIMAL(10, 2),
    FOREIGN KEY (vendedor_id) REFERENCES Vendedores(id)
);

## Passos finais


