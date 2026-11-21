# ✍️ Corretor Inteligente PRO ULTRA

Aplicação web responsiva e *mobile-first* para **revisão gramatical, ortográfica e análise textual em tempo real**, desenvolvida em arquitetura *single-file* (HTML5, CSS3 e JavaScript ES6+) com suporte a modo escuro, histórico persistente, fallback offline e ponte nativa para **Google AdMob SDK (Android WebView)**.

---

## 🚀 Funcionalidades Principais

* **Análise Gramatical e Ortográfica Multilíngue**: Integração com a API pública do **LanguageTool** (`pt-BR`, `pt-PT`, `en-US`, `es`, `fr`, `de-DE`, `it`) com controle de concorrência (`AbortController`) e *timeout* automático de 6 segundos.
* **Resiliência Offline (Fallback Local)**: Quando a rede está indisponível ou a API externa falha, um motor local em Expressões Regulares entra automaticamente em ação para detectar:
  * Espaços duplicados;
  * Espaços antes de sinais de pontuação;
  * Pontuação repetida ou reticências irregulares;
  * Palavras duplicadas em sequência.
* **Correções Encadeadas Seguras**:
  * **Aplicação individual** com recálculo dinâmico de *offsets* (`shiftCorrectionsAfterEdit`), impedindo deslocamento de índices entre sugestões;
  * **Correção em lote ("Corrigir tudo")** processada de trás para frente com proteção contra sobreposição de trechos.
* **Editor Completo com Produtividade**:
  * Pilhas de **Desfazer (`Ctrl + Z`)** e **Refazer (`Ctrl + Y` / `Ctrl + Shift + Z`)**;
  * Importação de arquivos `.txt` e `.md` e exportação direta do texto revisado;
  * Síntese de voz nativa via **Web Speech API** (`speechSynthesis`);
  * Ajuste dinâmico de tamanho da fonte (`14px` a `24px`) e alternância entre **Tema Claro e Tema Escuro**;
  * Salvamento automático no `localStorage` e **Histórico das últimas 20 análises**.
* **Estatísticas em Tempo Real**: Contagem instantânea de caracteres (limite de 60.000), palavras, frases e erros detectados, acompanhada de visualização prévia com destaque visual nos trechos sinalizados.
* **Monetização via Google AdMob (Android WebView)**: Objeto `AdMobBridge` pré-configurado com os IDs oficiais de teste do Google AdMob para **Banner Fixo**, **Native Advanced** e **Interstitial** (com *cooldown* de 60 segundos).

---

## 🛠️ Tecnologias Utilizadas

* **Front-end**: HTML5 Semântico, CSS3 (Grid, Flexbox, Custom Properties, Animações), JavaScript Vanilla (ES6+)
* **APIs Web**: Fetch API, AbortController, Web Speech API, FileReader API, Clipboard API, LocalStorage
* **Serviços Externos**: LanguageTool REST API v2
* **Integração Mobile**: Interface JavaScript `window.AndroidAdMob` para Android WebView

---

## 📂 Estrutura do Projeto

```text
corretor-inteligente-pro-ultra/
├── index.html      # Aplicação completa (HTML + CSS + JS em arquivo único)
└── README.md       # Documentação do projeto
