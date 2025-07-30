# 📚 Memória Viva - Repositório de Projetos

![Banner do Projeto](https://img.shields.io/badge/Status-Ativo-brightgreen) ![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black) ![Supabase](https://img.shields.io/badge/Supabase-3FCF8E?logo=supabase&logoColor=white)

## 🎯 Sobre o Projeto

O **Memória Viva** é uma plataforma web desenvolvida para preservar e dar continuidade aos projetos acadêmicos, especialmente Projetos Integradores de cursos técnicos e superiores. A ideia central é que o trabalho de uma turma sirva de ponto de partida para a próxima, criando um ciclo contínuo de desenvolvimento e impacto social.

### ✨ Principais Funcionalidades

- **Cadastro de Projetos**: Interface intuitiva para registrar projetos com informações completas
- **Upload de Mídia**: Suporte para imagens e vídeos de capa dos projetos
- **Sistema de Busca Avançada**: Filtros por área, turma, ano e palavras-chave
- **Visualização Detalhada**: Modal com informações completas de cada projeto
- **Design Responsivo**: Interface adaptável para desktop, tablet e mobile
- **Persistência de Dados**: Integração com Supabase para armazenamento seguro

## 🛠️ Tecnologias Utilizadas

### Frontend
- **HTML5**: Estrutura semântica da aplicação
- **CSS3**: Estilização moderna com flexbox, grid e animações
- **JavaScript (ES6+)**: Lógica da aplicação e manipulação do DOM
- **Font Awesome**: Biblioteca de ícones

### Backend/Banco de Dados
- **Supabase**: 
  - PostgreSQL para armazenamento de dados
  - Storage para arquivos de mídia
  - API REST automática
  - Autenticação e autorização

### Design
- **Design System Próprio**: Paleta de cores consistente
- **Responsividade**: Mobile-first approach
- **UX/UI Moderno**: Micro-interações e transições suaves

## 🚀 Como Executar o Projeto

### Pré-requisitos
- Navegador web moderno (Chrome, Firefox, Safari, Edge)
- Conexão com internet (para CDNs e Supabase)

### Instalação
1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/memoria-viva.git
   cd memoria-viva
   ```

2. **Configure o Supabase**:
   - Crie uma conta no [Supabase](https://supabase.com)
   - Crie um novo projeto
   - Configure a tabela `db_memoria_viva` com os campos:
     ```sql
     CREATE TABLE db_memoria_viva (
       id SERIAL PRIMARY KEY,
       nome_projeto VARCHAR(255) NOT NULL,
       area VARCHAR(100) NOT NULL,
       turma VARCHAR(100) NOT NULL,
       docente VARCHAR(255) NOT NULL,
       ano INTEGER NOT NULL,
       descricao TEXT NOT NULL,
       integrantes TEXT[] NOT NULL,
       url_midia TEXT,
       created_at TIMESTAMP DEFAULT NOW()
     );
     ```
   - Configure o Storage bucket `midia-projetos` para upload de arquivos
   - Copie a URL do projeto e a chave anônima

3. **Configure as credenciais**:
   - Substitua as constantes no código:
   ```javascript
   const SUPABASE_URL = "sua-url-do-supabase";
   const SUPABASE_ANON_KEY = "sua-chave-anonima";
   ```

4. **Execute o projeto**:
   - Abra o arquivo `index.html` diretamente no navegador
   - Ou utilize um servidor local como Live Server (VS Code)

## 📁 Estrutura do Projeto

```
memoria-viva/
├── index.html              # Arquivo principal da aplicação
├── README.md              # Documentação do projeto
└── assets/                # (opcional) Pasta para assets locais
    ├── images/           # Imagens do projeto
    └── docs/             # Documentação adicional
```

## 🎨 Design System

### Paleta de Cores
- **Azul Principal**: `#003366` - Cabeçalho e títulos
- **Azul Secundário**: `#002244` - Hero banner
- **Laranja Destaque**: `#FF6600` - Botões e elementos de ação
- **Cinza Claro**: `#F8FAFC` - Background geral
- **Texto Principal**: `#2C3E50`

### Tipografia
- **Fonte Principal**: Inter, Segoe UI, Tahoma, Geneva, Verdana, sans-serif
- **Hierarquia**: Títulos (2.8rem), Subtítulos (1.4rem), Corpo (1rem)

### Componentes
- **Botões**: Primário (laranja), Secundário (transparente)
- **Cards**: Sombra sutil, bordas arredondadas
- **Modal**: Overlay escuro com animações suaves

## 💾 Banco de Dados

### Tabela Principal: `db_memoria_viva`

| Campo | Tipo | Descrição |
|-------|------|-----------|
| `id` | SERIAL | Identificador único |
| `nome_projeto` | VARCHAR(255) | Nome do projeto |
| `area` | VARCHAR(100) | Área do curso |
| `turma` | VARCHAR(100) | Identificação da turma |
| `docente` | VARCHAR(255) | Nome do professor responsável |
| `ano` | INTEGER | Ano de realização |
| `descricao` | TEXT | Descrição detalhada |
| `integrantes` | TEXT[] | Array com nomes dos integrantes |
| `url_midia` | TEXT | URL da mídia (imagem/vídeo) |
| `created_at` | TIMESTAMP | Data de criação |

### Storage: `midia-projetos`
Bucket para armazenamento de imagens e vídeos dos projetos.

## 🔧 Funcionalidades Detalhadas

### 1. Cadastro de Projetos
- Formulário com validação client-side
- Upload de imagens/vídeos com preview
- Gestão dinâmica de integrantes
- Integração com Supabase para persistência

### 2. Consulta de Projetos
- Visualização em grid responsivo
- Sistema de filtros combinados:
  - Por área do curso
  - Por palavra-chave
  - Por turma
  - Por ano
- Modal com detalhes completos

### 3. Interface Responsiva
- Menu hamburger para mobile
- Grid adaptativo
- Componentes otimizados para touch

## 🚦 Status do Projeto

- ✅ Interface principal implementada
- ✅ Sistema de cadastro funcional
- ✅ Integração com Supabase
- ✅ Sistema de busca e filtros
- ✅ Design responsivo
- ✅ Upload de mídia
- 🔄 Melhorias contínuas de UX/UI

## 🤝 Como Contribuir

1. **Fork** o projeto
2. Crie uma **branch** para sua feature (`git checkout -b feature/nova-funcionalidade`)
3. **Commit** suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. **Push** para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um **Pull Request**

### Padrões de Contribuição
- Utilize commits semânticos
- Mantenha o código limpo e comentado
- Teste em diferentes dispositivos/navegadores
- Documente novas funcionalidades

## 📋 Áreas de Curso Suportadas

- Beleza e Estética
- Bem-estar
- Comunicação e Marketing
- Desenvolvimento Social
- Design, Artes e Arquitetura
- Educação
- Gastronomia e Alimentação
- Gestão e Negócios
- Idiomas
- Meio Ambiente, Segurança e Saúde no Trabalho
- Moda
- Saúde
- Tecnologia da Informação
- Turismo e Hospitalidade

## 🐛 Problemas Conhecidos

- Upload de arquivos muito grandes pode ser lento
- Filtros são aplicados apenas no frontend (limitação de performance com muitos registros)

## 🔮 Roadmap Futuro

- [ ] Sistema de autenticação de usuários
- [ ] Comentários e avaliações nos projetos
- [ ] Sistema de tags personalizado
- [ ] Exportação de dados para PDF
- [ ] API pública para integração
- [ ] Notificações de novos projetos

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👨‍💻 Autor

**Felipe Martins**
- GitHub: [@felipemartins03](https://github.com/felipemartins03)
- LinkedIn: [ifelipemartins](https://www.linkedin.com/in/ifelipemartins/)

## 🙏 Agradecimentos

- Comunidade open source pela inspiração
- Supabase pela excelente plataforma de desenvolvimento
- Font Awesome pelos ícones utilizados

---

**Memória Viva** - *Onde cada projeto tem um próximo capítulo* 📚✨
