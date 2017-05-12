# alura-web-design-responsivo
Curso de [Web Design Responsivo][curso] do [Alura][alura].

Este repositório contém a minha visão sobre o curso, as lições aprendidas e o projeto desenvolvido durante o curso.

---

## O curso

Neste curso o instrutor [Sérgio Lopes][sergio] nos ensina como desenvolver um website responsivo.

O projeto resultante desse curso está armazenado nesse repositório e pode ser visualizado [neste link][repo]. Ele está hospedado aqui no GitHub utilizando o [GitHub Pages][github-pages].

---

## Lições aprendidas

#### 1. Design Fluído com `%` e `em`

#### 2. Media Queries

#### 3. Viewport

#### 4. Workflow de desenvolvimento e testes

---

#### 1. Design Fluído

Quando temos que desenvolver um website que seja responsivo, a primeira coisa que temos que ter em mente é a utilização de medidas relativas. Devemos utilizar medidas relativas como o `%` e o `em` ao invés de deixar com medidas fixas definidas em `px`.

As duas medidas funcionam de forma parecida, pegam como base a propriedade do elemento pai. A diferença entre elas é que o `%` se baseia no `width` do elemento pai, enquanto o `em` é baseado no `font-size` do elemento pai.

---

#### 2. Media Queries

`Media Queries` são utilizados para definir um layout condicional para o seu site através do uso da sintaxe `@media`. É uma boa prática utilizar um design responsivo `Mobile Firt`, que significa fazer o CSS padrão para telas pequenas e utilizar `min-width` nas `Medias Queries` para definir o CSS para telas maiores. Esses `min-width` são `Breakpoints` onde outr layout (CSS) será aplicado, e esses `Breakpoints` devem ser definidos de acordo com o conteúdo do site sendo desenvolvido.

No exemplo abaixo temos um elemento com a class `secao`, que terá somente 1 coluna ocupando 100% da largura quando estiver em uma tela de até 599px (`Mobile First`). Em telas a partir de 600px esse elemento ocupará metade do espaço (50%) e ficarão lado a lado. Já em telas com 1000px ou mais de largura teremos 3 elementos, cada um ocupando 1/3 do espaço.

```css
.secao {
    width: 100%;
}

@media (min-width: 600px) {
    .secao {
        float: left;
        width: 50%;
    }
}
@media (min-width: 1000px) {
    .secao {
        float: left;
        width: 33.333%;
    }
}
```

---

#### 3. Viewport

>The viewport is the user's visible area of a web page.
>
> -- <cite>[w3schools][citacao]</cite>

Como definido no site do w3schools, o `viewport` é a área visível que a página web tem para ser renderizado. A área visível de um dispositivo mobile é bem menor que a de um desktop. Mas como todos os sites eram feitos para desktop, os navegadores dos primeiros dispositivos mobile que tinham condições para exibir uma página web passaram a 'simular' que tinham um `viewport` maior e faziam um `zoom out` da página para que todo o conteúdo fosse exibido sem quebrar o layout.

Isso acabou se tornando um comportamento padrão em todos os navegadores mobile. Por isso quando desenvolvemos uma página web com design responsivo temos que colocar uma `meta tag` para informar que o conteúdo página foi feito para se adaptar a telas de vários tamanhos.

```html
<meta name="viewport" content="width=device-width">
```

Essa `meta tag` quer dizer que o `viewport` deve ter a largura igual a largura do dispositivo em que está sendo exibido, ou seja, o navegador de dispositivo mobile não vai tentar 'simular' que tem um `viewport` maior do que realmente tem. Além disso, é possível adicionar mais um valor para o content dessa `meta tag`, o `initial-scale`, que define qual a escala (zoom) padrão quando abrir a página.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

No caso acima a escala inicial foi definida em `1` para que o navegador não faça `zoom in` nem `zoom out` no momento que estiver abrindo.

---

#### 4. Workflow de desenvolvimento e testes

Durante o desenvolvimento e testes de uma aplicação responsiva é importante utilizarmos as ferramentas e recursos a nosso favor para termos uma boa produtividade e qualidade. Então uma boa estratégia é utilizar as ferramentas de `Developer Tools` inclusas na maioria dos navegadores modernos para desenvolvermos e testarmos a responsividade do site/aplicação. Em seguida podemos fazer uso dos simuladores/emuladores dos dispositivos (Android / iOS / FirefoxOS / Windows Phone) para testarmos em um ambiente mais próximo do dispositivo real. Por fim, é muito interessante realizar testes nos dispositivos reais. Pois somente em um dispositivo real, com o SO / Navegador / Hardware verdadeiros é possivel verificar realmente como o site/aplicativo está se comportando. Com os testes nos dispositivos reais é possível realizar a conexão via USB para fazer a depuração através do Desktop/Mac.

 - Android: É possível abrir o inspetor no Chrome Desktop para depurar páginas abertas no Chrome de um dispositivo Android. Basta habilitar o Debug por USB no dispositivo e abrir o Chrome, depois disso no Chrome Desktop entrar em `chrome://inspect`.
 - iOS: Para quem possui um Mac, através do XCode é possível subir um simulador de um dispositivo (iOS, tvOS ou Apple Watch) e realizar o debug com o Safari instalado no Mac.
 - FirefoxOS: Existe também a possibilidade de simular um dispositivo FirefoxOS através do navegador Mozilla Firefox. Com o Firefox aberto basta ir na opção de Developer e procurar por WebIDE, lá terá uma opção para instalar e executar um simulador do FirefoxOS.
 - Outros: Para outros dispositivos/navegadores também é possível utilizar um inspetor remoto com a ferramenta `weinre`. O `weinre` pode ser instalado através do `npm`, e o funcionamento dele é com a inclusão de um script na página html que será testada. Depois pela linha de comando com o `weinre` subimos um "servidor" e acessamos o inspetor para os dispositivos que estão conectado via USB em um navegador no Desktop/Mac.

---

[alura]: https://www.alura.com.br
[citacao]: https://www.w3schools.com/css/css_rwd_viewport.asp
[curso]: https://www.alura.com.br/curso-online-web-design-responsivo
[github-pages]: https://pages.github.com/
[repo]: https://jeffersondev.github.io/alura-web-design-responsivo/
[sergio]: https://cursos.alura.com.br/user/sergiolopes