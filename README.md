# 🧟‍♂️ GROKZOMBORG

Um chatbot zumbi sarcástico e carismático alimentado por **Ollama**, com personalidade em português brasileiro.

## ✨ Funcionalidades

- **Resposta em Streaming** - Respostas em tempo real com `stream: true` para melhor desempenho
- **Indicador de Conexão** - Status em tempo real da conexão com Ollama (ping a cada 5 segundos)
- **Seleção de Modelos** - Dropdown para alternar entre modelos disponíveis (llama3.2, llama2, mistral, neural-chat)
- **Persistência de Mensagens** - Histórico salvo em localStorage e restaurado ao recarregar
- **Exportar Conversa** - Baixe o histórico em arquivo `.txt`
- **Limpeza de Histórico** - Apague todas as mensagens com um clique
- **Acessibilidade** - Labels ARIA, navegação por teclado (Shift+Enter para quebra de linha)
- **Design Responsivo** - Otimizado para mobile, tablet e desktop
- **Text-to-Speech** - Ouve as respostas do zumbi em português BR
- **Personalidade Zombie** - Rosnados, gemidos e ações entre asteriscos

## 🚀 Quick Start

### Pré-requisitos
- [Ollama](https://ollama.ai) instalado e rodando localmente
- Um modelo baixado (ex: `ollama pull llama3.2`)

### Instalação

1. Clone o repositório:
```bash
git clone https://github.com/robisonnorlei-ship-it/grokzomborg.git
cd grokzomborg
```

2. Inicie o Ollama:
```bash
ollama serve
```

3. Abra `index.html` no navegador:
```bash
# Opção 1: Abrir diretamente
open index.html

# Opção 2: Usar um servidor HTTP (recomendado)
python -m http.server 8000
# Então acesse: http://localhost:8000
```

## ⚙️ Configuração

No `index.html`, você pode customizar:

```javascript
// Endereço do Ollama (padrão: localhost:11434)
const API_URL = "http://localhost:11434/api/chat";

// Chave de armazenamento localStorage
const STORAGE_KEY = "grokzomborg_messages";
const MODEL_STORAGE_KEY = "grokzomborg_model";

// Intervalo de verificação de conexão (ms)
const HEALTH_CHECK_INTERVAL = 5000;
```

## 🛠️ Estrutura

```
grokzomborg/
├── index.html       # Aplicação completa (HTML + CSS + JS)
├── README.md        # Este arquivo
└── .gitignore       # Arquivos ignorados
```

## 🎮 Como Usar

1. **Digitar mensagens**: Use o campo de entrada para falar com GROKZOMBORG
2. **Quebra de linha**: Shift+Enter para múltiplas linhas
3. **Trocar modelo**: Use o dropdown no header
4. **Ver status**: O indicador verde/vermelho mostra conexão com Ollama
5. **Exportar**: Clique em "Exportar" para baixar o histórico
6. **Limpar**: Clique em "Limpar" para resetar a conversa

## 📱 Responsividade

- ✅ Desktop (1920+px)
- ✅ Tablet (768px - 1024px)
- ✅ Mobile (< 768px)

## 🎯 Características Avançadas

### Persistência
As mensagens são automaticamente salvas no localStorage. O histórico persiste entre sessões.

### Streaming
As respostas chegam em tempo real, não precisa esperar a resposta completa antes de começar a ler.

### Health Check
A cada 5 segundos, o cliente verifica se Ollama está ativo:
- 🟢 Verde = Conectado
- 🔴 Vermelho = Desconectado

### Acessibilidade
- Todos os controles têm labels ARIA
- Navegação completa por teclado
- Indicadores de status com `aria-live="polite"`

## 🐛 Troubleshooting

### "Desconectado" / Erro ao conectar

1. Verifique se Ollama está rodando:
```bash
curl http://localhost:11434/api/tags
```

2. Se retornar JSON, Ollama está OK. Tente recarregar a página.

3. Se a porta é diferente, edite `API_URL` no `index.html`

### Modelo não encontrado

Baixe o modelo antes de usar:
```bash
ollama pull llama3.2
ollama pull mistral
```

### Resposta muito lenta

- Aumentar RAM disponível para Ollama
- Usar um modelo menor (ex: neural-chat ao invés de llama3.2)
- Verificar CPU/GPU utilização

## 📝 Personalização

### Alterar personalidade do zumbi

Edite o `content` do `system` message no `messages` array:

```javascript
const messages = [
  {
    role: "system",
    content: `Você é GROKZOMBORG, um zumbi...
    // Seu prompt aqui
    `
  }
];
```

### Cores do tema

Edite as variáveis CSS no `<style>`:

```css
body {
  background: #0a0f0a;        /* Cor de fundo */
  color: #c8e6c9;             /* Cor de texto padrão */
}
```

## 📜 Licença

MIT - Veja LICENSE.md

## 🤝 Contribuições

Contribuições são bem-vindas! Sinta-se livre para:
- Reportar bugs
- Sugerir features
- Enviar PRs

## 👨‍💻 Autor

Criado com ❤️ e cérebro podre por [@robisonnorlei-ship-it](https://github.com/robisonnorlei-ship-it)

---

**GROKZOMBORG ESTÁ PRONTO PARA ROSNAR!** 🧟‍♂️
