# Trv Proxy for VTEX


### *`🇧🇷 (PT-BR)`*

Redirecione os tráfego dos assets de lojas VTEX para ter controle local e fazer alterações sem impactar o ambiente de produção, para lojas que utlizam estrutura CMS.

Imagens, arquivos de CSS e JS, entre outros. <!-- Liberte-se de Apps como Charles Proxy, Fiddler, Resource Override, Requestly.... -->

Este projeto é indicado para equipes de desenvolvimento, QA, suporte, ou quem tiver interesse em realizar testes sem atualizar nada no ambiente produtivo antes de ter certeza que tudo está como esperado. Ele executa em modo terminal, linha de comando e nãoestá disponúvel a versão de interface gráfica.

> Note: Indique a funcionalidade dos seus sonhos. Veja o item [notas](#Notas)

![image](https://user-images.githubusercontent.com/504327/125539104-38c4406c-a820-4146-ab30-a40ff0b057ab.png)

Para ter acesso na sua loja, veja o tópico [Notas](#Notas)

#### A aplicação levanta um servidor HTTPS e busca arquivos dentro pasta local e caso não encontre um arquivo, ele deixa o fluxo padrão seguir e busca o arquivo remoto. 


### Estrutura de diretórios

Neste momento server HTTPS está mapeando as seguintes pastas locais (leia-se diretórios, path na URL).

 - */arquivos*
 - */files*
 - */customElements*
 - */htmltemplates*
 - */partials*
 - */subtemplates*

Todas as pastas acima são mapeadas para o ambiente local. E ao utilizar o endereço local, será verificado se o arquivo solicitado está dentro de uma destas pastas. Caso não exista, o proxy realizará a chamada diretamente ao domínio da loja VTEX. Caso este arquivo também não exista online, o retorno comum da plataforma VTEX será entregue na requisição.

Obs: Este projeto não possui render dos componentes Vtex. Em breve novidades por aqui 😎.


## Disponível para as plataformas:
 
- [Linux](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-linux)
- [MacOS](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-macos)
- [Windows](https://github.com/Trivod/trv-vtex-proxy/raw/master/bin/TrivodProxy-win.exe)



## Como utilizar:

 1. Baixe o utilitário referente ao seu *S.O* em um dos links acima
 2. Coloque o arquivo na raiz do projeto
 3. Rode o utilirário com o comando abaixo:


```shell
./TrivodProxy-macos -f ./config.json -p 4433
```

> É possível rodar o utilitário sem o passar o arquivo de configuração como parâmetro. Dessa forma, ele busca a chave `vtex` dentro do **package.json**. Apenas crie a estrutura conforme o exemplo de configuração mais abaixo.

O parâmetro `-f ./config.json` **(pode ser qualquer nome)** indica o arquivo de configuração que deve possuir a chave `vtex` com o atributo `store` para ativar baseado no nome da loja.


O parâmetro `-p 4433` indica a porta para o servidor HTTP

Após a execução, será impresso no terminal a URL local do projeto.

É indicado que você utilize essa URL mapeada em seu arquivo `hosts` caso necessário, para que seja possível uma melhor experiência com a navegação.


## Exemplo de arquivo de configuração
```json
{
    "vtex": {
        "store": "vtex-store-name-id",
      }
}
```



## FAQ

### URL Insegura

Sim, neste momento, ainda, o SSL está self-signed para o ambiente disponível pelo proxy. É necessário adicionar o certificado como válido para continuar a navegação.

### Para Linux

Pode ser necessário configurar o aplicativo para que seja possível executálo com as permissões necessários como:

`chmod +x TrivodProxy-linux`.


## Notas

Neste momento o proxy está em modo fixo para algumas lojas. Para que seja possível utilizar na sua loja, envie um email para suporte+trvproxy@trivod.com com o título "acesso ao trv-vtex-proxy" e indique no corpo do e-mail o nome da loja Vtex a qual você deseja utilizar no trv-vtex-proxy.

Em breve estaremos postando novidades relacionadas a novas funcionalidades, incluindo estrutura para qualquer tipo de projeto e não apenas Vtex. Ative o modo observador aqui do projeto para acompanhar novas versões publicadas.

Caso queira indicar ou solicitar funcionalidades extras, fique a vontade para abrir uma Issue e descrever sua necessidade ou ideia para o projeto, ou também pode enviar por email para suporte+trvproxy@trivod.com.
