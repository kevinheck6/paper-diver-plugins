---
name: paper-diver
description: Use quando a pessoa quiser abrir a biblioteca Paper Diver, adicionar autos em PDF, consultar o índice documental ou conferir uma resposta com citações às páginas físicas do PDF.
---

# Biblioteca Paper Diver

Para abrir a biblioteca ou ajustar a experiência, chame `abrir_biblioteca`. Nos clientes compatíveis, o painel do Paper Diver permite arrastar PDFs. Se a pessoa pedir para adicionar arquivos e preferir escolhê-los nesta máquina, chame `adicionar_pdfs` e deixe a seleção com ela. A indexação usa os modelos visuais do serviço.

Use `listar_documentos` para identificar o PDF e conferir se o índice está pronto. Quando o nome for ambíguo, peça à pessoa que escolha. Em `ver_indice`, procure um tipo de peça com `ramo` (nome ou ID, inclui os descendentes). Use `pagina_de` e `pagina_ate` para localizar peças que cruzam um intervalo de páginas físicas. Para continuar uma busca, repita os filtros e use o valor de `proxima_peca` em `primeira_peca`.

Peça `detalhes: true` quando a hierarquia ou a confiança da categoria ajudar a escolher páginas. `classe_parcial: true` indica que a classificação parou em um nó com filhos. `confianca_classe` vai de 0 a 1 e estima o tipo da peça a partir da primeira página. Valores nulos indicam informação indisponível. Quando `pecas_sem_hierarquia` for positivo, consulte também a faixa sem o filtro de ramo antes de concluir que uma peça está ausente. Abra as páginas necessárias com `ler_pagina`. Se a classe sugerida for incerta, explore também as páginas vizinhas.

Confira cada valor, data e acontecimento na imagem original antes de responder. Identifique o documento e cite a página física a partir de 1. Para resumos, reúna as páginas que sustentam o pedido, as decisões e o estado do processo. Sinalize fatos que a leitura não permitiu confirmar.

Quando o usuário pedir para conectar a conta, chame `conectar_conta`. Peça que confira o código no portal e autorize o dispositivo antes de abrir a biblioteca.

Ao citar uma imagem lida por `ler_pagina`, use o nome do PDF e a página física. Quando a ferramenta devolver `url`, transforme a referência num link Markdown para essa URL exata, como [Nome do PDF, página física 3](URL retornada). Se a pessoa pedir para abrir a página citada, chame `abrir_biblioteca` com o mesmo `documento_id` e a mesma `pagina`.
