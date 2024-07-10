# Gerador de Senhas

Um simples gerador de senhas feito em JavaScript, que gera senhas aleatórias com base nos critérios configurados pelo usuário.

## Funcionalidades

- **Slider de Tamanho**: Permite ao usuário selecionar o tamanho da senha desejada.
- **Caracteres Personalizados**: Utiliza um conjunto predefinido de caracteres para gerar a senha.
- **Cópia de Senha**: Opção para copiar a senha gerada para a área de transferência.

## Como Usar

1. Abra o arquivo `index.html` no seu navegador.
2. Ajuste o slider para escolher o tamanho da senha.
3. Clique no botão "Gerar Senha" para criar uma nova senha.
4. Clique no botão "Copiar Senha" para copiar a senha gerada para a área de transferência.

## Exemplo de Uso

```javascript
// Exemplo de inicialização dos elementos
let sliderElement = document.querySelector("#slider");
let buttonElement = document.querySelector("#button");
let sizePassword = document.querySelector("#valor");
let password = document.querySelector("#password");
let containerPassword = document.querySelector("#container-password");
let charset = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%";
let novaSenha = "";

// Função para gerar senha aleatória
function generatePassword() {
  let pass = "";
  for (let i = 0, n = charset.length; i < sliderElement.value; i++) {
    pass += charset.charAt(Math.floor(Math.random() * n));
  }

  containerPassword.classList.remove("hide");
  password.innerHTML = pass;
  novaSenha = pass;
}

// Função para copiar senha para a área de transferência
function copyPassword() {
  alert("Senha copiada com sucesso!");
  navigator.clipboard.writeText(novaSenha);
}
