# 🤡 Projeto Memes - Integração com API Pública

![Status](https://img.shields.io/badge/Status-Finalizado-green)

Este repositório registra minha primeira experiência prática no consumo e tratamento de dados **JSON** provenientes de uma API pública. O projeto foi desenvolvido como um exercício acadêmico, focado em transformar dados brutos em uma interface amigável e dinâmica para o usuário.

## 🚀 Principais Aprendizados

O desenvolvimento deste projeto foi um marco importante para entender como o front-end recebe e processa informações externas:

- 📡 **Consumo de API (JSON)**: Aprendi a realizar requisições assíncronas para a API do Imgflip, extraindo objetos e arrays de dados para uso na aplicação.
- ⚡ **Manipulação Dinâmica do DOM**: Utilização de JavaScript para injetar conteúdo dinamicamente no HTML, utilizando *template literals* para criar componentes de forma eficiente.
- 🎨 **Estilização com Bootstrap**: Como é meu padrão de design, utilizei o **Bootstrap** para criar uma galeria de cartões (Cards) responsiva, com sombras e espaçamentos que garantem uma interface moderna.
- 🧩 **Lógica de Iteração**: Implementação de loops (`for...of`) para percorrer grandes volumes de dados e renderizar múltiplos elementos automaticamente.

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: JavaScript (ES6+).
- **Estruturação**: HTML5.
- **Design/UI**: Bootstrap 5.
- **Bibliotecas**: jQuery (utilizado para o método `$.getJSON`).
- **Fonte de Dados**: API Imgflip.

## 🖥️ Resultado Final

A aplicação exibe uma lista infinita de memes em um layout de cartões organizados, adaptando-se perfeitamente a dispositivos móveis e desktops:

![final_result](images/final_result.png)

## 🔍 Snippet: Integração de Dados

Abaixo, um exemplo da lógica principal utilizada para consumir a API e construir a interface:

```js
$.getJSON("[https://api.imgflip.com/get_memes](https://api.imgflip.com/get_memes)", (response) => {
    for (let m of response.data.memes) {
        document.getElementById("memes").innerHTML += 
            `<br><div class="card m-auto p-3 shadow-lg mb-3" style="width: 18rem;">
                <div class="card-body">
                    <h5 class="card-title text-center">${m.name}</h5>
                </div>
                <img src=${m.url} class="card-img-top shadow rounded" alt="memeID_${m.id}">            
            </div>`;
    }
});
