# 🎵 Minha Coleção Musical

<div align="center">

![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.2-3178C6?style=for-the-badge&logo=typescript)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.3-06B6D4?style=for-the-badge&logo=tailwindcss)
![Docker](https://img.shields.io/badge/Docker-Ready-2496ED?style=for-the-badge&logo=docker)

**Projeto Didático Completo para Ensinar React, APIs REST e Docker**

[Funcionalidades](#-funcionalidades) • [Tecnologias](#-tecnologias) • [Instalação](#-instalação) • [Docker](#-docker) • [Estrutura](#-estrutura-do-projeto) • [Conceitos](#-conceitos-ensinados)

</div>

---

## 📋 Sobre o Projeto do Gilson

Este é um projeto **educacional completo** criado para ensinar desenvolvimento web moderno. Ele implementa um sistema de gerenciamento de músicas (CRUD completo) com:

- ✅ **Frontend moderno** em React + TypeScript
- ✅ **API REST fake** com JSON Server
- ✅ **Design responsivo** e bonito com TailwindCSS
- ✅ **Todas as operações HTTP**: GET, POST, PUT, DELETE
- ✅ **Docker** pronto para produção
- ✅ **Código 100% comentado** em português

---

## ✨ Funcionalidades

### CRUD Completo

- 📖 **GET** - Listar todas as músicas
- ➕ **POST** - Adicionar nova música
- ✏️ **PUT** - Editar música existente
- 🗑️ **DELETE** - Remover música

### Interface Moderna

- 🎨 Design dark mode com gradientes
- 📱 Totalmente responsivo (mobile-first)
- 🔍 Busca em tempo real
- ✨ Animações suaves
- 🖼️ Cards com preview de imagem (imagem padrão musical se não houver URL)
- ⚡ Feedback visual (loading, toasts, etc.)

---

## 🛠️ Tecnologias

### Frontend

- **React 18** - Biblioteca UI
- **TypeScript** - Tipagem estática
- **Vite** - Build tool moderna
- **TailwindCSS** - Framework CSS utilitário
- **Axios** - Cliente HTTP
- **Lucide React** - Ícones modernos

### Backend

- **JSON Server** - API REST fake automática

### DevOps

- **Docker** - Containerização
- **Docker Compose** - Orquestração
- **Nginx** - Servidor web

---

## 🚀 Instalação

### Pré-requisitos

- **Node.js** 18 ou superior ([Download](https://nodejs.org/))
- **npm** ou **yarn**
- **Docker** (opcional, para containerização)

### Passo 1: Clone o Repositório

```bash
git clone <url-do-repositorio>
cd front-exemplo-react
```

### Passo 2: Instale as Dependências

#### Frontend

```bash
npm install
```

#### Backend (API)

```bash
cd api
npm install
cd ..
```

### Passo 3: Configure as Variáveis de Ambiente

```bash
cp .env.example .env
```

O arquivo `.env` já está configurado com valores padrão para desenvolvimento.

### Passo 4: Execute o Projeto

#### Opção A: Executar Frontend e Backend Separadamente

**Terminal 1 - Backend (API):**
```bash
cd api
npm start
```

A API estará rodando em: `http://localhost:3001`

**Terminal 2 - Frontend:**
```bash
npm run dev
```

O frontend estará rodando em: `http://localhost:5173`

#### Opção B: Usar Docker Compose

```bash
docker-compose up --build
```

Acesse:
- **Frontend**: `http://localhost:3000`
- **API**: `http://localhost:3001`

---

## 🐳 Docker

### Build da Imagem Frontend

```bash
docker build -t minha-colecao-musical:1.0 .
```

### Executar Container Frontend

```bash
docker run -p 3000:80 minha-colecao-musical:1.0
```

### Publicar no Docker Hub

#### 1. Faça Login

```bash
docker login
```

#### 2. Crie uma Tag

```bash
docker tag minha-colecao-musical:1.0 seu-usuario/minha-colecao-musical:1.0
```

#### 3. Publique

```bash
docker push seu-usuario/minha-colecao-musical:1.0
```

#### 4. Executar de Qualquer Máquina

```bash
docker pull seu-usuario/minha-colecao-musical:1.0
docker run -p 3000:80 seu-usuario/minha-colecao-musical:1.0
```

### Docker Compose Completo

O `docker-compose.yml` já está configurado para subir frontend + backend:

```bash
# Subir tudo
docker-compose up -d

# Ver logs
docker-compose logs -f

# Parar tudo
docker-compose down

# Reconstruir e subir
docker-compose up --build
```

---

## 📁 Estrutura do Projeto

```
minha-colecao-musical/
│
├── src/                          # Código fonte React
│   ├── components/              # Componentes React
│   │   ├── ui/                  # Componentes UI reutilizáveis
│   │   │   ├── Button.tsx       # Botão com variantes
│   │   │   ├── Input.tsx        # Campo de entrada
│   │   │   ├── Modal.tsx        # Modal acessível
│   │   │   └── Card.tsx         # Card componível
│   │   ├── MusicaCard.tsx       # Card de música
│   │   └── MusicaForm.tsx       # Formulário de música
│   │
│   ├── hooks/                   # Hooks customizados
│   │   └── useMusicas.ts        # Hook para gerenciar músicas
│   │
│   ├── services/                # Serviços de API
│   │   ├── api.ts               # Configuração Axios
│   │   └── musicaService.ts     # Serviço de músicas (CRUD)
│   │
│   ├── types/                   # Tipos TypeScript
│   │   └── musica.ts            # Interface Musica
│   │
│   ├── lib/                     # Utilitários
│   │   └── utils.ts             # Funções auxiliares
│   │
│   ├── App.tsx                  # Componente principal
│   ├── main.tsx                 # Ponto de entrada
│   └── index.css                # Estilos globais
│
├── api/                         # Backend JSON Server
│   ├── db.json                  # Banco de dados fake
│   └── package.json             # Dependências da API
│
├── Dockerfile                   # Imagem Docker frontend
├── docker-compose.yml           # Orquestração completa
├── nginx.conf                   # Configuração Nginx
├── .dockerignore                # Arquivos ignorados no build
│
├── package.json                 # Dependências frontend
├── tsconfig.json                # Configuração TypeScript
├── vite.config.ts               # Configuração Vite
├── tailwind.config.js           # Configuração Tailwind
└── README.md                    # Este arquivo
```

---

## 🎓 Conceitos Ensinados

### 1. React Fundamentals

#### Componentes Funcionais
```typescript
// Componente simples
function MeuComponente() {
  return <div>Olá Mundo!</div>;
}
```

#### Props
```typescript
interface MinhasProps {
  titulo: string;
  idade: number;
}

function Componente({ titulo, idade }: MinhasProps) {
  return <h1>{titulo} - {idade}</h1>;
}
```

#### useState - Gerenciamento de Estado
```typescript
const [contador, setContador] = useState(0);

const incrementar = () => {
  setContador(contador + 1);
};
```

#### useEffect - Efeitos Colaterais
```typescript
useEffect(() => {
  // Código executado após renderização
  console.log('Componente montado!');
  
  return () => {
    // Cleanup
    console.log('Componente desmontado!');
  };
}, []); // Array vazio = executa apenas uma vez
```

#### useCallback - Otimização
```typescript
const handleClick = useCallback(() => {
  // Função memorizada
}, [dependencias]);
```

### 2. TypeScript

#### Interfaces
```typescript
interface Musica {
  id?: number;
  titulo: string;
  artista: string;
}
```

#### Type Utilities
```typescript
type FormMusica = Omit<Musica, 'id'>;  // Remove campo 'id'
```

#### Tipagem de Funções
```typescript
const somar = (a: number, b: number): number => {
  return a + b;
};
```

### 3. HTTP / REST API

#### GET - Buscar Dados
```typescript
const response = await axios.get('/musicas');
const musicas = response.data;
```

#### POST - Criar Novo Recurso
```typescript
const novaMusica = { titulo: 'Teste', artista: 'Artista' };
await axios.post('/musicas', novaMusica);
```

#### PUT - Atualizar Recurso Completo
```typescript
const musicaAtualizada = { ...musica, titulo: 'Novo Título' };
await axios.put(`/musicas/${id}`, musicaAtualizada);
```

#### DELETE - Remover Recurso
```typescript
await axios.delete(`/musicas/${id}`);
```

### 4. Formulários Controlados

```typescript
const [valor, setValor] = useState('');

<input 
  value={valor}
  onChange={(e) => setValor(e.target.value)}
/>
```

### 5. Validação de Formulários

```typescript
const validar = () => {
  const erros: Record<string, string> = {};
  
  if (!titulo) {
    erros.titulo = 'Título é obrigatório';
  }
  
  return Object.keys(erros).length === 0;
};
```

### 6. Custom Hooks

```typescript
function useMinhaLogica() {
  const [estado, setEstado] = useState();
  
  // Lógica reutilizável
  
  return { estado, funcao };
}
```

### 7. TailwindCSS

#### Classes Utilitárias
```html
<div class="flex items-center justify-between p-4 bg-dark-800 rounded-lg">
  Conteúdo
</div>
```

#### Responsividade
```html
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4">
  Cards responsivos
</div>
```

#### Estados Hover/Focus
```html
<button class="bg-blue-500 hover:bg-blue-600 focus:ring-2">
  Botão
</button>
```

### 8. Docker

#### Multi-stage Build
```dockerfile
FROM node:18 AS build
# Build da aplicação

FROM nginx:alpine
# Servir arquivos estáticos
```

#### Docker Compose
```yaml
services:
  frontend:
    build: .
    ports:
      - "3000:80"
  
  backend:
    image: json-server
    ports:
      - "3001:3001"
```

---

## 🎨 Personalizações

### Alterar Imagem Padrão das Capas

A imagem padrão que aparece quando não há URL de capa está definida em `src/lib/constants.ts`:

```typescript
export const CAPA_PADRAO = 'https://images.unsplash.com/photo-1511379938547-c1f69419868d?w=300&h=300&fit=crop&q=80';
```

**Para trocar a imagem:**
1. Abra `src/lib/constants.ts`
2. Substitua a URL pela sua preferida
3. Sugestões de imagens gratuitas:
   - [Unsplash](https://unsplash.com/) - Fotos de alta qualidade
   - [Pexels](https://www.pexels.com/) - Fotos gratuitas
   - Ou use qualquer URL de imagem pública

**Alternativas já incluídas no arquivo:**
```typescript
// Opção 1: Equipamento musical (padrão)
'https://images.unsplash.com/photo-1511379938547-c1f69419868d'

// Opção 2: Estúdio musical
'https://images.unsplash.com/photo-1514320291840-2e0a9bf2a9ae'

// Opção 3: Discos de vinil
'https://images.unsplash.com/photo-1533174072545-7a4b6ad7a6c3'
```

---

## 🎯 Exercícios Propostos

### Nível Iniciante
1. Adicione um campo "Duração" nas músicas
2. Crie um filtro por gênero
3. Adicione mais músicas de exemplo no `db.json`
4. Mude a imagem padrão para outra URL
5. Mude as cores do tema

### Nível Intermediário
1. Implemente paginação
2. Adicione ordenação (por título, artista, ano)
3. Crie um componente de "Toast" para notificações
4. Adicione um player de áudio usando HTML5 Audio

### Nível Avançado
1. Implemente autenticação com JWT
2. Adicione testes com Vitest e React Testing Library
3. Implemente drag-and-drop para reordenar músicas
4. Crie um sistema de playlists

---

## 🐛 Troubleshooting

### Erro: "Cannot find module 'react'"
```bash
npm install
```

### Erro: "Port 3001 already in use"
```bash
# Windows
netstat -ano | findstr :3001
taskkill /PID <PID> /F

# Linux/Mac
lsof -ti:3001 | xargs kill -9
```

### Erro: "CORS policy"
Certifique-se de que a API está rodando em `localhost:3001` e configurada corretamente.

### Docker: "Cannot connect to daemon"
```bash
# Inicie o Docker Desktop
```

---

## 📚 Recursos Adicionais

### Documentação Oficial
- [React](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [TailwindCSS](https://tailwindcss.com/)
- [Axios](https://axios-http.com/)
- [Docker](https://docs.docker.com/)

### Tutoriais Recomendados
- [React Tutorial](https://react.dev/learn)
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Tailwind Tutorial](https://tailwindcss.com/docs/installation)

---

## 🤝 Contribuindo

Este é um projeto educacional. Contribuições são bem-vindas!

1. Fork o projeto
2. Crie uma branch (`git checkout -b feature/melhorias`)
3. Commit suas mudanças (`git commit -m 'Adiciona melhorias'`)
4. Push para a branch (`git push origin feature/melhorias`)
5. Abra um Pull Request

---

## 📝 Licença

Este projeto é livre para uso educacional.

---

## 👨‍💻 Autor

Projeto criado para ensinar desenvolvimento web moderno com foco em:
- React e TypeScript
- APIs REST
- Docker e DevOps
- Boas práticas de código

---

## ⭐ Comandos Rápidos

```bash
# Desenvolvimento
npm run dev              # Inicia dev server
npm run build            # Build para produção
npm run preview          # Preview do build

# API
cd api && npm start      # Inicia JSON Server

# Docker
docker-compose up -d     # Sobe tudo em background
docker-compose down      # Para tudo
docker-compose logs -f   # Ver logs em tempo real

# Linting
npm run lint             # Verifica código
```

---

<div align="center">

**Feito com ❤️ para ensinar programação**

[⬆ Voltar ao topo](#-minha-coleção-musical)

</div>
