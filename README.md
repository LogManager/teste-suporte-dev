# Teste de Programação - Etiquetas de Entrega

Este é um teste de programação que consiste em desenvolver um sistema para um vendedor de e-commerce e marketplace que precisa criar etiquetas de entrega para seus pedidos e selecionar a transportadora desejada. O sistema atual não permite essa seleção e envia automaticamente as etiquetas para a primeira transportadora cadastrada.

## Problema

O sistema atual apresenta a seguinte limitação:
- Não é possível selecionar a transportadora ao criar uma etiqueta de entrega.

## Solução Proposta

A solução proposta consiste em desenvolver um novo sistema com as seguintes funcionalidades:
- Permitir que o vendedor selecione a transportadora desejada ao criar uma etiqueta de entrega.
- Armazenar as informações das etiquetas de entrega, incluindo o vendedor, a transportadora, o pedido e a data de envio.

Além disso, será necessário criar uma documentação detalhada para orientar os clientes sobre como utilizar o sistema.

## Tecnologias Utilizadas

- Linguagem de Programação: [Informe a linguagem de programação utilizada]
- Banco de Dados: [Informe o banco de dados utilizado, se aplicável]
- Frameworks ou Bibliotecas: [Informe quaisquer frameworks ou bibliotecas adicionais utilizadas]

## Requisitos

- [Liste aqui os requisitos específicos do sistema que precisam ser atendidos]

## Como Executar o Projeto

1. Faça o clone deste repositório.
2. [Adicione aqui as instruções para configurar o ambiente de desenvolvimento, se aplicável]
3. [Adicione aqui as instruções para instalar as dependências, se aplicável]
4. [Adicione aqui as instruções para executar o projeto]

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
