# Prototype Boilerplate 🚀

> **Starter kit de alta fidelidade para prototipagem de produtos digitais, focado em testes com usuários reais e validação ágil de conceitos de produto.**

Construído com **React 19**, **Vite**, **Tailwind CSS v4** e **Motion**, este boilerplate reproduz fielmente a sensação de um aplicativo móvel nativo (gestos de arrasto, feedback tátil, contadores animados e navegação sincronizada com a URL), pronto para ser compartilhado via link web ou testado em dispositivos móveis.

---

## ⚡ Começando em 3 Passos (Get Started)

### 1. Crie seu repositório a partir deste template
1. No topo desta página no GitHub, clique no botão verde **"Use this template"** > **"Create a new repository"**.
2. Escolha um nome para seu protótipo (ex: `teste-onboarding-pix`) e marque como público ou privado.
3. Clone o seu novo repositório na sua máquina:
   ```bash
   git clone https://github.com/seu-usuario/seu-prototipo.git
   cd seu-prototipo
   ```

### 2. Instale e execute localmente
```bash
npm install
npm run dev
```
Abra [http://localhost:3000](http://localhost:3000) no seu navegador. Você verá a aplicação rodando em uma moldura de smartphone com a Home e o fluxo navegável.

### 3. Crie a sua hipótese de teste
1. Crie uma pasta dentro de `src/journeys/<nome-do-seu-teste>/` (ou duplique a jornada existente em `src/journeys/emprestimo-neon/`).
2. Crie as telas e formulários do seu teste nessa pasta.
3. Conecte a sua jornada ao ponto de partida desejado (na **Home**, na vitrine de **Produtos** ou via **URL direta**).

---

## 📱 Recursos Prontos no Núcleo (Core)

Para que seus testes tenham verossimilhança de aplicativo real, o núcleo já entrega:

* **🏠 Tela Inicial Completa (`GlobalHomeScreen`)**: Saldo, extrato, atalhos rápidos e carrossel de ofertas para simular o primeiro contato do usuário com a nova feature.
* **🛍️ Vitrine de Produtos (`ProductsScreen`)**: Menu categorizado de produtos para testes de descoberta e arquitetura de informação.
* **🛡️ Tela de Placeholder (`SurfacePlaceholderScreen`)**: Fallback elegante para qualquer botão ou atalho fora do escopo do teste, evitando "telas quebradas".
* **⚖️ Fluxo Baseline (`/baseline/`)**: Mantém um fluxo de referência para permitir **testes comparativos A/B** (Hipótese de teste vs. Fluxo de controle) no mesmo ambiente.
* **✨ Micro-interações Nativas**:
  * `BottomSheet`: Gaveta inferior nativa com suporte a arrasto por gestos e feedback tátil (haptics).
  * `RouletteOdometer` & `AnimatedNumber`: Valores e contadores que giram com fluidez ao mudar sliders ou parâmetros.
  * `PinBottomSheet`: Teclado numérico seguro de 4 dígitos para validação de confirmação de transação.

---

## 🌐 Publicação Instantânea no GitHub Pages

Para rodar testes de usabilidade remotos com usuários sem precisar de backend ou infraestrutura:

1. No repositório do seu protótipo no GitHub, acesse **Settings > Pages**.
2. Na seção **Build and deployment > Source**, selecione **GitHub Actions**.
3. Faça um push para a branch `main`:
   ```bash
   git push origin main
   ```
4. O GitHub Actions compilará a aplicação e publicará o link público automaticamente em segundos!

---

## 🎨 Herança Contínua: Design System & Core

Se o **Design System** ou o **Core** do template forem atualizados no futuro, você pode herdar as melhorias para o seu protótipo com um único comando:

* **Atualizar apenas o Design System (Cores, Tipografia e Tokens)**:
  ```bash
  npm run sync:ds
  ```
* **Atualizar tudo (Design System + Core + CI/CD de Deploy)**:
  ```bash
  npm run sync:template
  ```

> **Por que é seguro?** O código do seu teste fica 100% isolado dentro de `src/journeys/`. Como o template só altera `src/core/` e `src/design-system/`, a atualização ocorre de forma limpa pelo Git, sem conflitos com as suas telas de negócio.

---

## 📁 Estrutura de Pastas

```
prototype-boilerplate/
├── .github/workflows/deploy-pages.yml # Deploy automatizado no GitHub Pages
├── public/assets/                    # Ícones e ilustrações estáticas
├── scripts/                          # Scripts de sincronização contínua
├── src/
│   ├── core/                         # NÚCLEO DO BOILERPLATE
│   │   ├── shell/                    # Moldura mobile, StatusBar e barras
│   │   ├── screens/                  # Home, Produtos e Placeholders
│   │   ├── baseline/                 # Fluxo de controle para testes A/B
│   │   ├── components/               # BottomSheet, contadores e haptics
│   │   └── router/                   # Motor de rotas sincronizado com a URL
│   ├── design-system/                # Tokens visuais (Tailwind v4) e wrappers
│   │   ├── tokens.css
│   │   └── components/Button.tsx
│   └── journeys/                     # ONDE VOCÊ CRIA SEUS PROTÓTIPOS
│       └── seu-teste/                # Suas telas, regras e dados de teste
└── package.json
```

---

## 🛠️ Comandos Disponíveis

| Comando | Descrição |
| :--- | :--- |
| `npm run dev` | Inicia o servidor local de desenvolvimento na porta `3000` |
| `npm run build` | Compila o protótipo para produção em `dist/` com fallback SPA |
| `npm run lint` | Validação estática de tipos TypeScript (`tsc --noEmit`) |
| `npm run sync:ds` | Sincroniza cirurgicamente a pasta de Design System com o template |
| `npm run sync:template` | Sincroniza o Core e Design System completos com o template |
