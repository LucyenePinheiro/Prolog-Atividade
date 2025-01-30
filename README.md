# README - Sistema de Diagnóstico de Veículos Autônomos

## Descrição
Este sistema é um modelo de diagnóstico de falhas para veículos autônomos, implementado em Prolog, usando predicados dinâmicos para monitorar variáveis como o estado da bateria, temperatura do motor, nível de óleo, entre outros. Com base nesses dados, o sistema sugere possíveis causas de falhas e recomendações de ação corretiva.

## Funcionalidades

### 1. **Predicados Dinâmicos**
O sistema utiliza predicados dinâmicos para armazenar e atualizar informações sobre o estado do veículo:
- `bateria/1`: Estado da bateria (voltagem).
- `temperatura_motor/1`: Temperatura do motor.
- `nivel_oleo/1`: Nível de óleo no motor.
- `sensor_oxigenio/1`: Leitura do sensor de oxigênio.
- `luz_check_engine/0`, `luz_bateria/0`: Indicadores de falhas no veículo.
- `falha_ignicao/0`, `barulho_incomum/0`, `rotacao_alta/0`: Sintomas adicionais.

### 2. **Diagnóstico de Falhas**
O sistema realiza o diagnóstico de falhas a partir de regras predefinidas que associam sintomas a possíveis causas. Algumas falhas diagnosticadas incluem:
- **Bateria Fraca**: Diagnóstico com base na voltagem da bateria e luz de falha.
- **Alternador Defeituoso**: Identificado quando a luz da bateria acende, mas a bateria está em boas condições.
- **Problemas no Sistema de Arrefecimento**: Indicados por temperatura do motor acima de 100°C e luz de check engine acesa.
- **Baixo Nível de Óleo**: Quando o nível de óleo está abaixo de um valor mínimo aceitável.

### 3. **Recomendações de Ação**
Para cada causa diagnosticada, o sistema fornece uma recomendação de manutenção ou reparo. Exemplos incluem:
- **Bateria Fraca**: "Recarregar ou substituir a bateria."
- **Alternador Defeituoso**: "Verificar correia do alternador ou trocar alternador."
- **Problemas no Sistema de Arrefecimento**: "Checar radiador, bomba de água, ventoinha e fluido de arrefecimento."

### 4. **Justificativas para Diagnóstico**
O sistema também oferece justificativas detalhadas para cada diagnóstico, explicando os motivos que levam à conclusão de um problema específico. Por exemplo:
- **Bateria Fraca**: "O sistema comparou a voltagem da bateria com o limite mínimo e concluiu que a bateria não está fornecendo voltagem adequada."

### 5. **Casos de Teste**
O sistema inclui diversos cenários de teste para validar os diagnósticos. Exemplos de casos de teste:
- **Partida Inconsistente**: Diagnóstico de bateria fraca com luz de bateria acesa.
- **Superaquecimento no Motor**: Diagnóstico de problemas no sistema de arrefecimento.
- **Motor Engasgado em Altas Rotações**: Diagnóstico de sensor de oxigênio defeituoso.
- **Ruídos no Motor ao Acelerar**: Diagnóstico de problemas mecânicos internos ou na transmissão.

### 6. **Predicado Principal**
O predicado `diagnosticar/0` executa o diagnóstico geral, identificando todas as falhas possíveis e fornecendo recomendações e justificativas detalhadas para cada uma.

## Instruções para Execução

1. **Carregamento do Sistema**: Ao inicializar, o sistema executa automaticamente os casos de teste definidos no predicado `main/0`.
2. **Testes**: O sistema executa diferentes cenários de falhas no veículo, como partida inconsistente, superaquecimento no motor, e problemas no sensor de oxigênio.
3. **Diagnóstico**: Após a execução, o sistema exibirá as falhas detectadas, recomendações de ação e justificativas detalhadas.

## Exemplo de Execução

```prolog
=== Executando vários casos de teste ===

=== Caso de Teste 1: Partida Inconsistente ===

Possíveis problemas diagnosticados:

 -> Para bateria_fraca, recomenda-se:
    Recarregar ou substituir a bateria

Justificativa: O sistema comparou 11,8V com o limite mínimo de 12V e concluiu que a bateria não está fornecendo voltagem adequada.

=== Caso de Teste 2: Superaquecimento no Motor ===

Possíveis problemas diagnosticados:

 -> Para sistema_arrefecimento, recomenda-se:
    Checar radiador, bomba de água, ventoinha e fluido de arrefecimento

Justificativa: A temperatura do motor está acima de 100C, e a luz de check engine está acesa. Isso indica um problema no sistema de arrefecimento.
```

## Conclusão
Este sistema oferece um diagnóstico automático e eficaz para falhas em veículos autônomos, utilizando dados de sensores e sintomas para identificar problemas potenciais e fornecer recomendações de manutenção. 