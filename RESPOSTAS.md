# Respostas do LAB 01

Nome: Miguel Santana
Matricula:26176306
Dupla (M2 em diante):

---

## M2. Quem quebrou o painel
- Hash do commit: 01ef93b
- Autor: Tarcisio Melo <tarcisio.melo@techinova.com.br>
- Data: Mon Jun 15 22:38:00 2026 -0300
- Linha alterada (Antes): return (leitura - 32) * 5 / 9;
- Linha alterada (Depois): return leitura * 9 / 5 + 32;
```

---

## M3 - O segredo vazado

**O que voce esperava ver no `git status` e o que apareceu:**

**Depois do push, alguem que clonar o repositorio ainda consegue ler a chave?
Responda em duas linhas, explicando o motivo:**
Sim, qualquer pessoa que clonar o repositório ainda consegue ler a chave. Isso acontece porque o Git guarda todo o histórico de alterações, permitindo que a chave continue acessível em commits antigos feitos antes da remoção do arquivo.
---

## M4 - Colisao

**O que significavam os marcadores que apareceram dentro do arquivo:**

- `<<<<<<<` :
- `=======` :
- `>>>>>>>` :

**Qual pedaco veio de quem, e qual titulo voces decidiram manter:**

---

## Casa - Incidente na linha 3

**Hash do commit que quebrou o painel:**

**Hash do commit de revert:**

**Por que `git revert` e nao `git reset` neste caso:**
