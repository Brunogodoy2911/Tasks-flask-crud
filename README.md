# ✅ API de Gerenciamento de Tarefas com Flask

Este é um projeto de **API RESTful** para gerenciamento de tarefas (_To-Do List_), desenvolvido com **Python e Flask**. A API permite realizar operações CRUD (Criar, Ler, Atualizar e Deletar) de tarefas.

> ⚠ **Nota:** A aplicação utiliza uma lista em memória para armazenar os dados. Isso significa que todas as tarefas serão perdidas ao reiniciar a aplicação.

## 🚀 Funcionalidades

- ✅ Criar uma nova tarefa  
- 📋 Listar todas as tarefas  
- 🔍 Buscar tarefa por ID  
- ✏ Atualizar título, descrição e status (`completed`)  
- ❌ Excluir tarefa  

## 🛠 Tecnologias Utilizadas

| Tecnologia | Descrição |
|------------|------------|
| Python 3   | Linguagem de programação utilizada |
| Flask      | Micro-framework web para criação da API |
| Pytest     | Biblioteca para testes automatizados |
| Requests   | Utilizada para realizar chamadas HTTP nos testes |

## ⚙️ Instalação e Execução

### 1️⃣ Clone o repositório
```bash
git clone <url-do-seu-repositorio>
cd tasks-flask-crud
```

### 2️⃣ Crie e ative o ambiente virtual
```bash
# Criar o ambiente
python -m venv venv

# Ativar no Windows
.env\Scriptsctivate

# Ativar no macOS/Linux
source venv/bin/activate
```

### 3️⃣ Instale as dependências
```bash
pip install -r requirements.txt
```

### 4️⃣ Execute a aplicação
```bash
python app.py
```

🔗 A API estará disponível em: **http://127.0.0.1:5000**

## 📡 Endpoints da API

### 📌 1. Criar Tarefa
| Método | Endpoint |
|--------|----------|
| POST   | `/tasks` |

**Body (JSON):**
```json
{
  "title": "Minha Primeira Tarefa",
  "description": "Esta é a descrição da tarefa."
}
```

**Resposta (200):**
```json
{
  "message": "Nova tarefa criada com sucesso!",
  "id": 1
}
```

### 📌 2. Listar Todas as Tarefas
| Método | Endpoint |
|--------|----------|
| GET    | `/tasks` |

**Resposta (200):**
```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Minha Primeira Tarefa",
      "description": "Esta é a descrição da tarefa.",
      "completed": false
    }
  ],
  "total_tasks": 1
}
```

### 📌 3. Buscar Tarefa por ID
| Método | Endpoint |
|--------|----------|
| GET    | `/tasks/<int:id>` |

**Resposta de Sucesso (200):**
```json
{
  "id": 1,
  "title": "Minha Primeira Tarefa",
  "description": "Esta é a descrição da tarefa.",
  "completed": false
}
```

**Resposta de Erro (404):**
```json
{
  "message": "Não foi possível encontrar a atividade"
}
```

### 📌 4. Atualizar Tarefa
| Método | Endpoint |
|--------|----------|
| PUT    | `/tasks/<int:id>` |

**Body (JSON):**
```json
{
  "title": "Título da Tarefa Atualizado",
  "description": "Descrição atualizada.",
  "completed": true
}
```

**Resposta de Sucesso (200):**
```json
{
  "message": "Tarefa atualizada com sucesso!"
}
```

**Resposta de Erro (404):**
```json
{
  "message": "Não foi possível encontrar a atividade"
}
```

### 📌 5. Excluir Tarefa
| Método | Endpoint |
|--------|----------|
| DELETE | `/tasks/<int:id>` |

**Resposta de Sucesso (200):**
```json
{
  "message": "Tarefa deletada com sucesso!"
}
```

**Resposta de Erro (404):**
```json
{
  "message": "Não foi possível encontrar a atividade"
}
```

## ✅ Testes

O projeto inclui testes de integração utilizando **Pytest**.

### Executar os testes:
1. Certifique-se de que a API (`app.py`) está rodando.  
2. Em outro terminal:
```bash
pytest -v
```

## 📄 Licença

Este projeto é de uso livre para fins de estudo e prática.  
Fique à vontade para cloná-lo, modificar e evoluir! 🚀
