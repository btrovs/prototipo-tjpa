# Protótipo de redesign – Emissão de certidão no Portal do TJPA

> ⚠️ **Protótipo acadêmico.** Este não é o site oficial do Tribunal de Justiça do Estado do Pará e **não emite certidões**. O PDF gerado é um modelo fictício, sem validade. A certidão oficial deve ser pedida no [portal do TJPA](https://www.tjpa.jus.br/PortalExterno/).

**Acesse o protótipo:** https://btrovs.github.io/prototipo-tjpa/

## Sobre o trabalho

Protótipo navegável feito para o trabalho final da disciplina **Engenharia de Usabilidade (WYD7331)** do curso de Análise e Desenvolvimento de Sistemas da **FACI Wyden** (Belém – PA, 2026).

- **Autora:** Beatriz dos Santos Cardozo
- **Professora:** MSc. Larissa de Paula Serrão Garcia
- **Sistema avaliado:** Portal Externo do TJPA
- **Fluxo crítico:** emissão da Certidão de Antecedentes Criminais
- **Persona:** José Raimundo Ferreira, 50 anos, técnico em eletrotécnica, com uso básico de celular

O trabalho fez uma auditoria ergonômica do fluxo atual, com avaliação heurística (Nielsen), checklist de Bastien e Scapin e inspeção do código-fonte. Depois, redesenhou as três telas do fluxo e as validou com um ensaio piloto.

## O que o protótipo mostra

| Tela | Problema no site atual | Solução no protótipo |
|---|---|---|
| 1. Página inicial | O atalho para certidões é o 6º de 9 e fica abaixo de notícias e banners | Seção "Serviços ao cidadão" logo abaixo da busca, com "Emissão de Certidão" em destaque |
| 2. Tipo de certidão | Outro portal, com aparência diferente e nomes de certidão parecidos | Mesmo cabeçalho, indicador de etapas e explicação de cada tipo de certidão |
| 3. Formulário | Botão "Pesquisar" bloqueado sem explicação e erro genérico de CPF | Botão sempre ativo e mensagens que dizem o que falta e como corrigir |

No fim do fluxo, o protótipo mostra o resultado e gera um **PDF fictício** marcado como "Modelo fictício – sem validade".

## Como testar

Use os dados fictícios da persona. **Não digite seus dados reais.**

| Campo | Valor de teste |
|---|---|
| CPF | `123.456.789-09` |
| Data de nascimento | `03/05/1976` |

1. Clique em **Emissão de Certidão**.
2. Deixe marcada **Antecedentes Criminais** e clique em **Continuar**.
3. O CPF já vem incompleto de propósito. Clique em **Emitir certidão** para ver a mensagem de erro.
4. Complete o CPF com `09` e clique em **Emitir certidão** de novo.
5. Clique em **Baixar certidão (PDF)**.

### Mensagens de erro que dá para ver

| O que digitar | Mensagem |
|---|---|
| CPF com menos de 11 números | "O CPF tem 11 números. Você digitou 9." |
| `123.456.789-85` | "Esse CPF não existe: os dois últimos números não combinam com os outros." |
| CPF certo e outra data, como `03/05/1964` | "Essa data não confere com o cadastro desse CPF." |
| Data impossível, como `31/02/1976` | "Essa data não existe." |
| Outro CPF válido | Pede o CPF de teste do José |

> A versão usada no ensaio piloto conferia apenas a quantidade de números do CPF. A conferência dos dígitos verificadores e da data de nascimento foi incluída depois, nesta versão publicada.

## Acessibilidade

- Barra de acessibilidade com atalhos de teclado (ALT + 1, 2, 3 e 5), aumento e redução do texto (A+ / A−) e alto contraste
- Botões e campos com 48 px de altura, bons para o toque no celular
- Layout em uma coluna no celular
- Resumo de erros no topo, com link que leva direto ao campo
- Verificação de segurança automática, sem quebra-cabeça de imagens
- Página em português (`lang="pt-BR"`), para os leitores de tela pronunciarem corretamente

## Tecnologia

- Um único arquivo `index.html`, com HTML, CSS e JavaScript, sem bibliotecas externas
- O PDF de demonstração é gerado no próprio navegador
- Nenhum dado digitado é enviado ou guardado: tudo roda no seu navegador

Para rodar no computador, baixe o `index.html` e abra no navegador.

Também dá para abrir uma tela direto pelo endereço:

| Endereço | Tela |
|---|---|
| `?tela=home` | Página inicial |
| `?tela=tipo` | Escolha do tipo de certidão |
| `?tela=dados` | Formulário |
| `?tela=erro` | Formulário com a mensagem de erro |
| `?tela=ok` | Certidão emitida |

Exemplo: https://btrovs.github.io/prototipo-tjpa/?tela=erro

## Aviso

O brasão e as cores do Tribunal de Justiça do Estado do Pará foram usados só para fins acadêmicos, para manter a identidade visual no redesign. Eles pertencem ao TJPA. Este projeto não tem ligação com o Tribunal.
