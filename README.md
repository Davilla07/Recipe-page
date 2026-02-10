# Frontend Mentor - Solução da página de receita

Esta é uma solução para o [desafio Recipe page do Frontend Mentor](https://www.frontendmentor.io/challenges/recipe-page-KiTsR8QQKm). Os desafios do Frontend Mentor ajudam você a aprimorar suas habilidades de codificação construindo projetos realistas.

## Sumário

- [Visão geral](#visão-geral)
  - [Captura de tela](#captura-de-tela)
  - [Links](#links)
- [Meu processo](#meu-processo)
  - [Ferramentas utilizadas](#ferramentas-utilizadas)
  - [O que aprendi](#o-que-aprendi)
  - [Desenvolvimento futuro](#desenvolvimento-futuro)
  - [Recursos úteis](#recursos-úteis)
- [Autor](#autor)

## Visão geral

### Captura de tela

![![alt text](screenshot.png)](./screenshot.jpg)


### Links

- URL da solução: [https://github.com/seuusername/recipe-page](https://github.com/seuusername/recipe-page)
- URL do site ao vivo: [https://seuusername.github.io/recipe-page](https://seuusername.github.io/recipe-page)

## Meu processo

### Ferramentas utilizadas

- HTML5 semântico
- Variáveis CSS (Custom Properties)
- Flexbox
- Design responsivo (media queries)
- Workflow mobile-first
- Unidades relativas (rem, %, vw)
- Google Fonts (Young Serif, Outfit)
- CSS Reset
- Clamp() para tipografia responsiva
- Overflow-x para tabelas responsivas

### O que aprendi

Este projeto representou um **salto significativo** em relação ao meu desafio anterior (Social Links Profile). Aqui estão os principais aprendizados:

**1. Conversão completa de pixels para unidades relativas**

No desafio anterior, eu ainda usava valores em pixels fixos para muitos espaçamentos. Neste projeto, **converti 100% dos valores para `rem`**, criando um layout verdadeiramente fluído:

```css
:root {
  --font-size-paragraph: 1rem; /* 16px */
  --border-radius: 1.125rem; /* 18px */
  --border-shadow: 0.25rem 0.25rem 0.75rem rgba(0, 0, 0, 0.1);
}

.recipe-container {
  padding: 1.5rem; /* 24px */
}

.preparation-time {
  padding: 1.625rem 2.5rem; /* 26px 40px */
}
```
**Por que isso importa**: Unidades relativas escalam melhor em diferentes tamanhos de tela e facilitam a manutenção do código.

**2. Tipografia responsiva com clamp()**
Aprendi a usar a função clamp() para criar tamanhos de fonte que se adaptam automaticamente ao viewport:
```css
.recipe-name {
  font-size: clamp(1.5rem, 5vw, 2.5rem);
}

.preparation-time h4 {
  font-size: clamp(1rem, 0.85rem + 0.75vw, 1.25rem);
}
```
**Como funciona:**
- clamp(min, preferred, max) define um valor mínimo, preferido e máximo
- O valor "preferred" usa vw (viewport width) para escalar com a tela
- Em telas pequenas, usa o valor mínimo; em telas grandes, usa o valor máximo

**3. Flexbox avançado com gap**
No desafio anterior, eu usava apenas Flexbox básico para centralização. Neste projeto, apliquei Flexbox em listas para criar layouts mais flexíveis:
```css

.ingredients-list {
  display: flex;
  flex-direction: column;
  gap: 0.3rem 0; /* Espaçamento entre itens */
}

.instruction-list {
  display: flex;
  flex-direction: column;
  gap: 0.1rem 0;
}
```
**Vantagens do gap:**
- Elimina a necessidade de margens manuais entre itens
- Cria espaçamento consistente
- Funciona perfeitamente com flex-direction: column

**4. Design responsivo com media queries estratégicas**
Implementei breakpoints baseados nos designs fornecidos (mobile: 375px, desktop: 1440px):
```css
/* Mobile-first: estilos base para telas pequenas */
.recipe-container {
  padding: 1.5rem;
}

/* Tablet: 769px+ */
@media (min-width: 769px) {
  .recipe-container {
    padding: 1.75rem 2.25rem;
  }
}

/* Desktop: 1025px+ */
@media (min-width: 1025px) {
  .recipe-container {
    padding: 1.875rem 2.5rem;
  }
}
```
**Abordagem mobile-first:**
- Começa com estilos para mobile
- Adiciona melhorias para telas maiores
- Reduz código duplicado
- Melhor performance em dispositivos móveis

**5. Tabelas responsivas com overflow-x**
Para garantir que a tabela de nutrição não quebre o layout em telas pequenas:
```css

.table-wrapper {
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  width: 100%;
}

.nutrition-table {
  min-width: 100%;
}
```
**Como funciona:**
- overflow-x: auto permite rolagem horizontal se necessário
- min-width: 100% garante que a tabela ocupe toda a largura disponível
- -webkit-overflow-scrolling: touch melhora a experiência em dispositivos móveis

## Desenvolvimento futuro ##

## Pontos fortes do projeto:
✅ Design responsivo completo - O layout se adapta perfeitamente de mobile a desktop
✅ Unidades relativas consistentes - 100% dos valores convertidos para rem
✅ Variáveis CSS bem organizadas - Cores, fontes e medidas centralizadas no :root
✅ Flexbox aplicado corretamente - Uso de gap e flex-direction em listas
✅ Tipografia responsiva - Função clamp() para tamanhos de fonte adaptáveis
✅ Acessibilidade - HTML semântico com tags apropriadas (<h1>, <h2>, <ul>, <ol>, <table>)

## Áreas para aprimorar nos próximos projetos:
🔧 CSS Grid Layout - Explorar layouts bidimensionais para estruturas mais complexas
🔧 Metodologia BEM - Adotar convenção de nomenclatura para classes CSS mais escaláveis
🔧 Transições e animações - Adicionar micro-interações suaves para melhor experiência do usuário
🔧 Custom Properties avançadas - Criar variáveis para breakpoints e espaçamentos padrão
🔧 Performance de imagens - Implementar srcset e sizes para otimização de imagens responsivas

## Próximos conceitos a dominar:
- CSS Grid Layout - Para criar layouts complexos com linhas e colunas
- Metodologia BEM - Para nomeação consistente e escalável de classes CSS
- Pré-processadores CSS (SASS) - Para variáveis avançadas, mixins e funções
- Bootstrap - Para prototipagem rápida e componentes responsivos
- Tailwind CSS - Para desenvolvimento ágil com utilitários
- Transições e animações CSS - Para micro-interações e feedback visual
- Acessibilidade avançada - ARIA labels, contraste de cores, navegação por teclado

## Recursos úteis
- MDN Web Docs - CSS Custom Properties - Guia completo sobre variáveis CSS
- CSS-Tricks - Guia Completo do Flexbox - Referência definitiva para Flexbox
- MDN - clamp() - Documentação oficial da função clamp()
- Google Fonts - Young Serif - Fonte serifada usada nos títulos
- Google Fonts - Outfit - Fonte sans-serif usada nos parágrafos
- CSS Units - PX vs EM vs REM - Entendendo unidades relativas
- Responsive Design - Media Queries - Guia de media queries

## Autor ##
Frontend Mentor - @Davilla07
GitHub - @Davilla07