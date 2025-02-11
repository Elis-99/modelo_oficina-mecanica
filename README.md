# Modelo ER para Oficina Mecânica

Este repositório contém o diagrama Entidade-Relacionamento (ER) de um sistema de gerenciamento de ordens de serviço (OS) para uma oficina mecânica. O modelo foi desenvolvido para atender aos seguintes requisitos:
- Cadastro de clientes e veículos.
- Designação de equipes de mecânicos para execução de serviços.
- Cálculo de valores com base em serviços e peças utilizadas.
- Rastreamento de status e conclusão das ordens de serviço.

## Diagrama ER

(![modeloER_oficina](https://github.com/Elis-99/modelo_oficina-mecanica/blob/main/modeloER_oficina.png)
)

### Legenda das Cores
- **Tabelas Verdes**: Representam as **entidades principais** do sistema.
- **Tabelas Amarelas**: Representam **entidades de relacionamento muitos-para-muitos** (tabelas associativas).

## Estrutura do Banco de Dados

### Entidades Principais (Tabelas Verdes)
1. **`cliente`**:
   - Armazena informações dos clientes da oficina.
   - Atributos: `id_cliente`, `nome`, `telefone`, `endereco`.

2. **`veiculo`**:
   - Registra os veículos dos clientes.
   - Atributos: `id_veiculo`, `placa`, `marca`, `modelo`, `ano`, `id_cliente` (FK).

3. **`mecanico`**:
   - Contém dados dos mecânicos da oficina.
   - Atributos: `id_mecanico`, `nome`, `endereco`, `especialidade`.

4. **`equipe`**:
   - Representa as equipes de mecânicos.
   - Atributos: `id_equipe`, `nome_equipe`.

5. **`ordem_servico`**:
   - Gerencia as ordens de serviço.
   - Atributos: `id_os`, `data_emissao`, `data_conclusao`, `valor_total`, `status`, `id_veiculo` (FK), `id_equipe` (FK).

6. **`servico`**:
   - Lista os serviços disponíveis na oficina.
   - Atributos: `id_servico`, `descricao`, `valor_mao_de_obra`.

7. **`peca`**:
   - Registra as peças utilizadas nos serviços.
   - Atributos: `id_peca`, `nome`, `valor`.

### Tabelas de Relacionamento (Tabelas Amarelas)
1. **`equipe_mecanico`**:
   - Relaciona mecânicos a equipes.
   - Atributos: `id_equipe` (FK), `id_mecanico` (FK).

2. **`os_servico`**:
   - Relaciona ordens de serviço a serviços.
   - Atributos: `id_os` (FK), `id_servico` (FK).

3. **`servico_peca`**:
   - Relaciona serviços a peças.
   - Atributos: `id_servico` (FK), `id_peca` (FK), `quantidade`.

## Relacionamentos
- Um **cliente** pode ter vários **veículos**.
- Um **veículo** pode ter várias **ordens de serviço**.
- Uma **equipe** pode estar associada a várias **ordens de serviço**.
- Um **mecânico** pode pertencer a várias **equipes**.
- Uma **ordem de serviço** pode incluir vários **serviços**.
- Um **serviço** pode utilizar várias **peças**.

## Como Visualizar
- **Diagrama**: Veja o diagrama completo no arquivo [[modeloER_oficina.pdf](https://github.com/user-attachments/files/18751430/modeloER_oficina.pdf)
). 
---

Desenvolvido por [Elisangela Sena].
