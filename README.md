
# Trabalho-POO — Locadora de Veículos

Sistema de locadora de veículos em Java, executado pelo terminal. Projeto desenvolvido para praticar os conceitos de Programação Orientada a Objetos.

## Funcionalidades

Menu interativo com as opções:

1. **Incluir** um veículo (carro ou moto)
2. **Alterar** modelo, ano e valor da diária de um veículo
3. **Excluir** um veículo pela placa
4. **Listar** todos os veículos, ordenados por ano
5. **Buscar** um veículo pela placa
0. **Sair**

O sistema já inicia com 4 veículos cadastrados (3 carros e 1 moto).

## Cálculo da diária

**Carros**, de acordo com a categoria:

| Categoria | Valor final da diária |
|-----------|-----------------------|
| Suv       | diária + R$ 40        |
| Picape    | diária + R$ 50        |
| Sedan     | diária + R$ 20        |
| Hatch     | diária (sem acréscimo)|

**Motos**: se a cilindrada for maior que 500, a diária tem acréscimo de 30%. Caso contrário, vale o valor base.

## Estrutura do projeto

```
Aplicacao/
  Programa.java              # Classe principal (main)
Entidades/
  Veiculo.java               # Classe abstrata base
  Carro.java                 # Herda de Veiculo
  Moto.java                  # Herda de Veiculo
  Motor.java                 # Potência e combustível
Servicos/
  Locadora.java              # Menu e regras de interação com o usuário
  Repositorio.java           # Interface do repositório
  RepositorioVeiculos.java   # Implementação com ArrayList
```

## Conceitos de POO aplicados

- **Herança**: `Carro` e `Moto` estendem `Veiculo`
- **Classe abstrata**: `Veiculo` define `calcularDiaria()` e `getTipo()`
- **Polimorfismo**: cada tipo de veículo calcula a diária à sua maneira
- **Interface**: `Repositorio` é implementada por `RepositorioVeiculos`
- **Composição**: todo `Veiculo` possui um `Motor`
- **Encapsulamento**: atributos privados com getters e setters

## Como executar

Requisitos: JDK instalado (testado com o JDK 26).

**Pela IDE (IntelliJ):** abra o projeto, marque a pasta com os pacotes como *Sources Root* e execute `Aplicacao/Programa.java`.

**Pelo terminal**, na raiz do projeto:

```bash
javac Aplicacao/*.java Entidades/*.java Servicos/*.java
java Aplicacao.Programa
```

