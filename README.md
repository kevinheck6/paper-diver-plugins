# Paper Diver

Pesquise seus autos no Codex ou no Claude Code e confira as respostas pelas páginas físicas dos PDFs.

O piloto funciona no Windows x64 e requer uma conta convidada. Consulte os passos de instalação e conexão no [portal do Paper Diver](https://paper-diver-staging.kevinheck941972.workers.dev/#como-funciona).

| Assistente | Adicionar o catálogo | Instalar |
| --- | --- | --- |
| Codex | `codex plugin marketplace add kevinheck6/paper-diver-plugins` | `codex plugin add paper-diver@paper-diver` |
| Claude Code | `/plugin marketplace add kevinheck6/paper-diver-plugins` | `/plugin install paper-diver@paper-diver` |

Em uma nova conversa, peça **Conectar minha conta do Paper Diver** e confirme o código no portal. Depois peça **Adicionar um PDF à minha biblioteca**. Quando o documento estiver pronto, peça uma resposta com a página física.

O plugin envia os PDFs escolhidos ao armazenamento do seu escritório. Os modelos de indexação rodam no serviço Paper Diver. Os dois assistentes podem usar a mesma conta protegida pelo perfil Windows. Você pode revogar o dispositivo no portal.
