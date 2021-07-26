- [IAB](#iab)
  - [Tag Principal](#tag-principal)
  - [Under Banner](#under-banner)
  - [Side Banner](#side-banner)
  - [In-Text Banner](#in-text-banner)
  - [Scroll Banner](#scroll-banner)
- [Avançado](#avancado)
  - [Tamanhos Customizaveis](#tamanhos-customizaveis)


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
| Placebolder  | Descrição     |
|--------------|---------------|
| `<DIV_NAME>` | `id` da `div` |

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
| Placebolder  | Descrição     |
|--------------|---------------|
| `<DIV_NAME>` | `id` da `div` |

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
| Placebolder      | Descrição                                      |
|------------------|------------------------------------------------|
| `<DIV_NAME>`     | `id` da `div`                                  |
| `<CUSTOM_SIZES>` | Tamanhos personalizados, exemplo `[[496, 80]]` |

---------
