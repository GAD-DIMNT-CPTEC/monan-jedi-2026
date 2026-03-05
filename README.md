# MONAN-JEDI 2026

**Planejamento Técnico para a Implementação Estruturada do MONAN+JEDI (2026-2027)**  
CPTEC / DIMNT / Grupo de Assimilação de Dados (GAD)

---

## 1. Propósito do Repositório

Este repositório constitui o ambiente de referência técnica para:

1. Estruturação institucional do MPAS+JEDI
2. Transição controlada MPAS para o MONAN no contexto do JEDI
3. Consolidação do sistema de assimilação do CPTEC baseado no JEDI
4. Garantia de reprodutibilidade computacional
5. Execução paralela coordenada das frentes de trabalho

* 👉 Repositório oficial: https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026

> [!Note]
> Este documento não é apenas um repositório de código: é o instrumento formal de organização técnica que garantirá a rastreabilidade e validação institucional do projeto.

---

## 2. Execução Técnica

A execução técnica é controlada exclusivamente via GitHub Issues + GitHub Projects associados a este repositório ([monan-jedi-2026](https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026)):

- O [board](https://github.com/orgs/GAD-DIMNT-CPTEC/projects/4) é o único instrumento oficial de acompanhamento
- O estado do board deve refletir a realidade técnica
- Não são utilizados controles paralelos

---

## 3. Diretrizes

O projeto é pautado pelas seguintes diretrizes:

### Execução Paralela Coordenada

Nenhuma frente de trabalho pode permanecer inativa por indefinição estrutural.

### Marcos Verificáveis

Nenhuma [milestone](https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026/milestones) é considerada concluída sem evidência documentada.

### Reprodutibilidade Obrigatória

Build, ambiente e execução devem ser reproduzíveis em instalação limpa.

### Dependências Declaradas e Não Circulares

Toda [issue](https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026/issues) deve declarar:

- `Depends on`: a issue atual depende da conclusão de uma issue anterior
- `Related to`: a issue atual está relacionada a uma outra issue
- `Blocks`: o início do desenvolvimento de uma outra issue depende da conclusão da issue atual

Dependências circulares não são permitidas (por exemplo, #22 depende de #22).

### Governança Formal 

Toda issue deve conter:

- Milestone associada: `M1`, `M2`, `M3` etc (vide [milestones](https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026/milestones) para mais informações);
- Labels obrigatórias: `area` / `phase` / `type` (vide [labels](https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026/blob/main/GOVERNANCA_E_LABELS.md#2-labels) para mais informações);
- Responsável formal: membro do grupo que será o responsável por desenvolver e acompanhar o desenvolvimento da issue.

---

## 4. Fluxo Operacional das Issues

`Todo` → `Pronto para Execução` → `Em Execução` → `Em Revisão Técnica` → `Em Validação` → `Concluído`

Uma issue somente poderá ser encerrada quando:

- O código estiver versionado
- Os logs estiverem anexados
- Houver evidência de execução válida
- O critério objetivo for atendido
- A revisão técnica for realizada

---

## 5. Milestones Oficiais 2026–2027

Início formal: **02/03/2026**

### M1 - Consolidação Institucional de Ambiente e Governança de Build  
* Período: 02/03/2026 → 30/04/2026  

### M2 - Baseline Determinístico MPAS Oficial  
* Período: 04/05/2026 → 29/05/2026  

### M3 - Integração 3DVar FGAT  
* Período: 01/06/2026 → 31/07/2026  

### M4 - Avaliação Formal  
* Período: 03/08/2026 → 28/08/2026  

### M5 - Transição MPAS → MONAN  
* Período: 31/08/2026 → 30/10/2026  

### M6 - Consolidação MONAN-JEDI  
* Período: 02/11/2026 → 31/12/2026  

### M7 - Hybrid 3DVar (Prova de Conceito)  
* Período: 04/01/2027 → 26/02/2027  

* 👉 Milestones do projeto no GitHub: https://github.com/GAD-DIMNT-CPTEC/monan-jedi-2026/milestones

---

## 6. Estrutura Organizacional

O projeto está dividido em frentes de trabalho paralelas:

* Infraestrutura e Spack
* MPAS / MONAN
* Observações (IODA / UFO)
* Núcleo Variacional (JEDI)
* Avaliação e Métricas
* Documentação e Reprodutibilidade

Cada frente de trabalho possui:

* Responsável formal
* Colaboradores definidos
* Entregáveis objetivos

---

## 7. Cronograma Executivo Estratégico (Alinhado às Issues Reais)

```mermaid
gantt
  title MONAN-JEDI 2026/2027 – Execução Institucional
  dateFormat  YYYY-MM-DD
  axisFormat  %d/%m

  section Milestones
  M1 – Ambiente & Governança                        :mil_m1, 2026-03-02, 2026-04-30
  M2 – Baseline MPAS Oficial                        :mil_m2, 2026-05-04, 2026-05-29
  M3 – 3DVar FGAT MPAS-JEDI                         :mil_m3, 2026-06-01, 2026-07-31
  M4 – Avaliação Formal                             :mil_m4, 2026-08-03, 2026-08-28
  M5 – Transição MPAS → MONAN                       :mil_m5, 2026-08-31, 2026-10-30
  M6 – Consolidação MONAN-JEDI                      :mil_m6, 2026-11-02, 2026-12-31
  M7 – Hybrid 3DVar (PoC)                           :mil_m7, 2027-01-04, 2027-02-26

  section Infraestrutura
  Freeze Spack / spack.lock (M1)                    :crit, 2026-03-02, 2026-04-30
  Performance e I/O tuning                          :active, 2026-05-04, 2026-12-31

  section MPAS
  Baseline determinístico 7 dias (M2)               :crit, 2026-05-04, 2026-05-29
  Background estável para DA (M3)                   :active, 2026-06-01, 2026-07-31

  section Observações
  Estrutura Base IODA (M1)                          :active, 2026-03-02, 2026-04-30
  Integração IODA no ciclo baseline (M2)            :crit, 2026-05-04, 2026-05-29
  Relatórios por ciclo assimilado (M3/M4)           :active, 2026-06-01, 2026-08-28

  section JEDI
  1º ciclo 3DVar FGAT (M3)                          :crit, 2026-06-01, 2026-07-31
  Auditoria custo/convergência (M4)                 :active, 2026-08-03, 2026-08-28

  section Avaliação
  Módulo O–B/O–A estrutura base – M1)              :active, 2026-03-15, 2026-04-30
  Validação métricas no baseline (M2)               :crit, 2026-05-04, 2026-05-29
  Auditoria estatística formal (M4)                 :crit, 2026-08-03, 2026-08-28

  section MONAN
  Portabilidade MONAN (M5)                          :crit, 2026-08-31, 2026-10-30
  Estabilidade prolongada MONAN-JEDI (M6)           :active, 2026-11-02, 2026-12-31
````

---

## 8. Sanity Checks Automatizados

Requisitos:

* `gh` CLI autenticado (utilitário de linha de comando para gerenciamento do GitHub; mais informações em [link](https://cli.github.com/));
* `jq` instalado (utilitário em linha de comando para processar arquivos JSON; mais informações em [link](https://github.com/jqlang/jq)).

## 8.1 Verificação Estrutural de Issues

Script recomendado:

```
tools/gh_sanity_check_issues.sh
```

Como executar:

```bash
./tools/gh_sanity_check_issues.sh GAD-DIMNT-CPTEC/monan-jedi-2026
```

### O que é verificado:

* Toda issue tem milestone
* Toda issue tem assignee
* Toda issue tem:
  * 1 label area:*
  * 1 label phase:M*
  * 1 label type:*  
* Não existe auto-dependência (por exemplo: #22 depende de #22)
* Referências (#n) apontam para issues existentes

Se falhar, o avanço do milestone deve ser bloqueado.

---

## 8.2 Geração de Matriz de Dependências

Script recomendado:

```
tools/gh_report_issues_matrix.sh
```

Como executar:

```bash
./tools/gh_report_issues_matrix.sh GAD-DIMNT-CPTEC/monan-jedi-2026 > docs/issues_matrix.md
```

Permite auditoria rápida de:

* Paralelismo real
* Gargalos
* Dependências mal definidas

---

## 9. Documentação Estrutural

* `docs/milestones/`
* `docs/relatorios/`
* `GOVERNANCA_E_LABELS.md`: leitura obrigatória antes de iniciar execução
* `README_EXECUCAO_TECNICA.md`: leitura obrigatória antes de iniciar execução
* `spack/`
* `tools/`

---

## 10. Regra Institucional Crítica

> [!IMPORTANT]
> Nenhuma frente técnica pode permanecer bloqueada por erro estrutural de organização. Caso ocorra, a inconsistência deve ser corrigida imediatamente como falha estrutural de governança.

---

## 11. Status Atual

Data base: 02/03/2026
Projeto em início formal do Milestone `M1`.
