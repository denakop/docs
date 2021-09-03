- [IAB](#iab)
  - [Tag Principal](#tag-principal)
  - [Postitial Banner](#postitial)
  - [Under Banner](#under-banner)
  - [Side Banner](#side-banner)
    - [Exemplo Side Banner](#exemplo-side-banner)
  - [In-Text Banner](#in-text-banner)
    - [Exemplo In-Text Banner](#exemplo-in-text-banner)
  - [Scroll Banner](#scroll-banner)
    - [Exemplo Scroll Banner](#exemplo-scroll-banner)
- [Avançado](#avançado)
  - [Tamanhos Customizaveis](#tamanhos-customizaveis)
    - [Exemplo Tamanhos Customizaveis](#exemplo-tamanhos-customizaveis)
  - [Tamanhos Customizaveis Por Tipo de Dispositivo](#tamanhos-customizaveis-por-tipo-de-dispositivo)
    - [Exemplo Tamanhos Customizaveis Por Tipo de Dispositivo](#exemplo-tamanhos-customizaveis-por-tipo-de-dispositivo)
  - [Refresh do Banner Customizado](#refresh-do-banner-customizado)
    - [Exemplo Refresh do Banner Customizado](#exemplo-refresh-do-banner-customizado)
  - [Targetings Customizados Por Banner](#targetings-customizados-por-banner)
    - [Exemplo Targetings Customizados Por Banner](#exemplo-targetings-customizados-por-banner)
  - [Configurações Globais](#configurações-globais)
    - [Exemplo Configurações Globais](#exemplo-configurações-globais)

# IAB

Esta é a documentação de como implementar os formatos IAB no seu site.

---

## Tag Principal

Copie e cole o snippet de código abaixo dentro da tag `head` do seu site:

```html
<!-- IMPLEMENTAÇÃO COMEÇA AQUI -->
<script
  async
  src="https://securepubads.g.doubleclick.net/tag/js/gpt.js"
></script>
<script async src="https://v3.denakop.com/prebid.js"></script>
<script async type="text/javascript" src="/1/iab.denakop.com.js"></script>
<script>
  var denakop = denakop || { cmd: [] };
</script>
<!-- IMPLEMENTAÇÃO TERMINA AQUI -->
```

---

## Postitial

Para mostrar o formato `Postitial` siga as intruções do snippet abaixo:

```html
<script>
  denakop.cmd.push(function () {
    denakop.usePostitialBanner();
  });
</script>
```

---

## Under Banner

Para mostrar o formato `Under Banner` siga as intruções do snippet abaixo:

```html
<script>
  denakop.cmd.push(function () {
    denakop.useUnderBanner();
  });
</script>
```

---

## Side Banner

Para mostrar o formato `Side Banner` siga as intruções do snippet abaixo:

```html
<script>
  denakop.cmd.push(function () {
    denakop.useSideBanner({
      containerWidth: <CONTAINER_WITDH>
    });
  });
</script>
```

### Onde

- `<CONTAINER_WITDH>`: Largura da área útil de conteúdo do seu site

#### Exemplo Side Banner

```html
<script>
  denakop.cmd.push(function () {
    denakop.useSideBanner({
      containerWidth: 1130,
    });
  });
</script>
```

---

## In-Text Banner

Para mostrar o formato `In-Text Banner` coloque o snippet abaixo dentro da tag `body` exatamente onde você quer que o anúncio apareça

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "<DIV_NAME>",
        name: "intext",
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`

#### Exemplo In-Text Banner

```html
<div id="denakop-ad-intext">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-intext",
        name: "intext",
      });
    });
  </script>
</div>
```

---

## Scroll Banner

Para mostrar o formato `Scroll Banner` coloque o snippet abaixo dentro da tag `body` exatamente onde você quer que o anúncio apareça

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "<DIV_NAME>",
        name: "scroll",
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`

#### Exemplo Scroll Banner

```html
<div id="denakop-ad-scroll">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-scroll",
        name: "scroll",
      });
    });
  </script>
</div>
```

---

# Avançado

## Tamanhos Customizaveis

Para forçar o tamanho de anúncios utilize a seguinte configuração de Snippet abaixo:

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: '<DIV_NAME>',
        name: 'scroll',
        sizes: <CUSTOM_SIZES>
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`
- `<CUSTOM_SIZES>`: Array de tamanhos personalizados

#### Exemplo Tamanhos Customizaveis

```html
<div id="denakop-ad-scroll">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-scroll",
        name: "scroll",
        sizes: [[496, 80]],
      });
    });
  </script>
</div>
```

---

## Tamanhos Customizaveis Por Tipo de Dispositivo

Para forçar o tamanho de anúncios por tipo de dispositivo, utilize a seguinte configuração de Snippet abaixo:

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: '<DIV_NAME>',
        name: 'intext',
        sizes: <CUSTOM_SIZES>
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`
- `<CUSTOM_SIZES>`: Object de tamanhos personalizados

#### Exemplo Tamanhos Customizaveis Por Tipo de Dispositivo

```html
<div id="denakop-ad-intext">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-intext",
        name: "intext",
        sizes: {
          desktop: [[496, 80]],
          tablet: [[120, 600]],
          mobile: [[250, 250]],
        },
      });
    });
  </script>
</div>
```

---

## Refresh do Banner Customizado

Para forçar o refresh do banner customizado, utilize a seguinte configuração do Snippet abaixo:

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: '<DIV_NAME>',
        name: 'intext',
        refresh: <CUSTOM_REFRESH_TIME>
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`
- `<CUSTOM_REFRESH_TIME>`: Tempo em segundos que o banner vai realizar o refresh. O valor mínimo aceito é `30`segundos. Caso o valor passado for `0` ou `false`, será desabilitado o refresh.

#### Exemplo Refresh do Banner Customizado

```html
<div id="denakop-ad-intext">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-intext",
        name: "intext",
        refresh: 30,
      });
    });
  </script>
</div>
```

---

## Targetings Customizados Por Banner

Para forçar targeting customizado no banner, utilize a seguinte configuração do Snippet abaixo:

```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: '<DIV_NAME>',
        name: 'intext',
        targetings: <CUSTOM_TARGETINGS>
      });
    });
  </script>
</div>
```

### Onde

- `<DIV_NAME>`: `id` da `div`
- `<CUSTOM_TARGETINGS>`: Array com os targetings customizados para esse banner.

#### Exemplo Targetings Customizados Por Banner

```html
<div id="denakop-ad-intext">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd({
        divId: "denakop-ad-intext",
        name: "intext",
        targetings: [["teste", "123"]],
      });
    });
  </script>
</div>
```

---

## Configurações Globais

Para definir as configurações globais do Denakop utilize a configuração do Snippet abaixo:

```html
<script>
  denakop.cmd.push(function () {
    denakop.setPageConfig(
      { 
        lazyLoad: <ENABLE_LAZY_LOAD>,
        targetings: <CUSTOM_PAGE_TARGETING>,
        networkCode: <NETWORK_CODE>
      }
    );
  });
</script>
```

### Onde

- `<ENABLE_LAZY_LOAD>`: Habilita o lazy load de todos os elementos da página. Recebe `true` ou `false` como valor.
- `<CUSTOM_PAGE_TARGETING>`: Define os targetings personalizados para todos os banners da páigna.
- `<NETWORK_CODE>`: Define um network code adicional para os requests.

#### Exemplo Configurações Globais

```html
<script>
  denakop.cmd.push(function () {
    denakop.setPageConfig(
      { 
        lazyLoad: true,
        targetings: [["teste", "123"]],
        networkCode: "21715141650" 
      }
    );
  });
</script>
```

---
