# Laravel em Executável com Banco de Dados Local
Um executável compilado pelo Electron com estrutura de Laravel e banco de dados de SQLITE.
- *Desenvolvimento de executáveis com estrutura front-end e back-end em Laravel e db Sqlite*

**Para Baixar os Componentes do Electron**
```
npm install
npm start
```
**Para Baixar os Componentes do Laravel**
```
cd structure
Composer Install
copy (cp) .env.example .env
php artisan key:generate
```

***No arquivo .env***
```
DB_CONNECTION=sqlite
DB_DATABASE=../database/database.db
```

Nota: Se você estiver usando o Linux Bash para Windows, [veja este guia](https://www.howtogeek.com/261575/how-to-run-graphical-linux-desktop-applications-from-windows-10s-bash-shell/) ou use o `node` no prompt de comando.


## Configuração
Você pode passar um retorno de chamada para o método run, isso será chamado quando o servidor PHP estiver ativo e em execução. Se você não passar um retorno de chamada para o método run, será retornada uma promessa que resolve quando o servidor PHP estiver ativo e em execução. Isso você precisa fazer no arquivo main.js de onde você encontra o comentário

## Configuração

Nome | Default | Descrição
-----|---------|------------
`php` | `php` | O arquivo de comando do php
`host` | `127.0.0.1` | O host do servidor
`port` | `8000` | A porta usado
`directory` | `null` | A raiz do documento. Por padrão, é o diretório de trabalho atual
`script` | `null` | O script "roteador"
`stdio` | `inherit` | stdio opção passada para o processo gerado - https://nodejs.org/api/child_process.html#child_process_options_stdio
`directives` | `{}` | Um objeto com as diretivas personalizadas do PHP
`config` | `null` | O caminho de um arquivo php.ini personalizado
`env` | `process.env` | As variáveis de ambiente passadas

Exemplo:

```js
const PHPServer = require('php-server-manager');

const server = new PHPServer({
    port: 3000,
    directives: {
        display_errors: 0,
        expose_php: 0
    }
});

server.run();
```

## Licenças

[CC0 1.0 (Public Domain)](LICENSE.md)
