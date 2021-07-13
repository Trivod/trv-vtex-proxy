# TRV VTEX PROXY

### *`🇧🇷 (PT-BR)`*


## Redirecione os tráfego dos assets de lojas VTEX para ter controle local e fazer alterações sem impactar o ambiente de produção.

#### A aplicação levanta um servidor HTTP e busca arquivos dentro pasta local `dist` e caso não encontre um arquivo, ele deixa o fluxo padrão seguir e busca o arquivo remoto. 

<br />

### As pastas mapeadas são:

 - *arquivos*
 - *files*
 - *customElements*
 - *htmltemplates*
 - *partials*
 - *subtemplates*

<br />

## Baixe para as plataformas:
 
- [Linux](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-linux)
- [MacOS](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-macos)
- [Windows](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-win.exe)


<br />

## Como utilizar:
 1. Baixe o utilitário referente ao seu *S.O* em um dos links acima
 2. Coloque o arquivo na raiz do projeto
 3. Rode o utilirário com o comando abaixo:
<br />

```shell
./TrivodProxy-macos -f ./config.json -p 4433
```
<br />

> É possível rodar o utilitário sem o passar o arquivo de configuração como parâmetro. Dessa forma, ele busca a chave `vtex` dentro do **package.json**

O parâmetro `-f ./config.json` **(pode ser qualquer nome)** indica o arquivo de configuração que deve possuir a chave `vtex` com o atributo `store` para ativar baseado no nome da loja.

<br />

O parâmetro `-p 4433` indica a porta para o servidor HTTP

<br />

## Exemplo de arquivo de configuração
```json
{
    "vtex": {
        "store": "vtex-store-name-id",
      }
}
```

<br />

## Para Linux:
Execute `chmod +x TrivodProxy-linux`.
