- [IAB](#iab)
  - [Tag Principal](#tag-principal)
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


# IAB

Esta é a documentação de como implementar os formatos IAB no seu site.

---------

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

---------

## Under Banner

Para mostrar o formato `Under Banner` siga as intruções do snippet abaixo:
```html
<script>
  var denakop = denakop || { cmd: [] };
  denakop.cmd.push(function () {
    denakop.showUnderPlacement(); // Implementar Under Banner
  });
</script>
```

---------

## Side Banner

Para mostrar o formato `Side Banner` siga as intruções do snippet abaixo:
```html
<script>
  var denakop = denakop || { cmd: [] };
  denakop.cmd.push(function () {
    denakop.showSidePlacement(<CONTAINER_WITDH>); // Implementar Side Banner
  });
</script>
```
### Onde
- `<CONTAINER_WITDH>`: Largura da área útil de conteúdo do seu site

#### Exemplo Side Banner
```html
<script>
  var denakop = denakop || { cmd: [] };
  denakop.cmd.push(function () {
    denakop.showSidePlacement(1130); // Implementar Side Banner
  });
</script>
```

---------

## In-Text Banner

Para mostrar o formato `In-Text Banner` coloque o snippet abaixo dentro da tag `body` exatamente onde você quer que o anúncio apareça
```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd('<DIV_NAME>', 'intext');
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
      denakop.displayAd('denakop-ad-intext', 'intext');
    });
  </script>
</div>
```

---------

## Scroll Banner

Para mostrar o formato `Scroll Banner` coloque o snippet abaixo dentro da tag `body` exatamente onde você quer que o anúncio apareça
```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd('<DIV_NAME>', 'scroll');
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
      denakop.displayAd('denakop-ad-scroll', 'scroll');
    });
  </script>
</div>
```

---------

# Avançado

## Tamanhos Customizaveis

Para forçar o tamanho de anúncios utilize a seguinte configuração de Snippet abaixo:
```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd('<DIV_NAME>', 'scroll', <CUSTOM_SIZES>);
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
      denakop.displayAd('denakop-ad-scroll', 'scroll', [[496, 80]]);
    });
  </script>
</div>
```

---------

## Tamanhos Customizaveis Por Tipo de Dispositivo

Para forçar o tamanho de anúncios por tipo de dispositivo, utilize a seguinte configuração de Snippet abaixo:
```html
<div id="<DIV_NAME>">
  <script type="text/javascript">
    denakop.cmd.push(function () {
      denakop.displayAd('<DIV_NAME>', 'intext', <CUSTOM_SIZES>);
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
      denakop.displayAd('denakop-ad-intext', 'intext', {
        desktop: [[496, 80]],
        tablet: [[120, 600]],
        mobile: [[250, 250]]
      });
    });
  </script>
</div>
```

---------
