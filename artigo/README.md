# 📘 Projeto Integrador — Guia Oficial de Versionamento (Git)

## 🎯 Regras Gerais

1. ❌ Nunca trabalhar direto na `main`.
2. ✅ Toda alteração deve ser feita em uma **branch de tarefa**.
3. ✅ A `main` só recebe alterações via **Pull Request**.
4. ✅ Pelo menos 1 aprovação é obrigatória para merge.

---

# 🚀 Fluxo Oficial da Equipe

## 1️⃣ Antes de começar qualquer tarefa

```bash
git checkout main
git pull origin main
```

---

## 2️⃣ Criar branch da tarefa

```bash
git checkout -b nome-da-tarefa
```

Exemplos:

```bash
git checkout -b estado-da-arte
git checkout -b metodologia
git checkout -b ajustes-codeowners
```

---

## 3️⃣ Trabalhar normalmente

```bash
git add .
git commit -m "Descrição clara do que foi feito"
```

---

## 4️⃣ Enviar branch

```bash
git push -u origin nome-da-tarefa
```

---

## 5️⃣ Abrir Pull Request

No GitHub:

* Base: `main`
* Compare: `nome-da-tarefa`
* Solicitar review
* Após aprovação → Merge

---

## 6️⃣ Atualizar a `main` após merge

```bash
git checkout main
git pull origin main
```

---

# 🔄 Atualizar sua branch com a main

Sempre antes de abrir PR ou continuar trabalho:

```bash
git checkout main
git pull origin main
git checkout sua-branch
git merge main
git push
```

---

# 🔁 Atualizar a main local

```bash
git checkout main
git pull origin main
```

---

# 🛠️ Se você cometeu direto na main (erro comum)

## Passo 1 — Criar branch com os commits

```bash
git checkout -b fix/commit-feito-na-main
git push -u origin fix/commit-feito-na-main
```

## Passo 2 — Abrir PR

## Passo 3 — Resetar a main local

```bash
git checkout main
git fetch origin
git reset --hard origin/main
```

---

# 🗑️ Arquivos LaTeX que NÃO devem ir para o Git

Adicionar no `.gitignore`:

```
*.aux
*.log
*.out
*.toc
*.synctex.gz
*.fls
*.fdb_latexmk
build/
out/
```

Se já foram adicionados:

```bash
git rm --cached -r -- '*.aux' '*.log' '*.out'
```

---

# ⚠️ Erros Comuns e Soluções

## ❌ Erro: “Changes must be made through a pull request”

Causa: Tentou `push` na `main`.

Solução:
Criar branch → Push → PR.

---

## ❌ PR bloqueado: “Review required”

Causa: Ruleset exige 1 aprovação com Write.

Solução:

* Verificar se colaborador aceitou convite.
* Garantir que ele tem permissão Write.

---

## ❌ “Your branch is ahead of origin/main”

Causa: Commit feito na main local.

Solução:
Criar branch + reset da main.

---

# 🧠 Estrutura Recomendada de Branches

Utilizar nomes baseados na tarefa:

* `estado-da-arte`
* `metodologia`
* `resultados`
* `fix/codeowners`
* `docs/readme`

Nunca usar:

* `main` para desenvolvimento
* Branch com nome pessoal como padrão

---

# 🏆 Regra de Ouro

👉 Trabalhe na branch.
👉 Publique via Pull Request.
👉 Atualize a main depois do merge.

---

Se você quiser, posso:

* Criar uma versão ainda mais profissional (com badges e layout bonito)
* Criar versão enxuta só com comandos essenciais
* Ou adaptar para incluir OpenCV + Flask + LaTeX no mesmo fluxo

Qual você prefere? 🚀
