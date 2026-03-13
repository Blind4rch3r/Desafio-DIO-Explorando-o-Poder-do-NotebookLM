# Desafio DIO – Explorando o Poder do NotebookLM

Este repositório contém o resultado de um desafio educacional proposto pela DIO, cujo objetivo é explorar o uso do **NotebookLM como ferramenta de aprendizagem ativa**, organização do conhecimento e apoio ao estudo de temas introdutórios.

O projeto foi desenvolvido a partir da curadoria de fontes, formulação de perguntas estratégicas e experimentação de variações de prompts, com registro estruturado das respostas e referências.

---

# Pesquisa de Vulnerabilidades e Engenharia Reversa: Um Guia Prático com NotebookLM

## 1. Contexto e Objetivos
Este caderno temático foca nos fundamentos da **segurança de software**, especificamente na **identificação de vulnerabilidades** (como *buffer overflows*) e nas técnicas de **Engenharia Reversa**. 
**Objetivos de Estudo:**
*   Compreender o ciclo de vida de uma vulnerabilidade, do "Day Zero" ao "Zero Day".
*   Diferenciar metodologias de análise estática e dinâmica.
*   Aprender estratégias de mitigação e codificação segura em C/C++.

## 2. Curadoria de Fontes
As seguintes fontes foram selecionadas para compor a base de conhecimento deste projeto:
1.  *The Shellcoder's Handbook 2nd Edition*, Chris Anley et al (Foco em pesquisa de vulnerabilidades).
2.  *The Art of Software Security Assessment*, Mark Dowd et al. (Processos de auditoria e revisão de código).
3.  *Praktyczna inżynieria wsteczna*, Gynvael Coldwind et al. (Técnicas de análise de binários).
4.  *Secure Coding in C and C++*, Robert C. Seacord (Estratégias de mitigação e defesa).
5.  *Exploit!*, Klaus Gebeshuber et al. (Exploração e detecção de falhas de memória).

## 3. Engenharia de Prompts e "Cicatrizes"
Nesta seção, documento o processo de refinamento das consultas para extrair o melhor da IA.

*   **Prompt Inicial (Iniciante):** "O que é engenharia reversa?"
    *   *Resultado:* Uma definição genérica.
*   **Prompt Refinado (Técnico):** "Explique a diferença entre análise estática e dinâmica na engenharia reversa, citando quando usar cada uma."
    *   *Resposta da IA:* A análise estática foca no código em repouso (desmontagem/descompilação), enquanto a dinâmica observa o comportamento em tempo real com depuradores.
*   **Prompt Estratégico (Troubleshooting):** "Quais são os principais 'sinks' (funções perigosas) que devo procurar em um código C para identificar possíveis buffer overflows?"
    *   *Dificuldade Encontrada:* Inicialmente a IA listou apenas `strcpy`. Precisei forçar a busca por variantes como `strcat`, `sprintf` e `vsprintf`, que frequentemente aparecem em cabeçalhos de funções banidas.

## 4. Miniguia de Estudo (Entrega Final)

### Resumo Estruturado: O Ciclo de Análise de Segurança
1.  **Identificação da Superfície de Ataque:** Mapeamento de entradas controladas pelo usuário, como parâmetros de rede, arquivos ou APIs de sistema.
2.  **Análise de Taint (Contaminação):** Rastrear dados de uma "origem" (source) até um "sumidouro" (sink) perigoso.
3.  **Engenharia Reversa:** Uso de ferramentas como Ghidra ou IDA Pro para entender binários sem código-fonte, analisando o fluxo de controle (CFG) e de dados (DFG).
4.  **Mitigação:** Implementação de defesas como **ASLR** (Address Space Layout Randomization) e **DEP** (Data Execution Prevention) para impedir a execução de código arbitrário.

### Glossário de Conceitos Chave
*   **Buffer Overflow:** Condição onde um programa escreve dados além dos limites de um buffer, podendo sobrescrever o endereço de retorno (EIP).
*   **Fuzzing:** Teste automatizado que injeta dados inválidos ou aleatórios para causar falhas e encontrar bugs.
*   **Shellcode:** Conjunto de instruções (geralmente em assembly) injetado para executar comandos após a exploração bem-sucedida de uma vulnerabilidade.
*   **Integridade:** Garantia de que os dados não foram alterados de forma não autorizada.

### Prompts Reutilizáveis para Revisão
*   "Resuma as principais técnicas de proteção contra estouro de pilha mencionadas no livro *Secure Coding in C and C++*."
*   "Explique como o mecanismo de *backtracking* no Metasm auxilia na descoberta de destinos de saltos (`jmp`) em código ofuscado."
*   "Dada uma função que utiliza `memcpy`, descreva o processo de auditoria necessário para garantir que não haja overflow."

---

## Considerações Finais

Este repositório representa um **exercício prático de uso consciente da IA como apoio ao aprendizado**, reforçando a importância da curadoria de fontes, da formulação de boas perguntas e da organização do conhecimento para estudos futuros.
