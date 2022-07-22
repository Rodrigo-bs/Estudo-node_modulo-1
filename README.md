# Módulo 1
--- 

Configuração do ambiente, instalação das dependências e conceitos básicos.

<p>O modelo de desenvolvimento é utilizando typescript e traduzindo para código JavaScript. Para isso utilizamos o comando <code>tsc -W</code> para iniciar o modo de observação (Responsável por fazer a tradução do TypeScript para JavaScript), mas antes disso precisamos fazer algumas configurações:</p>


- No arquivo tsconfig.json, temos que habilitar as seguintes configurações:

```json
"module": "commonjs", // Pasta onde o JavaScript vai ser gerado.
"rootDir": "./src", // Pasta onde o TypeScript vai está.
"moduleResolution": "node", 
```

### Import/Export em CommonJs
---

Arquivo index.js
```typeScript
const Matematica = require('./Matematica');

let n1: number = 10;
let n2: number = 2;

console.log(Matematica.somar(n1, n2));
console.log(Matematica.subtrair(n1, n2))
```

Arquivo Matematica.js
```javascript
function somar(x: number, y: number) {
    return x + y;
}

function subtrair(x: number, y: number) {
    return x - y;
}

function multiplicar(x: number, y:number) {
    return x * y;
}

module.exports.somar = somar;
module.exports.subtrair = subtrair;
module.exports.multiplicar = multiplicar;
```