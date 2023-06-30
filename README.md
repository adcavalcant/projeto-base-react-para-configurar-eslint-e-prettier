# Configuração do Prettier com o ESLint para projetos React

Este tutorial tem como objetivo mostrar como configurar o Prettier em conjunto com o ESLint para resolver conflitos entre as duas ferramentas e garantir uma formatação consistente de código em projetos React.

## Pré-requisitos

Antes de começar, verifique se você possui os seguintes requisitos instalados:

- Node.js
- Yarn (ou NPM)
- Visual Studio Code (ou outro editor de texto de sua preferência)

## Passo a passo

Siga os passos abaixo para configurar corretamente o Prettier com o ESLint em seu projeto React:

1. Crie uma configuração local do ESLint executando o seguinte comando no terminal:
```
yarn create @eslint/config
```

2. Certifique-se de que os plugins ESLint e Prettier - Code formatter estejam instalados no seu editor de texto.

3. Instale as dependências necessárias executando o seguinte comando no terminal:
```
yarn add -D eslint-config-prettier prettier
```

4. Abra o arquivo `.eslintrc` no diretório raiz do seu projeto e adicione `"prettier"` na seção `"extends"`, como mostrado abaixo:

```json
{
  "extends": [
    "...",
    "prettier"
  ]
}
```

5. No arquivo settings.json do Visual Studio Code, adicione a seguinte configuração para formatar automaticamente o código ao salvar o projeto:
```json
[...]
"editor.formatOnSave": true
```

6. Crie um arquivo settings.json no diretório .vscode do seu projeto e adicione o seguinte conteúdo para padronizar a formatação em arquivos JavaScript React.
```json
{
  "editor.formatOnSave": true,
  "[javascriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

7. Crie um arquivo extensions.json no diretório .vscode do seu projeto para recomendar extensões ao baixar o projeto em outra máquina:
```json
{
  "recommendations": ["esbenp.prettier-vscode", "dbaeumer.vscode-eslint"]
}
```

8. Crie um arquivo .prettierrc no diretório raiz do seu projeto e defina as configurações do Prettier de acordo com suas preferências. Por exemplo:
```json
{
  "singleQuote": true
}
```

9. No arquivo .eslintrc, remova ou ajuste as regras que não serão utilizadas no seu projeto. Por exemplo:
```json
"rules": {
  "react/react-in-jsx-scope": "off"
}
```

10. Realize as personalizações desejadas nos arquivos .eslintrc e .prettierrc para ajustar as configurações de acordo com suas preferências.

Com essas configurações, você terá o Prettier e o ESLint funcionando em conjunto para garantir uma formatação consistente de código em seu projeto React. Certifique-se de reiniciar seu editor de texto para que as alterações tenham efeito.
