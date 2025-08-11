<div align="center">
  <img src="./if-logo.png" alt="Logo da Instituição" width="450"/>
  <h3>Instituto Federal de Educação, Ciência e Tecnologia do Triângulo Mineiro - Campus Ituiutaba</h3>
  <p><em>Gradução em Tecnólogia em <u>Análise e Desenvolvimento de Sistemas</u></em></p>
  <p>Projeto Integrador Extensionista III</p>
</div>

# 🐶 Adote IF - Sistema de Adoção de Pets
[![Preview do site](https://raw.githubusercontent.com/perera2k4/AdoteI.FTM-PIE3/refs/heads/main/preview.png)](https://perera2k4.github.io/AdoteI.FTM-PIE3/)

## 📋 Sobre o Projeto

O **Adote I.F** é uma plataforma web completa para adoção de pets, desenvolvida como um projeto acadêmico. O sistema permite que usuários criem publicações de animais disponíveis para adoção e se conectem via WhatsApp para facilitar o processo de adoção.


<a align="center" href="https://www.youtube.com/shorts/2iIqQzVAL50" target="_blank">
  <span><strong>Vídeo de demonstração:</strong></span>
  <img src="https://img.youtube.com/vi/2iIqQzVAL50/0.jpg" target="_blank" alt="Vídeo de Demonstração" width="600"/>
</a>

## 🏗️ Arquitetura do Sistema

### Frontend
- **Framework**: React 18.2.0 com Vite
- **Styling**: Tailwind CSS 3.3.0
- **Roteamento**: React Router DOM 6.8.1
- **Ícones**: Lucide React 0.263.1
- **Linguagem**: JavaScript (JSX)

### Backend
- **Framework**: Flask 2.3.3 (Python)
- **Banco de Dados**: MongoDB (Atlas)
- **Autenticação**: Sistema de sessões com bcrypt
- **CORS**: Flask-CORS 4.0.0
- **Deploy**: Render.com

## 🚀 Funcionalidades

### 👤 Autenticação
- Sistema de login e cadastro
- Gerenciamento de sessões com timeout automático
- Verificação de atividade do usuário
- Logout automático por inatividade

### 📱 Publicações
- Criação de posts com foto, título e descrição
- Categorização por tipo de animal (cão/gato)
- Visualização em grid responsivo
- Modal com detalhes completos do pet

### 💬 Comunicação
- Integração com WhatsApp para contato direto
- Link automático com mensagem pré-formatada
- Exibição de informações do responsável

### 👥 Perfil do Usuário
- Visualização de publicações próprias
- Gerenciamento de posts (exclusão)
- Badge para administradores

## 🛠️ Instalação e Configuração

### Pré-requisitos
- Node.js (versão 16 ou superior)
- Python 3.8 ou superior
- MongoDB Atlas (conta gratuita)
- Git

### 🔧 Configuração do Backend

1. **Clone o repositório**:
```bash
git clone [url-do-repositorio]
cd "Adote I.F - PIE3"
```

2. **Navegue para o diretório do backend**:
```bash
cd backend
```

3. **Instale as dependências Python**:
```bash
pip install flask==2.3.3
pip install flask-cors==4.0.0
pip install pymongo==4.5.0
pip install bcrypt==4.0.1
pip install PyJWT==2.8.0
pip install gunicorn==21.2.0
```

Ou use o arquivo requirements.txt:
```bash
pip install -r requirements.txt
```

4. **Configure as variáveis de ambiente**:
Crie um arquivo `.env` ou configure no sistema:
```bash
# Opcional - o sistema usa valores padrão
SECRET_KEY=sua_chave_secreta_aqui
MONGO_URI=sua_string_de_conexao_mongodb
```

5. **Execute o servidor**:
```bash
python app.py
```

O backend estará disponível em `http://localhost:5000`

### 🎨 Configuração do Frontend

1. **Navegue para o diretório do frontend**:
```bash
cd frontend
```

2. **Instale as dependências base**:
```bash
npm install
```

3. **Instale as dependências específicas**:
```bash
# Dependências principais
npm install react@^18.2.0
npm install react-dom@^18.2.0
npm install react-router-dom@^6.8.1
npm install lucide-react@^0.263.1

# Dependências de desenvolvimento
npm install -D @types/react@^18.2.15
npm install -D @types/react-dom@^18.2.7
npm install -D @vitejs/plugin-react@^4.0.3
npm install -D autoprefixer@^10.4.14
npm install -D eslint@^8.45.0
npm install -D eslint-plugin-react@^7.32.2
npm install -D eslint-plugin-react-hooks@^4.6.0
npm install -D eslint-plugin-react-refresh@^0.4.3
npm install -D postcss@^8.4.24
npm install -D tailwindcss@^3.3.0
npm install -D vite@^4.4.5
```

4. **Configure o Tailwind CSS**:
O projeto já possui a configuração, mas se precisar recriar:
```bash
npx tailwindcss init -p
```

5. **Execute o servidor de desenvolvimento**:
```bash
npm run dev
```

O frontend estará disponível em `http://localhost:5173`

## 📁 Estrutura do Projeto

```
Adote I.F - PIE3/
├── backend/
│   ├── app.py                 # Servidor Flask principal
│   ├── requirements.txt       # Dependências Python
│   └── package.json          # Configuração Node (opcional)
├── frontend/
│   ├── public/
│   │   ├── assets/
│   │   │   └── logo.png      # Logo da aplicação
│   │   ├── favico.png        # Favicon
│   │   └── vite.svg          # Ícone do Vite
│   ├── src/
│   │   ├── components/
│   │   │   ├── defaults/
│   │   │   │   ├── HotBar.jsx      # Barra de navegação inferior
│   │   │   │   └── NavBar.jsx      # Barra de navegação superior
│   │   │   ├── userdata/
│   │   │   │   └── Login.jsx       # Tela de login/cadastro
│   │   │   ├── AddPost.jsx         # Formulário de criação de posts
│   │   │   ├── Button.jsx          # Componente de botão
│   │   │   ├── Input.jsx           # Componente de input
│   │   │   ├── Profile.jsx         # Perfil do usuário
│   │   │   ├── SessionInfo.jsx     # Informações da sessão
│   │   │   ├── SideBar.jsx         # Barra lateral (não utilizada)
│   │   │   ├── Tasks.jsx           # Listagem de posts
│   │   │   └── Title.jsx           # Componente de título
│   │   ├── config/
│   │   │   └── api.js              # Configuração da API
│   │   ├── utils/
│   │   │   └── auth.js             # Serviço de autenticação
│   │   ├── App.jsx                 # Componente principal
│   │   ├── main.jsx                # Ponto de entrada
│   │   └── index.css               # Estilos globais
│   ├── .env                        # Variáveis de ambiente
│   ├── .gitignore                  # Arquivos ignorados pelo Git
│   ├── eslint.config.js            # Configuração do ESLint
│   ├── index.html                  # HTML principal
│   ├── package.json                # Dependências Node.js
│   ├── postcss.config.js           # Configuração PostCSS
│   ├── tailwind.config.js          # Configuração Tailwind
│   └── vite.config.js              # Configuração Vite
└── README.md
```

## 🔧 Configuração do MongoDB

1. **Crie uma conta no MongoDB Atlas**:
   - Acesse [MongoDB Atlas](https://cloud.mongodb.com/)
   - Crie uma conta gratuita

2. **Configure o cluster**:
   - Crie um novo cluster (Free Tier)
   - Configure as credenciais de acesso
   - Adicione seu IP à whitelist

3. **Obtenha a string de conexão**:
   - Clique em "Connect"
   - Escolha "Connect your application"
   - Copie a string de conexão

4. **Configure no backend**:
   ```python
   # Em app.py, substitua pela sua string
   MONGO_URI = "mongodb+srv://usuario:senha@cluster.mongodb.net/AdoteIFTM"
   ```

## 🌐 Deploy

### Backend (Render.com)
1. Crie conta no [Render](https://render.com/)
2. Conecte seu repositório GitHub
3. Configure como "Web Service"
4. Defina:
   - Build Command: `pip install -r requirements.txt`
   - Start Command: `gunicorn app:app`
   - Environment Variables: `MONGO_URI`, `SECRET_KEY`

### Frontend (Vercel)
1. Crie conta no [Vercel](https://vercel.com/)
2. Conecte seu repositório GitHub
3. Configure:
   - Framework: Vite
   - Build Command: `npm run build`
   - Output Directory: `dist`
   - Root Directory: `frontend`

## 🎯 Como Usar

### 1. Primeiro Acesso
- Acesse a aplicação
- Clique em "Crie sua Conta"
- Preencha: usuário, senha e telefone
- Faça login com as credenciais criadas

### 2. Criando uma Publicação
- Clique no botão "+" na barra inferior
- Preencha o nome do pet
- Selecione o tipo (cão/gato)
- Adicione uma descrição
- Faça upload da foto
- Clique em "Adicionar Post"

### 3. Adotando um Pet
- Navegue pelos posts na tela inicial
- Clique em um post para ver detalhes
- Clique no botão WhatsApp para contatar o responsável
- Uma mensagem será pré-formatada automaticamente

### 4. Gerenciando Publicações
- Clique no ícone de usuário na barra inferior
- Visualize todas suas publicações
- Exclua posts que não são mais necessários

## 🔐 Segurança

### Sistema de Sessões
- Timeout automático de 10 minutos
- Verificação de atividade do usuário
- Limpeza automática de sessões expiradas
- Headers de segurança configurados

### Validações
- Senhas criptografadas com bcrypt
- Validação de dados no frontend e backend
- Sanitização de uploads de imagem
- Proteção contra CORS

## 🐛 Resolução de Problemas

### Erro de CORS
```bash
# Verifique se o backend está rodando
# Confirme a URL da API em frontend/src/config/api.js
```

### Erro de Conexão com MongoDB
```bash
# Verifique a string de conexão
# Confirme se seu IP está na whitelist
# Teste a conexão diretamente
```

### Erro de Dependências
```bash
# Frontend
npm install --legacy-peer-deps

# Backend
pip install --upgrade pip
pip install -r requirements.txt
```

### Erro de Upload de Imagem
```bash
# Verifique o tamanho da imagem (máximo 5MB)
# Confirme o formato (JPG, PNG, GIF)
# Teste com imagem menor
```

## 📱 Responsividade

O sistema foi desenvolvido com design responsivo:
- **Mobile First**: Otimizado para dispositivos móveis
- **Tablets**: Layout adaptativo para telas médias
- **Desktop**: Interface completa para telas grandes

## 🎨 Customização

### Cores (Tailwind)
- **Primária**: Purple (roxo) - `#9533EC`
- **Secundária**: Blue (azul) - `#3B82F6`
- **Sucesso**: Green (verde) - `#10B981`
- **Erro**: Red (vermelho) - `#EF4444`

### Fontes
- **Sistema**: Usa fontes do sistema operacional
- **Ícones**: Lucide React (consistente e moderno)

## 📋 Scripts Disponíveis

### Frontend
```bash
npm run dev         # Servidor de desenvolvimento
npm run build       # Build para produção
npm run preview     # Preview do build
npm run lint        # Verificação de código
```

### Backend
```bash
python app.py       # Servidor de desenvolvimento
gunicorn app:app    # Servidor de produção
```

## 🤝 Contribuição

1. Faça fork do projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## 📄 Licença

- M.I.T.
- Este projeto foi desenvolvido para fins educacionais como parte do curso de Graduação em Análise e Desenvolvimento de Sistemas.

## 👥 Autores

- **Bruno Carvalho** - Desenvolvedor Full Stack
- **Diogenes Cassimiro** - Desenvolvedor Front-end
- **Ronald Abdias** - Analista de QA e Desenvolvedor BD

---

## 📞 Suporte

Para dúvidas ou problemas:
1. Verifique a seção de **Resolução de Problemas**
2. Consulte os logs do console (F12 no navegador)
3. Verifique se todos os serviços estão rodando
4. Confirme as configurações de ambiente
5. Entre em contato via e-mail: bruno.carvalho@estudante.iftm.edu.br, diogenes.cassimiro@estudante.iftm.edu.br, ronald.abdias@estudante.iftm.edu.br

**Desenvolvido para facilitar a adoção de pets!** 🐶🐱
