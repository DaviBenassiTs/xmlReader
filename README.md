# Leitor de XML — Comprovantes SRI

Ferramenta web (HTML/CSS/JS puro, sem dependências ou build) para visualizar de forma legível arquivos XML de comprovantes eletrônicos do SRI (Serviço de Rendas Internas do Equador): faturas, notas de crédito/débito, guias de remissão, comprovantes de retenção e respostas de autorização.

## Uso

Basta abrir o arquivo [leitor-xml-sri.html](leitor-xml-sri.html) diretamente no navegador — não é necessário servidor nem instalação.

1. Arraste um ou mais arquivos `.xml` para a área de upload (ou clique para selecionar).
2. O conteúdo é interpretado e exibido em cartões organizados: dados do emissor, detalhes do documento, impostos, pagamentos, assinatura digital, mensagens de autorização etc.
3. Alterne entre a aba **Resumo** (visualização formatada) e **XML Bruto** (arquivo original com indentação).

Um exemplo de fatura está disponível em [exemplo-fatura.xml](exemplo-fatura.xml) para testes rápidos.

## Funcionalidades

- **Leitura de múltiplos formatos**: identifica automaticamente o tipo de documento (fatura, nota de crédito, nota de débito, guia de remissão, comprovante de retenção) e respostas de autorização do SRI, incluindo o comprovante XML embutido dentro da resposta.
- **Tradução de rótulos**: campos técnicos do XML (em espanhol) são exibidos com rótulos em português.
- **Formatação de valores**: datas, valores monetários e códigos (ambiente, tipo de emissão, etc.) são formatados para leitura humana.
- **Edição inline**: modo de edição permite alterar valores diretamente na interface, com pré-visualização do XML resultante.
- **Exportação**: baixa o XML (original ou editado) como arquivo `.xml`.
- **Múltiplos arquivos**: gerencia vários arquivos carregados simultaneamente, com lista lateral para alternar entre eles.
- **Cache local**: os arquivos carregados ficam salvos no `localStorage` do navegador e são restaurados automaticamente ao reabrir a página (pode ser limpo pelo botão "Limpar cache local").
- **Copiar com um clique**: campos como RUC e chave de acesso podem ser copiados para a área de transferência ao clicar.

## Estrutura do projeto

- [leitor-xml-sri.html](leitor-xml-sri.html) — aplicação completa (HTML, CSS e JavaScript em um único arquivo).
- [exemplo-fatura.xml](exemplo-fatura.xml) — arquivo XML de exemplo para testes.

## Tecnologia

Página estática sem frameworks ou dependências externas — usa apenas APIs nativas do navegador (`DOMParser`, `XMLSerializer`, `localStorage`, Clipboard API).
