# 🚀 Fluxo Oficial da Equipe (Git)

1. **Nunca trabalhar direto na `main`.**
2. Atualizar antes de começar:

   ```bash
   git checkout main && git pull origin main
   ```
3. Criar branch com nome da tarefa:

   ```bash
   git checkout -b nome-da-tarefa
   ```
4. Fazer alterações apenas nos arquivos da sua seção.
5. Commitar com mensagem clara:

   ```bash
   git add . && git commit -m "Descrição objetiva"
   ```
6. Enviar a branch:

   ```bash
   git push -u origin nome-da-tarefa
   ```
7. Abrir **Pull Request** para `main`.
8. Solicitar review de pelo menos 1 colaborador.
9. Após aprovação, fazer **Merge via PR** (nunca via push direto).
10. Atualizar a `main` local após merge:

```bash
git checkout main && git pull origin main
```

---

Se quiser, posso montar também uma versão ainda mais curta (tipo “Regra de Ouro em 5 linhas”) para colocar como destaque no topo do README.
