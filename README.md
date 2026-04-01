## Formatic

Formatic é um aplicativo de apoio aos estudos feito em Flutter. O app centraliza organização acadêmica em um único lugar, com foco em:

- gerenciamento de tarefas de estudo
- revisão por flashcards
- biblioteca com leitura de PDFs
- assistente virtual para tirar dúvidas e sugerir planos de estudo
- autenticação e perfil do usuário

## Função do App

O objetivo do Formatic é ajudar estudantes a planejar, executar e revisar seus estudos de forma prática. A proposta é combinar produtividade (tarefas), revisão ativa (flashcards), leitura (biblioteca) e suporte com IA (assistente) no mesmo fluxo.

## Páginas/Telas Principais

O app possui as seguintes telas, organizadas por feature:

1. Login/Cadastro
- autentica usuários
- permite criar conta e entrar no sistema

2. Home
- tela principal com barra superior e navegação inferior
- organiza o acesso rápido para as demais features

3. Tarefas
- cria, edita e remove tarefas
- permite definir data, hora, descrição e cor
- salva dados localmente (SharedPreferences)

4. Flashcards
- cria, edita e exclui flashcards
- possui modo de estudo para revisão

5. Assistente
- chat com a tutora virtual "Helpy"
- usa IA para responder dúvidas e propor próximos passos
- aceita anexos de documentos para contexto

6. Biblioteca
- lista livros e materiais
- busca e filtros por tags
- abre materiais em PDF

7. Visualizador de PDF
- leitura de PDFs com zoom e navegação por página
- mostra informações do livro/material

8. Perfil
- visualiza e atualiza dados do usuário
- permite inserir/editar telefone e avatar

## Linguagens, Frameworks e Bibliotecas

- Dart (linguagem principal)
- Flutter (framework de UI multiplataforma)
- Supabase (autenticação e backend)
- HTTP (comunicação com APIs externas)
- flutter_dotenv (variáveis de ambiente)
- shared_preferences (persistência local)
- syncfusion_flutter_pdfviewer / syncfusion_flutter_pdf (leitura/manipulação de PDF)
- image_picker, file_picker, archive, xml, path_provider, url_launcher

## Requisitos

Antes de rodar o projeto, você precisa de:

1. Flutter SDK instalado
- recomendado: versão estável mais recente compatível com o projeto

2. Dart SDK
- já vem junto com o Flutter
- no projeto, o ambiente está configurado para Dart SDK `^3.8.1`

3. IDE
- VS Code ou Android Studio

4. Ferramentas de plataforma (dependendo de onde vai rodar)
- Android: Android SDK + emulador/dispositivo
- iOS (macOS): Xcode
- Windows/macOS/Linux: toolchain desktop do Flutter

5. Arquivo `.env` na raiz do projeto
- o app usa variáveis de ambiente para integrações

### Exemplo de `.env`

Crie um arquivo `.env` na raiz do projeto com:

```env
SUPABASE_URL=https://SEU-PROJETO.supabase.co
SUPABASE_ANON_KEY=SUA_CHAVE_ANON
DEEPSEEK_API_KEY=SUA_CHAVE_DEEPSEEK
```

Observações:
- `SUPABASE_ANON_KEY` é obrigatória para autenticação e acesso ao Supabase.
- `DEEPSEEK_API_KEY` é necessária para usar a tela de assistente.
- `SUPABASE_URL` pode ser usada por serviços internos do projeto (mantenha configurada).

## Como Rodar o App (Passo a Passo)

### 1. Clonar/abrir o projeto

```bash
git clone <url-do-repositorio>
cd Formatic
```

Se você já possui os arquivos localmente, apenas abra a pasta do projeto.

### 2. Conferir ambiente Flutter

```bash
flutter doctor
```

Resolva os avisos/erros mostrados antes de seguir.

### 3. Criar e preencher o `.env`

- crie o arquivo `.env` na raiz
- adicione as chaves mostradas na seção anterior

### 4. Instalar dependencias

```bash
flutter pub get
```

### 5. Executar o app

Escolha uma plataforma:

```bash
flutter run
```

Ou especifique o dispositivo:

```bash
flutter devices
flutter run -d <device_id>
```

### 6. Build para produção (opcional)

Android APK:

```bash
flutter build apk --release
```

Android App Bundle:

```bash
flutter build appbundle --release
```

Web:

```bash
flutter build web --release
```

Windows:

```bash
flutter build windows --release
```

macOS:

```bash
flutter build macos --release
```

Linux:

```bash
flutter build linux --release
```

## Estrutura do Projeto (Resumo)

- `lib/features/` contém as telas e fluxos principais por módulo
- `lib/services/` contém regras de acesso a dados e integrações
- `lib/models/` contém modelos de domínio
- `lib/core/` contém utilitários e temas compartilhados
- `assets/` contém imagens, PDFs e outros recursos estáticos

## Dicas de Troubleshooting

- erro de chave/API: valide o arquivo `.env` e reinicie o app
- dependências quebradas: rode `flutter clean` e depois `flutter pub get`
- problemas de plataforma: rode `flutter doctor` e ajuste o ambiente

---

Projeto desenvolvido com Flutter para apoiar rotinas de estudo de forma integrada.


