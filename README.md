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
    A[Usuário] --> B((Cadastrar conta))
    A --> C((Fazer login))
    A --> D((Consultar saldo))
    A --> E((Registrar receita))
    A --> F((Registrar despesa))
    A --> G((Editar lançamento))
    A --> H((Excluir lançamento))
    A --> I((Consultar histórico))
    A --> J((Visualizar relatórios))
    A --> K((Gerenciar categorias))
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
        +cadastrar()
        +fazerLogin()
        +editarPerfil()
    }

    class Movimentacao {
        +int id
        +double valor
        +String descricao
        +DateTime data
        +editar()
        +excluir()
    }

    class Receita {
        +int id
        +double valor
        +registrarReceita()
    }

    class Despesa {
        +int id
        +double valor
        +registrarDespesa()
    }

    class Categoria {
        +int id
        +String nome
        +String tipo
        +cadastrarCategoria()
        +editarCategoria()
    }

    class Relatorio {
        +int id
        +double totalReceitas
        +double totalDespesas
        +double saldo
        +gerarRelatorio()
    }

    class BancoDeDados {
        +conectar()
        +salvarDados()
        +buscarDados()
        +excluirDados()
    }

    Movimentacao <|-- Receita
    Movimentacao <|-- Despesa
    Usuario "1" --> "0..*" Movimentacao : registra
    Categoria "1" --> "0..*" Movimentacao : classifica
    Usuario "1" --> "0..*" Categoria : gerencia
    Usuario "1" --> "0..*" Relatorio : consulta
    BancoDeDados ..> Usuario : armazena
    BancoDeDados ..> Movimentacao : armazena
    BancoDeDados ..> Categoria : armazena
```

7. Organização da equipe para desenvolvimento
Marcus Luan Alves Pinheiro
Desenvolvimento das telas e interface
Cadastro e gerenciamento das movimentações
Banco de dados, relatórios e testes
