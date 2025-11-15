# iFlow de Conversão XML → JSON usando SAP Integration Suite

Este projeto demonstra um *Integration Flow (iFlow)* criado no **SAP Integration Suite (CPI)** para realizar a transformação de um payload **XML → JSON**, utilizando **Message Mapping**, **Content Modifiers** e o **XML to JSON Converter** como principais steps.

O objetivo é mostrar de forma clara e prática como aplicar um fluxo simples, mas completo, envolvendo transformação de dados, rastreabilidade em runtime e teste via Postman.

---

## 🧩 Arquitetura do Fluxo (iFlow)

A estrutura geral do iFlow está representada no print abaixo:

![iFlow](prints/iflow.png)

**Componentes principais usados no projeto:**
- **Sender / Receiver HTTP**
- **Message Mapping** (transformação XML → XML)
- **Content Modifier – BEFORE**
- **XML to JSON Converter**
- **Content Modifier – AFTER**

---

## 🔄 1. Message Mapping (XML → XML)

O Message Mapping foi utilizado para transformar a estrutura de entrada XML em um formato mais adequado antes da conversão final para JSON.

### 📷 Print do Message Mapping
![Message Mapping](prints/message-mapping.png)

---

## 🏷 2. Content Modifiers (Before & After)

Foram adicionados dois Content Modifiers para fins de rastreabilidade:

- **BEFORE** → Armazena o conteúdo antes do XML to JSON Converter  
- **AFTER** → Armazena o conteúdo após a conversão

### 📷 BEFORE
![Content Modifier Before](prints/before.png)

### 📷 AFTER
![Content Modifier After](prints/after.png)

---

## 🔁 3. XML to JSON Converter

Este step é responsável por converter automaticamente o payload XML transformado em JSON.

### 📷 Print do Converter
![XML to JSON Converter](prints/xml-to-json.png)

---

## 🧪 Teste via Postman

O teste foi realizado através de uma requisição **POST** para o endpoint exposto pelo iFlow no SAP Integration Suite.

O print abaixo mostra:
- O endpoint usado
- O payload XML enviado
- O JSON retornado após o processamento

### 📷 Requisição e resposta
![Postman](prints/postman-request-response.png)

---

## 📝 Payload de Exemplo

### 🔹 **XML enviado no Postman**
```xml
<root>
    <value>123</value>
</root>
🔹 JSON retornado
json
Copiar código
{
    "root": {
        "value": 123
    }
}
(O conteúdo exato pode variar de acordo com o Message Mapping configurado.)

📦 Objetivo Educacional
Este projeto faz parte da minha jornada de estudos no ecossistema SAP Integration Suite, com foco em:

Entender o fluxo completo de transformação XML → JSON

Praticar o uso de Message Mapping

Aplicar o XML to JSON Converter

Consolidar boas práticas de organização de iFlows

Aprender a documentar e publicar integrações no GitHub

🔗 Tecnologias Utilizadas
SAP Integration Suite (CPI)

Message Mapping

XML to JSON Converter

Content Modifier

Postman

📄 Estrutura do Repositório
pgsql
Copiar código
/
├── README.md
└── prints/
    ├── after.png
    ├── before.png
    ├── iflow.png
    ├── message-mapping.png
    ├── postman-request-response.png
    └── xml-to-json.png
🚀 Como Executar (Caso queira replicar)
Importe o iFlow no SAP Integration Suite.

Configure o endpoint HTTPS.

Defina a estrutura do Message Mapping.

Adicione os Content Modifiers (Before e After).

Execute um POST via Postman com qualquer XML válido.

Verifique o JSON retornado.

📚 Autor
Gustavo Flávio
Estudante e desenvolvedor em formação no ecossistema SAP Integration Suite, focado em integrações, automações e boas práticas de documentação técnica.