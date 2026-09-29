# Tempero da Terra 🍲

Site oficial do restaurante **Tempero da Terra** — Sítio Represa, São Paulo/SP.

Comida caseira, porções generosas e delivery. Cardápio completo sincronizado com o
cardápio oficial do FlashMenu, com **carrinho que envia o pedido direto no WhatsApp**.

---

## 🚀 Publicar no GitHub Pages

Este repositório já está pronto para subir. São só três arquivos e a pasta `assets/`.

### 1. Criar o repositório

No GitHub, clique em **New repository** e escolha um nome, por exemplo `tempero-da-terra`.
Pode marcar como **Public**.

> ⚠️ Se você criar o repositório pela interface do GitHub com a opção *"add a README"*,
> desmarque. Se quiser usar este README, crie o repositório **vazio** e suba tudo por cima.

### 2. Subir os arquivos

**Opção A — pelo navegador (mais simples)**
1. Abra o repositório que você acabou de criar
2. Clique em **uploading an existing file**
3. Arraste **todos** os arquivos e a pasta `assets/` para a área de upload
4. Clique em **Commit changes**

> Suba o *conteúdo* das pastas, não as pastas compactadas em .zip.
> O GitHub não aceita .zip e o GitHub Pages não descompacta.

**Opção B — pelo terminal (Git já instalado)**

```bash
cd tempero-da-terra
git init
git add .
git commit -m "Site do Tempero da Terra"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/tempero-da-terra.git
git push -u origin main
```

### 3. Ligar o GitHub Pages

1. No repositório: **Settings** › **Pages**
2. Em *Source*, escolha **Deploy from a branch**
3. Branch: **main** · Pasta: **/ (root)**
4. Clique em **Save**

aguarde 1–2 minutos. O site fica no ar em:

```
https://SEU_USUARIO.github.io/tempero-da-terra/
```

---

## 📁 O que tem nesta pasta

```
index.html      página completa (toda a estrutura do site)
styles.css      design system, responsivo e animações
script.js       cardápio, busca, filtros, carrinho e integração WhatsApp
assets/img/     logo, fotos dos pratos, porções e bebidas
```

Site estático puro — **não tem build, não tem npm, não tem dependências.**
Basta abrir o `index.html` que funciona.

---

## ✏️ Como editar o cardápio

Os produtos ficam no começo do `script.js`, no array `PRODUCTS`:

```js
{ id: "ntC9nKA201sU6J81B1xQ", name: "Costela bovina com mandioca", description: "...", price: 20, cat: "..." }
```

- `name` — nome do prato
- `description` — descrição curta (aparece no card e no cardápio)
- `price` — preço em reais, **sem** o `R$` e **sem** vírgula: `20.50`
- `cat` — o id da categoria (veja o array `CATS` logo acima)

Depois de editar, é só salvar e dar **Ctrl+Shift+R** no navegador pra recarregar sem cache.

### Trocar as fotos

As fotos ficam mapeadas por id de produto no objeto `IMG` (`script.js`):

```js
const IMG = {
  "ntC9nKA201sU6J81B1xQ": "pratos/costela.jpg",
  // ...
};
```

- `pratos/` → fotos de pratos
- `bebidas/` → fotos de bebidas
- Para os itens em que não há foto, o objeto cai numa taça de dose de fallback
  (`bebidas/dose.jpg`). São 8 itens: Carquejio, Cacau, Danny's, Bombeirinho (×2),
  Domeque, Patudo e Emburana — cachaças artesanais sem foto pública.
  **Se você tiver fotos do seu estoque, é só jogar na pasta `bebidas/` e apontar o id aqui.**

Formato recomendado: **JPG, 900 px de largura, qualidade 82.**
A pasta inteira tem ~3,3 MB e carrega rápido em 3G.

---

## 📱 Contato

- **WhatsApp / Telefone:** (11) 95704-6499
- **Endereço:** Av. Doutora Nise da Silveira, 2461 — Sítio Represa, São Paulo/SP, CEP 04894-020
- **Horário:** Seg a Sáb, das 11h15 às 15h (domingo fechado)
- **Pedido mínimo:** R$ 12,00
- **Pagamento:** Pix (CNPJ 39.932.039/0001-82), crédito, débito e dinheiro

O botão **"Aberto agora"** no topo do site calcula sozinho se o restaurante está aberto,
usando o mesmo horário de Seg a Sáb 11h15–15h. Se mudar o horário, edite a condição
`openStatus()` no fim do `script.js`.

---

## 🔗 Mudar o número do WhatsApp

O número está em 2 lugares:

1. `index.html` — todos os links `wa.me/5511957046499`
2. `script.js` — a constante `WA`, lá em cima

Busque e troque `5511957046499` (com `55` e o `9` do celular, sem o `+`).

---

## ⚖️ Créditos das fotos

As imagens de produtos e bebidas foram obtidas de fontes com licença livre ou de domínio público:
**galetos.com.br, Receiteria, Aurora Alimentos, Dolly, Campari Group, Amazon,
Wikimedia Commons e Open Food Facts** (CC BY-SA / domínio público).

Os créditos estão também no rodapé do site.

---

## ✅ Checklist antes de publicar

- [ ] Trocar `SEU_USUARIO` no exemplo de URL acima
- [ ] Conferir se o logo está em `assets/img/logo.jpg`
- [ ] Conferir se o número do WhatsApp está certo
- [ ] Testar o pedido no WhatsApp (adicione um item, abra o carrinho, envie)
- [ ] Abrir no celular pra conferir o layout responsivo
