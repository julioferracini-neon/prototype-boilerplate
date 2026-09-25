# AGENTS.md

## 1. Visão Geral
Boilerplate oficial para criação rápida de protótipos navegáveis (SPAs client-side) de alta fidelidade e micro-interações nativas.
Projetado especificamente para **testes de usabilidade com usuários reais** e **validação ágil de hipóteses de produto**.

## 2. Arquitetura: Núcleo (Core) vs. Jornada (Journeys)
- **Regra Central de Isolamento**:
  - Todo o código de uma hipótese de teste (telas, textos, regras simuladas e dados mockados) deve residir isolado em `src/journeys/<nome-da-jornada>/`.
  - O núcleo (`src/core/`) e o Design System (`src/design-system/`) devem permanecer agnósticos a regras de negócio de produtos específicos.
- **Telas Reutilizáveis do Core**:
  - `src/core/screens/GlobalHomeScreen.tsx`: Ponto de partida padrão do app.
  - `src/core/screens/ProductsScreen.tsx`: Vitrine de produtos para testes de descoberta.
  - `src/core/screens/SurfacePlaceholderScreen.tsx`: Fallback para fluxos fora do escopo do teste.
  - `src/core/baseline/`: Fluxo de controle para testes comparativos A/B.
- **Zero Backend**: Aplicação 100% estática. Proibido adicionar backend, APIs ativas ou persistência em banco de dados.

## 3. Design System (Adapter)
- **Estrutura**: `src/design-system/tokens.css` (tokens via Tailwind v4) e `src/design-system/components/` (wrappers finos).
- **Consumo Obrigatório**: Componentes de jornada devem consumir exclusivamente os wrappers de `src/design-system/` ou classes utilitárias semânticas.
- **Proibição de Hex Arbitrário**: Proibido adicionar estilos com valores hardcoded (ex: `text-[#142742]`). Utilize tokens primitivos e semânticos (`--color-surface-primary`, `--color-text-primary`, `--color-action-default`).

## 4. Scripts e Herança
- `npm run dev`: Servidor local em `http://0.0.0.0:3000`.
- `npm run build`: Compila bundle estático em `dist/`.
- `npm run lint`: Checagem estática de tipos (`tsc --noEmit`).
- `npm run sync:template`: Sincroniza núcleo e design system a partir do template central.
- `npm run sync:ds`: Sincroniza cirurgicamente apenas a pasta de Design System.
