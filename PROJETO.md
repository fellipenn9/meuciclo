# MeuCiclo

PWA para controle de ciclo menstrual com privacidade total. Todos os dados ficam localmente no dispositivo.

## Stack

- HTML + CSS + JS puro (arquivo unico `index.html`)
- Chart.js (CDN) para graficos de insights
- Service Worker para funcionamento offline
- LocalStorage para persistencia de dados

## Funcionalidades

### 5 Telas
1. **Painel (Dashboard)** — Circulo de progresso do ciclo, fase atual, contagem regressiva, acoes rapidas
2. **Calendario** — Visualizacao mensal com cores por fase, detalhes do dia, registro de menstruacao
3. **Registrar** — Fluxo, sintomas, humor, energia, muco cervical, atividade sexual, notas
4. **Analises (Insights)** — Estatisticas, grafico de ciclos, padroes de sintomas, visao anual
5. **Configuracoes** — Ciclo padrao, lembretes, PIN, export/import, disclaimer medico

### Algoritmo do Ciclo
- Ciclo medio = media dos ultimos 6 ciclos (ou padrao 28 dias)
- Ovulacao = inicio do ultimo ciclo + ciclo medio - 14
- Janela fertil = ovulacao - 5 ate ovulacao + 1
- Fases: Menstrual, Folicular/Seguro, Fertil, Ovulacao, Lutea

### Privacidade
- 100% local (LocalStorage)
- PIN opcional de 4 digitos
- Notificacoes discretas (sem detalhes pessoais)
- Export/Import JSON para backup

## Estrutura de Arquivos

```
MeuCiclo/
├── index.html              — App completo
├── sw.js                   — Service Worker (cache-first)
├── manifest.webmanifest    — PWA manifest
├── icon.svg                — Icone vetorial
├── icon-192.png            — Android icon
├── icon-512.png            — Splash/maskable
├── apple-touch-icon.png    — iOS
├── PROJETO.md              — Este arquivo
└── .github/workflows/deploy.yml
```

## Deploy

GitHub Pages via GitHub Actions (auto-deploy no push para main).

- **Repo**: `fellipenn9/meuciclo`
- **URL**: https://fellipenn9.github.io/meuciclo/

## Desenvolvimento

Abrir `index.html` direto no navegador para teste rapido.
Para testar Service Worker: `npx serve .` (requer localhost).

## Paleta de Cores

| Fase | Cor | Hex |
|------|-----|-----|
| Menstruacao | Vermelho coral | #E63946 |
| Fertil | Roxo | #8B5CF6 |
| Ovulacao | Pink | #EC4899 |
| Seguro | Verde | #10B981 |
| Lutea/TPM | Ambar | #F59E0B |

## Aviso Medico

O MeuCiclo e uma ferramenta de acompanhamento e NAO substitui orientacao medica. As previsoes sao estimativas baseadas em medias e podem variar. NAO use este app como metodo contraceptivo unico.
