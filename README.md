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

[alura]: https://www.alura.com.br
[curso]: https://www.alura.com.br/curso-online-web-design-responsivo
[github-pages]: https://pages.github.com/
[repo]: https://jeffersondev.github.io/alura-web-design-responsivo/
[sergio]: https://cursos.alura.com.br/user/sergiolopes