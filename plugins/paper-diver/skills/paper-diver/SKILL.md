---
name: paper-diver
description: Use quando a pessoa quiser abrir a biblioteca Paper Diver, adicionar autos em PDF, consultar o índice documental ou conferir uma resposta com citações às páginas físicas do PDF.
---

# Biblioteca Paper Diver

Para abrir a biblioteca ou ajustar a experiência, chame `abrir_biblioteca`. Nos clientes compatíveis, o painel do Paper Diver permite arrastar PDFs. Se a pessoa pedir para adicionar arquivos e preferir escolhê-los nesta máquina, chame `adicionar_pdfs` e deixe a seleção com ela. A indexação usa os modelos visuais do serviço.

Use `listar_documentos` para identificar o PDF e conferir se o índice está pronto. Quando o nome for ambíguo, peça à pessoa que escolha.

## Como ler uma peça de `ver_indice`

- `start` e `end` são a primeira e a última página física da peça, ambas inclusive. O PDF começa na página 1. Uma entrada de 4 a 8 abrange cinco páginas.
- `label` é o tipo de peça sugerido. Use o nível de detalhe que o índice sustenta. Uma categoria geral é válida por si só.
- `confianca_classe` é a estimativa do classificador para esse tipo, a partir da primeira página da peça. Vai de 0 a 1. Por exemplo, 0,68 corresponde a 68%. O valor `null` indica que a estimativa está indisponível.
- `conferir_tipo: true` é um alerta automático para conferir a categoria na imagem. Quando o campo está ausente, a peça veio sem alerta. Nenhuma das situações informa se houve revisão humana.

## Como escolher as páginas

Use `ramo` para buscar uma categoria pelo nome ou ID e incluir as categorias abaixo dela. Por exemplo, `pronunciamento` inclui Juízo decisório e Sentença. Para localizar uma sentença, busque diretamente `sentenca`. Se precisar identificar outro ramo, consulte a [árvore de categorias](references/categorias.md).

Use `pagina_de` e `pagina_ate` para selecionar as peças que cruzam um intervalo físico. O filtro preserva a faixa inteira de cada peça. Para continuar a busca, repita os filtros e passe o valor de `proxima_peca` em `primeira_peca`. Se `pecas_sem_hierarquia` for positivo, confira também a faixa sem o filtro de ramo antes de concluir que uma peça está ausente.

Abra a imagem original com `ler_pagina` para confirmar cada valor, data ou acontecimento que for relatar. Se houver dúvida sobre o tipo ou o início da peça, confira também as páginas vizinhas. Identifique o PDF e cite a página física que sustenta cada fato. Para resumos, reúna as páginas que sustentam o pedido, as decisões e o estado do processo. Sinalize o que a leitura deixou em aberto.

Quando o usuário pedir para conectar a conta, chame `conectar_conta`. Peça que confira o código no portal e autorize o dispositivo antes de abrir a biblioteca.

Ao citar uma imagem lida por `ler_pagina`, use o nome do PDF e a página física. Quando a ferramenta devolver `url`, transforme a referência num link Markdown para essa URL exata, como [Nome do PDF, página física 3](URL retornada). Se a pessoa pedir para abrir a página citada, chame `abrir_biblioteca` com o mesmo `documento_id` e a mesma `pagina`.
