# 🥗 Nutri Lens

Aplicação web que analisa **fotos de refeições** com inteligência artificial e estima as **calorias e os nutrientes** de cada alimento identificado.

> ⚠️ **Aviso:** os valores são **estimativas** feitas a partir das porções visíveis na foto. Não são medições nem consultas a uma base nutricional externa e não substituem a orientação de um nutricionista.

<!-- Adicione aqui um print ou GIF da aplicação:
![Nutri Lens](./docs/screenshot.png)
-->

---

## ✨ Funcionalidades

- Envio de foto da refeição nos formatos **JPG, PNG ou WEBP** (até 10 MB)
- Identificação dos alimentos presentes na imagem
- Estimativa de calorias e nutrientes por item
- **Totais da refeição** somados a partir dos itens identificados
- Imagens de exemplo que passam pela mesma análise real, sem resultados fictícios
- Mensagens de erro claras na interface para chave inválida, falta de créditos, foto sem alimentos e falhas da API

---

## 🛠️ Tecnologias

- [Next.js](https://nextjs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS](https://tailwindcss.com/) e [shadcn/ui](https://ui.shadcn.com/)
- [OpenAI API](https://platform.openai.com/) (análise de imagens com saídas estruturadas)

---

## 🔒 Segurança e privacidade

- As chamadas à OpenAI são feitas **somente no servidor**, então a chave da API nunca é exposta ao navegador
- As requisições usam `store: false`
- Nunca use o prefixo `NEXT_PUBLIC_` na variável da chave da API

---

## 🚀 Como rodar o projeto

### Pré-requisitos

- Node.js instalado
- Uma chave da API da OpenAI com créditos e acesso ao modelo escolhido

### Passo a passo

```bash
# 1. Clone o repositório
git clone https://github.com/CleitonB3/Nutri-lens.git
cd Nutri-lens

# 2. Instale as dependências
npm install

# 3. Crie o arquivo de variáveis de ambiente
cp .env.example .env.local
```

Abra o `.env.local` e preencha a chave:

```env
OPENAI_API_KEY=sua_chave_aqui
# Opcional: troca o modelo padrão (precisa aceitar imagens e saídas estruturadas)
# OPENAI_MODEL=nome-do-modelo
```

```bash
# 4. Rode em modo de desenvolvimento
npm run dev
```

Acesse [http://localhost:3000](http://localhost:3000).

> Reinicie o servidor sempre que alterar as variáveis de ambiente.

### Variáveis de ambiente

| Variável | Obrigatória | Descrição |
|---|---|---|
| `OPENAI_API_KEY` | Sim | Chave da API da OpenAI |
| `OPENAI_MODEL` | Não | Modelo usado na análise (o projeto já tem um padrão) |

---

## 📡 API

### `POST /api/analyze`

Recebe um formulário `multipart/form-data` com o campo `image`.

| Campo | Tipo | Regras |
|---|---|---|
| `image` | arquivo | JPG, PNG ou WEBP, até 10 MB |

Retorna a lista de alimentos identificados com as estimativas nutricionais e os totais da refeição.

---

## ✅ Verificação

```bash
npx tsc --noEmit   # checagem de tipos
npm run build      # build de produção
```

## ☁️ Deploy

Configure as mesmas variáveis de ambiente no servidor de hospedagem e faça um novo deploy.

---

## 👨‍💻 Autor

**Cleiton**

- GitHub: [@CleitonB3](https://github.com/CleitonB3)
- LinkedIn: [SEU-LINKEDIN](https://www.linkedin.com/in/SEU-PERFIL/)
