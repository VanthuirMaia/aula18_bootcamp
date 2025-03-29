
# Projeto de Integração com API - Pokémon

Este projeto tem como objetivo praticar o uso de APIs, coletando dados em formato JSON, transformando-os em dicionários e, em seguida, filtrando e limpando os dados antes de armazená-los no banco de dados. O foco está na eficiência no uso de recursos, economizando o uso de banco de dados ao processar os dados antes de salvar.

## Descrição

O projeto consome dados da [Pokémon API](https://pokeapi.co/) para obter informações sobre Pokémon. Ele realiza o seguinte processo:

1. **Consome a API**: Utiliza requisições HTTP para acessar a API pública do Pokémon e obter dados sobre diversos Pokémons.
2. **Transforma os dados JSON**: Os dados retornados pela API são em formato JSON e são convertidos em dicionários Python.
3. **Filtragem e Limpeza**: Antes de armazenar os dados no banco de dados, realiza-se uma limpeza para garantir que apenas as informações necessárias sejam salvas, otimizando o uso do banco de dados.
4. **Armazenamento no Banco de Dados**: Os dados filtrados são salvos no banco de dados, economizando espaço e recursos ao evitar salvar dados desnecessários.

## Funcionalidades

- **Busca de Pokémon por ID**: É possível buscar informações de um Pokémon específico usando o ID da API.
- **Armazenamento no Banco de Dados**: Após a limpeza e filtragem dos dados, os mesmos são armazenados em um banco de dados SQL.
- **Eficiência**: Apenas os dados essenciais são salvos, minimizando o uso de espaço no banco de dados.

## Tecnologias Utilizadas

- **Python**: Linguagem principal utilizada para o desenvolvimento do projeto.
- **Pydantic**: Para a validação de dados e criação de modelos de dados.
- **SQLAlchemy**: Para interação com o banco de dados e manipulação de dados.
- **Requests**: Para realizar requisições HTTP à API externa.
- **Banco de Dados SQL**: Qualquer banco de dados SQL pode ser utilizado, como PostgreSQL, MySQL ou SQLite.

## Estrutura do Projeto

```bash
aula18_bootcamp/
│
├── src/
│   ├── __init__.py            # Marca o diretório como pacote
│   ├── main.py                # Arquivo principal, onde o processo de obtenção e armazenamento ocorre
│   ├── controller.py          # Controlador responsável por interagir com a API e filtrar os dados
│   ├── db.py                  # Configurações do banco de dados e mapeamento de tabelas
│   ├── schema.py              # Definição dos schemas de validação de dados com Pydantic
│   ├── models.py              # Definição das classes do banco de dados com SQLAlchemy
└── .venv/                     # Ambiente virtual para dependências
```

## Como Executar

1. **Clone o repositório**:

   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd aula18_bootcamp
   ```

2. **Crie um ambiente virtual**:

   No diretório raiz do projeto, execute:

   ```bash
   python -m venv .venv
   ```

3. **Instale as dependências**:

   Com o ambiente virtual ativado, execute:

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure o Banco de Dados**:

   Certifique-se de que o banco de dados está configurado corretamente no arquivo `db.py`.

5. **Execute o projeto**:

   A partir do diretório raiz, execute:

   ```bash
   python -m src.main
   ```

## Como Funciona

1. **Obter Dados da API**: O arquivo `controller.py` contém a função que consulta a API pública do Pokémon e recupera os dados em formato JSON.
2. **Transformar em Dicionário**: O JSON retornado é convertido em um dicionário Python para fácil manipulação.
3. **Filtragem e Limpeza**: A filtragem ocorre para que apenas as informações relevantes (como nome e tipo) sejam extraídas.
4. **Salvar no Banco de Dados**: O banco de dados armazena apenas os dados filtrados, minimizando o uso de espaço e recursos.

## Exemplo de Uso

Após rodar o código, você verá a seguinte saída no terminal:

```bash
Pokemon: Caterpie, Type: Bug
Pokemon: Bulbasaur, Type: Grass, Poison
Pokemon: Charmander, Type: Fire
```

Além disso, as informações dos Pokémons serão salvas no banco de dados conforme a estrutura definida no modelo.

## Dependências

- `requests`: Para fazer as requisições HTTP.
- `pydantic`: Para validação de dados.
- `sqlalchemy`: Para interação com o banco de dados.

Para instalar as dependências, basta rodar:

```bash
pip install -r requirements.txt
```

## Contribuições

Sinta-se à vontade para contribuir com o projeto! Se tiver sugestões ou encontrar algum bug, abra uma issue ou faça um pull request.

## Licença

Este projeto está licenciado sob a Licença MIT - consulte o arquivo [LICENSE](LICENSE) para mais detalhes.
