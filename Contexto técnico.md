# 📚 Contexto Técnico: Certificados SSL no e-SUS e Android

Este documento explica, de forma simples, o motivo pelo qual certos tablets Android apresentam erro ao acessar sistemas web como o e-SUS APS, e como o uso da autoridade certificadora Let's Encrypt influencia isso.

## 🔒 Sobre os Certificados SSL

Serviços públicos como o e-SUS APS utilizam **certificados SSL/TLS** para garantir que a conexão entre o servidor e o navegador seja segura (HTTPS).

Esses certificados são emitidos por uma **Autoridade Certificadora (CA)**, que é uma entidade confiável reconhecida por navegadores e sistemas operacionais.

## 🏛️ Let's Encrypt

A **Let's Encrypt** é uma das principais autoridades certificadoras públicas e gratuitas do mundo. Ela fornece certificados para sites e serviços web, inclusive muitos sistemas municipais.

- Os certificados emitidos pela Let's Encrypt têm **validade de 90 dias**.
- São automaticamente renovados pelos servidores que os utilizam, sem necessidade de ação por parte do usuário final.
- Esses certificados são assinados digitalmente por um **certificado raiz** chamado **ISRG Root X1**.

## 📲 Tablets Android e o Erro de Certificado

Em alguns tablets Android — especialmente versões mais antigas ou sem atualizações recentes — o certificado raiz da Let's Encrypt (**ISRG Root X1**) **não é reconhecido por padrão**.

Isso faz com que o sistema operacional rejeite conexões HTTPS com sites que usam certificados assinados por essa CA, exibindo mensagens como "certificado inválido" ou "erro de segurança".

## ✅ Solução: Instalar o Certificado Raiz Manualmente

Ao instalar o **ISRG Root X1** manualmente no tablet Android, o sistema passa a confiar na Let's Encrypt, resolvendo o problema de conexão com sites como o do e-SUS APS.

- O certificado raiz tem validade até **2035**, ou seja, **não precisa ser substituído com frequência**.
- A instalação é feita apenas uma vez por dispositivo.

## 🛠️ Considerações Finais

Este ajuste é especialmente útil em ambientes públicos, como unidades de saúde, onde os tablets podem estar desatualizados ou com restrições de atualização. A instalação manual do certificado raiz permite o acesso seguro e contínuo aos sistemas essenciais, mesmo em dispositivos com suporte limitado.

