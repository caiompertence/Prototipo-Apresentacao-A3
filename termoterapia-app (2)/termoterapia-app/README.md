# Termoterapia - protótipo de alta fidelidade

Abra `index.html` no Chrome ou no Edge (ou use a extensão Live Server do VS Code).
Sem servidor e sem bibliotecas. A fonte de leitura fácil (Atkinson Hyperlegible) também vem do Google Fonts. As fontes (Baloo 2 e Figtree) vêm do Google Fonts; sem internet o app usa fontes do sistema.

## Arquivos
- `index.html`: estrutura da página.
- `css/estilo.css`: cores e medidas (variáveis no `:root`) e estilos.
- `js/app.js`: tudo o resto, nesta ordem:
  1. Conteúdo: recursos (`R`), condições (`C`), objetivos (`O`), segurança (`SEG`), triagem (`Q`), orientações (`ORI`), informações (`INF`).
  2. Estado e navegação.
  3. Telas (objeto `V`, uma função por tela).
  4. Eventos (clique, change, input).

## Onde editar o conteúdo
- Fichas e textos científicos: `R`, `EX` e `SEG` em `js/app.js` (campos "a preencher" ficam nas telas `ficha` e `comp`).
- Perguntas e regra da triagem: `Q` e `decide`.
- Cores: `:root` em `css/estilo.css`.

## Dados salvos no navegador (localStorage)
`t_role`, `t_user` (nome, e-mail, CREFITO; a senha não é guardada), `t_reg`, `t_fav`, `t_lemb`, `t_notas`, `t_chat`, `t_ult`, `t_acc` (preferências de acessibilidade), `t_art` (biblioteca de artigos do fisioterapeuta).
Em Perfil > Apagar dados, tudo é removido, exceto o login.

Protótipo: o login não valida conta em servidor, o chat é simulado e a lista de fisioterapeutas próximos é de exemplo.

## Acessibilidade
Aba "Acessib." (e botão "Aa" antes do login): tamanho do texto, contraste (padrão, alto, escuro), negrito, espaçamento, fonte de leitura fácil, botões maiores, reduzir animações e leitura em voz alta. Código: `ACC`, `ap()` e `V.acc` em `js/app.js`; estilos `html[data-...]` em `css/estilo.css`.


## Biblioteca de artigos (fisioterapeuta)
Aba "Artigos": cadastro com título, autores, revista, ano, DOI ou link, tipo de estudo, certeza da evidência, condições e recursos relacionados, resultados e aplicação clínica. Os artigos vinculados aparecem na ficha do recurso (resultados, certeza e referências) e na contagem dos resultados da busca. Ficam salvos no navegador de cada pessoa; use "Importar ou exportar" para compartilhar com o grupo. O app não traz nenhum artigo pré-cadastrado, para não inventar referências. "Apagar dados" no Perfil não remove a biblioteca.


## Imagens
O app não traz imagens: os locais delas aparecem como espaços vazios com contorno tracejado, prontos para as fotos e ilustrações do grupo de fisioterapia. A tela inicial usa uma fotografia de fundo se existir o arquivo `img/fundo-inicio.jpg`; sem ele, mostra o fundo azul-marinho. Veja `img/LEIA-ME.txt` para a lista de espaços, tamanhos e como preencher (objeto `IM` e constante `FOTO` em `js/app.js`).
No arquivo único `termoterapia-app.html` (e no link publicado) não há pasta `img/`; lá as imagens precisam ir embutidas (endereço `data:` em `IM` e em `FOTO`). Se você me enviar as imagens, eu embuto.
