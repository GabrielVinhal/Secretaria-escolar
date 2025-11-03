# Sistema de Gestão Escolar (Secretaria Web)

Este é um projeto full-stack de um sistema de gestão escolar, construído para modernizar e centralizar as operações de uma instituição de ensino. O sistema possui um backend robusto feito em Django (Python) que serve uma API REST, e um frontend moderno em React (JavaScript) focado na experiência do usuário.

## 🚀 Principais Funcionalidades

O sistema é dividido em módulos que cobrem as principais necessidades de uma secretaria acadêmica:

### Módulo Pedagógico
* **Gestão de Alunos e Turmas:** CRUD completo para Alunos e Turmas, permitindo vincular alunos a usuários e turmas.
* **Controle Acadêmico:** Lançamento de Notas, Faltas e Presenças por disciplina.
* **Relatórios de Desempenho:** Geração de relatórios por aluno, exibindo médias, faltas e histórico.
* **Download de Boletim:** Geração de boletim completo em PDF para download.
* **Calendário Acadêmico:** Calendário interativo (usando FullCalendar) para visualização de provas, trabalhos e eventos escolares. Administradores podem criar, editar e excluir eventos.
* **Eventos Extracurriculares:** Alunos podem visualizar e se inscrever em eventos com controle de vagas.

### Módulos de Gestão e Administração
* **Autenticação por Papel:** Sistema de login baseado em token que reconhece diferentes cargos (Aluno, Professor, Coordenador, Diretor, TI) e adapta a interface e as permissões.
* **Módulo Financeiro:** Controle de Mensalidades (status de pagamento) e Transações financeiras (entradas e saídas).
* **Módulo Disciplinar:** Registro de Advertências e Suspensões para os alunos.
* **Gestão de Recursos:** Módulo para coordenadores gerenciarem Salas de Laboratório, Materiais Didáticos e Colaboradores.

---

## 🛠️ Tecnologias Utilizadas

### Backend (Pasta: `escola/`)
* **Python 3**
* **Django 5+**
* **Django Rest Framework (DRF):** Para construção da API REST.
* **Autenticação:** DRF Token Authentication (Autenticação por Token).
* **Banco de Dados:** SQLite3 (configurado por padrão).
* **Admin:** `Jazzmin` para um painel de administração customizado.
* **CORS:** `django-cors-headers` para permitir a comunicação com o frontend.

### Frontend (Pasta: `frontend/`)
* **React 18**
* **Vite:** Como ferramenta de build e servidor de desenvolvimento.
* **React Router v6:** Para gerenciamento de rotas no lado do cliente.
* **Material-UI (MUI) v5:** Biblioteca de componentes para a interface.
* **Axios:** Para realizar as requisições HTTP para o backend Django.
* **FullCalendar:** Para a renderização do calendário acadêmico.

---

## ⚙️ Instalação e Execução

Para executar este projeto, você precisará de dois terminais: um para o Backend (Django) e um para o Frontend (React).

### 1. Backend (Django)

1.  **Navegue até a pasta `escola/`:**
    ```bash
    cd escola
    ```

2.  **Crie e ative um ambiente virtual (venv):**
    ```bash
    # Windows
    python -m venv venv
    venv\Scripts\activate
    
    # macOS / Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Instale as dependências:**
    *(Observação: você precisará criar um arquivo `requirements.txt` para listar as dependências do Django, como `django`, `djangorestframework`, `django-cors-headers`, `jazzmin`, etc.)*
    ```bash
    pip install -r requirements.txt 
    ```

4.  **Aplique as migrações do banco de dados:**
    ```bash
    python manage.py migrate
    ```

5.  **Crie um superusuário** (para acessar o Admin e criar outros usuários):
    ```bash
    python manage.py createsuperuser
    ```

6.  **Inicie o servidor Django:**
    ```bash
    python manage.py runserver
    ```
    *O backend estará rodando em `http://127.0.0.1:8000`.*

### 2. Frontend (React)

1.  **Abra um novo terminal e navegue até a pasta `frontend/`:**
    ```bash
    cd frontend
    ```

2.  **Instale as dependências do Node.js:**
    ```bash
    npm install
    ```

3.  **Inicie o servidor de desenvolvimento do Vite:**
    ```bash
    npm run dev
    ```
    *O frontend estará rodando em `http://localhost:5173`.*

---

## 📂 Estrutura dos Módulos (Apps Django)

O backend está organizado nos seguintes apps:

* `escola.base`: Gerencia o `Usuario` customizado, a autenticação da API e os formulários de login/registro.
* `escola.pedagogico`: O coração da aplicação. Gerencia Alunos, Turmas, Disciplinas, Notas, Faltas, Eventos Acadêmicos e Extracurriculares.
* `escola.coordenacao`: Módulo para gestão de recursos, como Salas de Laboratório, Materiais Didáticos e Colaboradores.
* `escola.financeiro`: Gerencia Mensalidades e Transações financeiras.
* `escola.disciplinar`: Gerencia o histórico disciplinar dos alunos (Advertências e Suspensões).
