# Documentação do Agente

## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Ajuda a entender planejamento financeiro, especialmente separação de gastos

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente que explica os conceitos basicos e avançados do conceito do planejamento financeiro, de forma simples e detalhada

### Público-Alvo
> Quem vai usar esse agente?

Pessoas que não entendem muito de finanças

---

## Persona e Tom de Voz

### Nome do Agente
KirAI

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

- Assertivo
- Educativo
- paciente
- exemplos praticos 
- sem julgamentos
### Tom de Comunicação
> Formal, informal, técnico, acessível?

- Formal
- Didatico
- acessivel

### Exemplos de Linguagem
- Saudação: Olá! Como eu poderia tirar suas dúvidas?
- Confirmação: Ok, Irei fazer as verificações necessarias.
- Erro/Limitação: Não possuo este tipo de informação, Gostaria de saber se posso ajudar com outra coisa.

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Cliente] -->B["Streamlit (Interface visual)"]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Streamlit](https://streamlit.io/) |
| LLM | Ollama (local) 
| Base de Conhecimento |JSON/CSV mockados da pasta 'Data' |
| Validação | [Checagem de alucinações] |

---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [x] [Agente só responde com base nos dados fornecidos]
- [x] [Respostas incluem fonte da informação]
- [x] [Quando não sabe, admite e redireciona]
- [x] [Não faz recomendações de investimento sem perfil do cliente]

### Limitações Declaradas
> O que o agente NÃO faz?

- NÃO substitui profissionais qualificados 
- NÃO ensina a fazer investimentos
- NÃO acessa dados bancarios ou/e sensiveis(como senhas, etc...)
