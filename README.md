# NEODOJO — Landing Page

Página única (single-file) da **NEODOJO**, academia de Judô e Jiu-Jitsu da Família Kawazoe em Londrina, Paraná. Todo o site vive em um só arquivo `index.html`: HTML, CSS, animações e imagens estão embutidos, sem build e sem dependências locais para servir.

Instagram: [@neodojolondrina](https://instagram.com/neodojolondrina) · WhatsApp: [(43) 99162-9962](https://wa.me/5543991629962)

---

## Como rodar

Não há etapa de build. Basta abrir o arquivo:

```bash
# abra direto no navegador
open index.html        # macOS
xdg-open index.html    # Linux

# ou sirva localmente (recomendado, para o mapa do Google carregar)
python3 -m http.server 8000
# acesse http://localhost:8000
```

O mapa do Google Maps e as fontes do Google só carregam **com internet**. Abrindo o arquivo offline, o restante da página funciona normalmente; apenas o mapa fica em branco.

---

## Estrutura da página

A navegação é por âncoras, na ordem em que aparecem:

| Seção | Âncora | Conteúdo |
|---|---|---|
| Navbar | — | Logo centralizada no topo e botão **Agendar treino** (dropdown) |
| Hero | `#` | Marca d'água ネオ, título e chamada principal |
| Quem somos | `#posicionamento` | Posicionamento da academia |
| Em que acreditamos | `#metodo` | Princípios do método |
| De onde a gente vem | `#historia` | Linha do tempo da Família Kawazoe (1976 → 2026) |
| Quem te ensina | `#instrutores` | Cards dos professores com foto e graduação |
| Treinos | `#treinos` | Modalidades: Judô Baby, Judô Infantil, Judô, Jiu-Jitsu, No Gi |
| Grade de Treinos | `#horarios` | Tabela de horários por dia |
| Onde treinar | `#local` | Endereço e mapa do Google Maps clicável |
| Contato | `#contato` | CTA com WhatsApp e Instagram |
| Rodapé | — | Logo, modalidades e assinatura da família |

O botão **Agendar treino** abre um menu com quatro links de agendamento (NextFit), um por modalidade: Judô Adulto, Judô Infantil, Judô Baby e Jiu-Jitsu Adulto.

---

## Identidade visual

### Paleta

| Token | Hex | Uso |
|---|---|---|
| `--ink` | `#22242B` | Fundo principal |
| `--layer` | `#25282A` | Superfícies e blocos |
| `--paper` | `#FFFFFF` | Texto e detalhes claros |
| `--gold` | `#C8B560` | Destaque (CTA, links, acentos) |

O dourado é usado com parcimônia, só onde precisa puxar a atenção.

### Tipografia

- **Dela Gothic One** — títulos e display (via Google Fonts).
- **Potta One** — exclusiva do ícone ネオ (via Google Fonts).
- **FRICK 3.0**, **Degular Display** e **Necto Mono** — fontes licenciadas da marca. Estão como `@font-face` comentado, com fallbacks ativos (`Dela Gothic One`, `Archivo`/sans, `IBM Plex Mono`). Para usar as licenciadas, adicione os arquivos de fonte e descomente os blocos `@font-face`.

### Imagens

Logos e fotos dos instrutores estão embutidas como **base64** dentro do `index.html`. As fotos recebem filtro `grayscale` para manter o visual em preto e branco, e o mapa do Maps usa o mesmo tratamento.

---

## Detalhes técnicos

- **Animações:** GSAP + ScrollTrigger (via CDN) fazem os reveals ao rolar. A animação respeita `prefers-reduced-motion`: quem desativa movimento no sistema vê a página estática e completa.
- **Mapa:** iframe do Google Maps (sem chave de API) com uma camada clicável por cima — tocar no mapa abre a localização direto no Google Maps. Há também o link **Abrir no Google Maps**.
- **Responsivo:** layout testado em **1440px** (desktop) e **390px** (mobile), com `overflow` horizontal zerado. No mobile, o botão de agendamento encurta para caber ao lado da logo centralizada.
- **Agendamento:** integração por links externos do NextFit (abrem em nova aba).

---

## Localização

**Rua Ibiporã, 359, Sobreloja — Londrina, Paraná**

---

## Licença

Conteúdo, marca, logos e fotos são de propriedade da NEODOJO / Família Kawazoe. Uso restrito ao projeto.
