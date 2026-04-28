Aqui está um exemplo de **README.md** bem estruturado para o seu código Java:

---

# 📊 SafeBuild - Monitoramento de Carga em Lajes

Sistema simples em Java para monitoramento de carga em lajes durante processos de construção, auxiliando na tomada de decisão com base em limites de segurança.

## 🚀 Objetivo

O programa simula a leitura de um sensor de carga (kN/m²) e classifica a situação em três níveis:

* 🟢 **VERDE** → Operação normal
* 🟡 **AMARELO (Alerta)** → Atenção necessária
* 🔴 **VERMELHO (Crítico)** → Risco estrutural

## 🧠 Lógica de Funcionamento

O sistema utiliza dois parâmetros principais:

* `cargaProjeto`: carga máxima suportada pela estrutura (15.0 kN/m²)
* `limiteSeguranca`: 80% da carga de projeto

### Regras:

* **Carga < limite de segurança**

  * Status: VERDE
  * Operação normal

* **Carga entre limite de segurança e carga de projeto**

  * Status: AMARELO
  * Redução de atividades e evacuação parcial

* **Carga > carga de projeto**

  * Status: VERMELHO
  * Interrupção imediata

* **Carga > 120% da carga de projeto**

  * Alerta de falha catastrófica iminente

## ⚠️ Observação Importante (Bug no código)

Há um erro nesta linha:

```java
double limiteSeguranca = cargaProjeto = 0.8;
```

### ✔ Correção:

```java
double limiteSeguranca = cargaProjeto * 0.8;
```

Sem essa correção, o valor de `cargaProjeto` é sobrescrito para `0.8`, comprometendo toda a lógica.

## 💻 Como Executar

1. Compile o programa:

```bash
javac MonitoramentoLage.java
```

2. Execute:

```bash
java MonitoramentoLage
```

3. Insira o valor da carga quando solicitado.

## 🧪 Exemplo de Uso

```
Digite a leitura atual do sensor (kN/m²): 12
Status: AMARELO (ALERTA)
Decisão: Reduzir velocidade e concretagem e evacuar pessoal não essencial.
```

## 🛠️ Tecnologias Utilizadas

* Java
* Classe `Scanner` para entrada de dados

## 📌 Possíveis Melhorias

* Validação de entrada do usuário
* Interface gráfica
* Integração com sensores reais (IoT)
* Registro de histórico de leituras
* Alertas automáticos (email/SMS)

## 📄 Licença

Este projeto é livre para uso educacional e pode ser adaptado conforme necessidade.

---
