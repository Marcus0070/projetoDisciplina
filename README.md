# projetoDisciplina

1. Título
Meu Bolso – Aplicativo de Controle Financeiro Pessoal

2. Equipe
- Integrante 1: Marcus Luan Alves Pinheiro
  
3. Objetivo
Desenvolver um aplicativo mobile que ajude os usuários a organizar suas finanças pessoais, permitindo registrar entradas e saídas de dinheiro, acompanhar gastos e visualizar o saldo disponível.

O objetivo principal é facilitar o controle financeiro e ajudar as pessoas a terem mais consciência sobre como utilizam seu dinheiro.

4. Público-alvo
O aplicativo será destinado a:
- Estudantes.
- Jovens que estão começando a administrar o próprio dinheiro.
- Pessoas que desejam controlar seus gastos.
- Trabalhadores que querem organizar suas finanças pessoais.
  
5. Requisitos
Requisitos funcionais
1. Permitir cadastro e identificação do usuário.
2. Permitir registrar entradas de dinheiro.
3. Permitir registrar despesas.
4. Permitir editar e excluir lançamentos.
5. Exibir o saldo total disponível.
6. Organizar despesas por categorias.
7. Mostrar histórico de movimentações.
8. Exibir relatórios de gastos.
   
Requisitos não funcionais
1. Interface simples e intuitiva.
2. Aplicativo compatível com Android.
3. Armazenamento seguro dos dados.
4. Bom desempenho durante a utilização.
5. Facilidade de manutenção e atualização.

## Diagrama de Casos de Uso

```mermaid
flowchart TD
    A[Comerciante] --> B((Cadastrar cliente))
    A --> C((Editar cliente))
    A --> D((Excluir cliente))
    A --> E((Registrar compra))
    A --> F((Consultar conta))
    A --> G((Registrar pagamento))
    A --> H((Calcular juros))
    A --> I((Consultar histórico))
    A --> J((Encerrar conta))
    A --> K((Gerar relatório))
```
## Diagrama de Classes

```mermaid
classDiagram
    direction TB

    class Usuario {
        +int id
        +String nome
        +String email
        +String senha
        +entrar()
        +cadastrar()
        +sair()
    }

    class Cliente {
        +int id
        +String nome
        +String telefone
        +cadastrar()
        +editar()
        +excluir()
    }

    class Conta {
        +int id
        +double saldo
        +String status
        +calcularTotal()
        +atualizarSaldo()
        +encerrarConta()
    }

    class Compra {
        +int id
        +double valor
        +String descricao
        +DateTime data
        +registrarCompra()
        +calcularJuros()
    }

    class Pagamento {
        +int id
        +double valor
        +DateTime data
        +registrarPagamento()
        +abaterDivida()
    }

    class Juros {
        +int id
        +double taxa
        +int prazo
        +calcularJuros()
        +atualizarTaxa()
    }

    class Relatorio {
        +int id
        +String periodo
        +double totalRecebido
        +double totalPendente
        +gerarRelatorio()
        +consultarRelatorio()
    }

    Usuario "1" --> "0..*" Cliente : gerencia
    Cliente "1" --> "1" Conta : possui
    Conta "1" --> "0..*" Compra : registra
    Conta "1" --> "0..*" Pagamento : recebe
    Compra "0..*" --> "1" Juros : aplica
    Usuario "1" --> "0..*" Relatorio : gera
```

7. Organização da equipe para desenvolvimento
Marcus Luan Alves Pinheiro
Desenvolvimento das telas e interface
Cadastro e gerenciamento das movimentações
Banco de dados, relatórios e testes
