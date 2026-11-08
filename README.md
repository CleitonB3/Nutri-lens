# Nutri Lens

Análise de fotos com a OpenAI. Calorias e nutrientes são estimativas das porções visíveis, não medições ou consultas a uma base nutricional externa.

1. Instale dependências: `npm install`.
2. Copie `.env.example` para `.env.local` e preencha `OPENAI_API_KEY` com uma chave da API com créditos e acesso ao modelo. Nunca use `NEXT_PUBLIC_` nessa chave.
3. Execute `npm run dev`. Reinicie após alterar as variáveis.

Na hospedagem, configure as mesmas variáveis no servidor e faça um novo deploy.

`OPENAI_MODEL` permite trocar o modelo padrão `gpt-5.4` por outro com suporte a imagens e saídas estruturadas. A rota `/api/analyze` recebe formulário multipart com `image` em JPG, PNG ou WEBP, até 10 MB. Os exemplos passam pela mesma análise real, sem fallback fictício.

As chamadas ficam no servidor com `store: false`. Totais são somados a partir dos itens identificados. Erros de chave, créditos, fotos sem alimentos e falhas da API são exibidos na interface.

Verificação: `npx tsc --noEmit` e `npm run build`.
