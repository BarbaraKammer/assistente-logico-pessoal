# Assistente Lógico Pessoal

> Atividade da disciplina Linguagem de Programação e Paradigmas · UNIDAVI · 2026/2

**Aluno(a):** Barbara Cristina Kammer
**Linguagem do sistema:** Node.js (apague a que não usou)

## O que é

Uma base de conhecimento em Prolog (`meus_dados.pl`) com fatos e regras sobre mim e um assistente em linha de comando que consulta essa base pela ponte (`prolog.py` ou `prolog.js`).

## Como executar

Requisitos: SWI-Prolog no PATH e Python 3 **ou** Node.js.

```bash
# testar a ponte
python teste_ponte.py      # ou: node teste_ponte.js

# executar o assistente
python assistente.py       # ou: node assistente.js
```

## Minha base

- Fatos: `eu/1`, `cursa/3`, `compromisso/3`, `sabe/2`, `gosta/2`
- Regras: `ocupado/2`, `livre/2`, `o_que_faco/3`, `pode_ensinar/1`, `dia_cheio/1` e a minha regra abaixo

## Minha regra (R6)

```prolog
% R6 · Maratona: dias em que tenho a noite livre e posso assistir a uma série de que gosto.
maratona(Dia, Serie) :- dia(Dia), livre(Dia, noite), gosta(serie, Serie).
```

**O que ela significa:** 
A regra identifica os dias em que tenho a noite livre para assistir a uma série de que gosto. O subobjetivo dia(Dia) verifica os dias cadastrados, livre(Dia, noite) verifica se estou livre durante a noite e gosta(serie, Serie) verifica quais séries gosto. Quando os três subobjetivos são verdadeiros, a regra retorna o dia e a série.

## Saída real do assistente

```
=== Assistente pessoal de barbara ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
8. Maratona
0. Sair
> 1

== Minhas disciplinas ==
  - lpp (quarta, noite)
  - redes (segunda, noite)
  - mobile (terca, noite)
  - projetos (quinta, noite)
  - seguranca_em_alimentos (sexta, noite)

=== Assistente pessoal de barbara ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
8. Maratona
0. Sair
> 2
Qual dia? (segunda, terca, quarta, quinta, sexta, sabado): segunda

== Agenda de segunda ==
  - noite: redes
  - manha: trabalho
  - tarde: trabalho

=== Assistente pessoal de barbara ===
1. Minhas disciplinas
2. Agenda de um dia
3. Horários livres
4. Estou livre em...?
5. Linguagens que posso ensinar
6. Meus gostos por categoria
7. Dias cheios
8. Maratona
0. Sair
> 8

== Maratona: noites livres ==
  - sabado - dark
  - sabado - the_office
```
