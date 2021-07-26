
# IAB

Esta é a documentação de como implementar os formatos IAB no seu site.

- [Tag Principal](#tag-principal)
- [Under Banner](#under-banner)
- [Side Banner](#side-banner)

## Tag Principal

Copie e cole o código abaixo dentro da tag `head` do seu site:
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

## Under Banner

Para mostrar o formato `Under Banner` utilize a seguinte exemplo de Snnipet
```html
<script>
  var denakop = denakop || { cmd: [] };
  denakop.cmd.push(function () {
    denakop.showUnderPlacement(); // Implementar Under Banner
  });
</script>
```

## Side Banner

Para mostrar o formato `Under Banner` utilize a seguinte exemplo de Snnipet
```html
<script>
  var denakop = denakop || { cmd: [] };
  denakop.cmd.push(function () {
    denakop.showSidePlacement(1130); // Implementar Side Banner
  });
</script>
```
