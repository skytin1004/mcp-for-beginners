<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "788eb17750e970a0bc3b5e7f2e99975b",
  "translation_date": "2025-05-18T15:09:52+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "pa"
}
-->
# 📖 MCP ਕੋਰ ਸੰਕਲਪ: AI ਇੰਟਿਗ੍ਰੇਸ਼ਨ ਲਈ ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ 'ਚ ਮਾਹਰਤਾ

ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਇੱਕ ਸ਼ਕਤੀਸ਼ালী, ਮਿਆਰੀ ਫਰੇਮਵਰਕ ਹੈ ਜੋ ਵੱਡੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ (LLMs) ਅਤੇ ਬਾਹਰੀ ਟੂਲ, ਐਪਲੀਕੇਸ਼ਨਾਂ ਅਤੇ ਡਾਟਾ ਸਰੋਤਾਂ ਵਿਚਕਾਰ ਸੰਚਾਰ ਨੂੰ ਸੁਧਾਰਦਾ ਹੈ। ਇਹ SEO-ਅਨੁਕੂਲ ਗਾਈਡ ਤੁਹਾਨੂੰ MCP ਦੇ ਮੁੱਖ ਸੰਕਲਪਾਂ ਨਾਲ ਜਾਣੂ ਕਰਵਾਏਗੀ, ਜਿਸ ਨਾਲ ਤੁਹਾਨੂੰ ਇਸ ਦੀ ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ, ਜਰੂਰੀ ਹਿੱਸੇ, ਸੰਚਾਰ ਮਕੈਨਿਕਸ ਅਤੇ ਲਾਗੂ ਕਰਨ ਦੀਆਂ ਵਧੀਆ ਪ੍ਰਥਾਵਾਂ ਦੀ ਸਮਝ ਹੋਵੇਗੀ।

## ਓਵਰਵਿਊ

ਇਸ ਪਾਠ ਵਿੱਚ ਅਸੀਂ ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਪਰਿਵਾਰ ਦੀ ਮੂਲ ਆਰਕੀਟੈਕਚਰ ਅਤੇ ਹਿੱਸਿਆਂ ਦੀ ਖੋਜ ਕਰਾਂਗੇ। ਤੁਸੀਂ MCP ਦੇ ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ, ਮੁੱਖ ਹਿੱਸਿਆਂ ਅਤੇ ਸੰਚਾਰ ਮਕੈਨਿਕਸ ਬਾਰੇ ਸਿੱਖੋਗੇ ਜੋ MCP ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਚਲਾਉਂਦੇ ਹਨ।

## 👩‍🎓 ਮੁੱਖ ਸਿੱਖਣ ਦੇ ਲਕੜੇ

ਇਸ ਪਾਠ ਦੇ ਅੰਤ ਤੱਕ, ਤੁਸੀਂ:

- MCP ਕਲਾਇੰਟ-ਸਰਵਰ ਆਰਕੀਟੈਕਚਰ ਨੂੰ ਸਮਝੋਗੇ।
- Hosts, Clients ਅਤੇ Servers ਦੇ ਭੂਮਿਕਾਵਾਂ ਅਤੇ ਜ਼ਿੰਮੇਵਾਰੀਆਂ ਦੀ ਪਛਾਣ ਕਰੋਗੇ।
- MCP ਨੂੰ ਇੱਕ ਲਚਕੀਲਾ ਇੰਟਿਗ੍ਰੇਸ਼ਨ ਲੇਅਰ ਬਣਾਉਣ ਵਾਲੀਆਂ ਮੁੱਖ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦਾ ਵਿਸ਼ਲੇਸ਼ਣ ਕਰੋਗੇ।
- MCP ਪਰਿਵਾਰ ਵਿੱਚ ਜਾਣਕਾਰੀ ਦੇ ਪ੍ਰਵਾਹ ਨੂੰ ਸਮਝੋਗੇ।
- .NET, ਜਾਵਾ, ਪਾਇਥਨ ਅਤੇ ਜਾਵਾਸਕ੍ਰਿਪਟ ਵਿੱਚ ਕੋਡ ਉਦਾਹਰਨਾਂ ਰਾਹੀਂ ਪ੍ਰਾਇਗਮਿਕ ਜਾਣਕਾਰੀ ਪ੍ਰਾਪਤ ਕਰੋਗੇ।

## 🔎 MCP ਆਰਕੀਟੈਕਚਰ: ਇੱਕ ਡੂੰਘੀ ਨਜ਼ਰ

MCP ਪਰਿਵਾਰ ਇੱਕ ਕਲਾਇੰਟ-ਸਰਵਰ ਮਾਡਲ 'ਤੇ ਬਣਿਆ ਹੈ। ਇਹ ਮਾਡੂਲਰ ਢਾਂਚਾ AI ਐਪਲੀਕੇਸ਼ਨਾਂ ਨੂੰ ਟੂਲ, ਡਾਟਾਬੇਸ, API ਅਤੇ ਸੰਦਰਭਿਕ ਸਰੋਤਾਂ ਨਾਲ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਢੰਗ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ। ਆਓ ਇਸ ਆਰਕੀਟੈਕਚਰ ਨੂੰ ਇਸਦੇ ਮੁੱਖ ਹਿੱਸਿਆਂ ਵਿੱਚ ਵੰਡ ਕੇ ਵੇਖੀਏ।

### 1. Hosts

ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਵਿੱਚ, Hosts ਉਹ ਮੁੱਖ ਇੰਟਰਫੇਸ ਹੁੰਦੇ ਹਨ ਜਿਨ੍ਹਾਂ ਰਾਹੀਂ ਯੂਜ਼ਰ ਪ੍ਰੋਟੋਕੋਲ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦੇ ਹਨ। Hosts ਉਹ ਐਪਲੀਕੇਸ਼ਨ ਜਾਂ ਵਾਤਾਵਰਨ ਹੁੰਦੇ ਹਨ ਜੋ MCP ਸਰਵਰਾਂ ਨਾਲ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ ਤਾਂ ਜੋ ਡਾਟਾ, ਟੂਲ ਅਤੇ ਪ੍ਰੌਂਪਟ ਤੱਕ ਪਹੁੰਚ ਪ੍ਰਾਪਤ ਕਰ ਸਕਣ। Hosts ਦੇ ਉਦਾਹਰਨ ਹਨ: Visual Studio Code ਵਰਗੇ ਇੰਟੀਗਰੇਟਿਡ ਡਿਵੈਲਪਮੈਂਟ ਇੰਵਾਇਰਨਮੈਂਟ (IDEs), Claude Desktop ਵਰਗੇ AI ਟੂਲ, ਜਾਂ ਕਿਸੇ ਵਿਸ਼ੇਸ਼ ਕੰਮ ਲਈ ਬਣਾਏ ਗਏ ਕਸਟਮ ਏਜੰਟ।

**Hosts** LLM ਐਪਲੀਕੇਸ਼ਨਾਂ ਹਨ ਜੋ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ। ਇਹ:

- AI ਮਾਡਲਾਂ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਕੇ ਜਵਾਬ ਬਣਾਉਂਦੇ ਹਨ।
- MCP ਸਰਵਰਾਂ ਨਾਲ ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦੇ ਹਨ।
- ਗੱਲਬਾਤ ਦਾ ਪ੍ਰਵਾਹ ਅਤੇ ਯੂਜ਼ਰ ਇੰਟਰਫੇਸ ਸੰਭਾਲਦੇ ਹਨ।
- ਅਨੁਮਤੀਆਂ ਅਤੇ ਸੁਰੱਖਿਆ ਸੀਮਾਵਾਂ ਨੂੰ ਨਿਯੰਤਰਿਤ ਕਰਦੇ ਹਨ।
- ਡਾਟਾ ਸਾਂਝਾ ਕਰਨ ਅਤੇ ਟੂਲ ਚਲਾਉਣ ਲਈ ਯੂਜ਼ਰ ਦੀ ਸਹਿਮਤੀ ਸੰਭਾਲਦੇ ਹਨ।

### 2. Clients

Clients MCP ਸਰਵਰਾਂ ਅਤੇ Hosts ਵਿਚਕਾਰ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਸਹੂਲਤ ਦੇਣ ਵਾਲੇ ਜਰੂਰੀ ਹਿੱਸੇ ਹਨ। Clients ਮੱਧਸਥ ਹਨ ਜੋ Hosts ਨੂੰ MCP ਸਰਵਰਾਂ ਵੱਲੋਂ ਦਿੱਤੀਆਂ ਗਈਆਂ ਖੂਬੀਆਂ ਤੱਕ ਪਹੁੰਚ ਅਤੇ ਉਪਯੋਗ ਕਰਨ ਦੇ ਯੋਗ ਬਣਾਉਂਦੇ ਹਨ। ਇਹ MCP ਆਰਕੀਟੈਕਚਰ ਵਿੱਚ ਸਹੀ ਸੰਚਾਰ ਅਤੇ ਡਾਟਾ ਦੇ ਅਦਾਨ-ਪ੍ਰਦਾਨ ਨੂੰ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ।

**Clients** Host ਐਪਲੀਕੇਸ਼ਨ ਦੇ ਅੰਦਰ ਕਨੈਕਟਰ ਹੁੰਦੇ ਹਨ। ਇਹ:

- ਸਰਵਰਾਂ ਨੂੰ ਪ੍ਰੌਂਪਟ/ਹਦਾਇਤਾਂ ਨਾਲ ਬੇਨਤੀਆਂ ਭੇਜਦੇ ਹਨ।
- ਸਰਵਰਾਂ ਨਾਲ ਖੂਬੀਆਂ ਦੀ ਮੋਲ-ਤੋਲ ਕਰਦੇ ਹਨ।
- ਮਾਡਲ ਤੋਂ ਟੂਲ ਚਲਾਉਣ ਦੀਆਂ ਬੇਨਤੀਆਂ ਸੰਭਾਲਦੇ ਹਨ।
- ਯੂਜ਼ਰਾਂ ਨੂੰ ਜਵਾਬ ਪ੍ਰੋਸੈਸ ਅਤੇ ਦਿਖਾਉਂਦੇ ਹਨ।

### 3. Servers

Servers MCP clients ਵੱਲੋਂ ਆਉਣ ਵਾਲੀਆਂ ਬੇਨਤੀਆਂ ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ ਅਤੇ ਉਚਿਤ ਜਵਾਬ ਦਿੰਦੇ ਹਨ। ਇਹ ਡਾਟਾ ਪ੍ਰਾਪਤੀ, ਟੂਲ ਚਲਾਉਣਾ ਅਤੇ ਪ੍ਰੌਂਪਟ ਬਣਾਉਣ ਵਰਗੀਆਂ ਕਾਰਵਾਈਆਂ ਨੂੰ ਸੰਭਾਲਦੇ ਹਨ। Servers ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ ਕਿ clients ਅਤੇ Hosts ਵਿਚਕਾਰ ਸੰਚਾਰ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਅਤੇ ਭਰੋਸੇਯੋਗ ਹੈ, ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਪ੍ਰਕਿਰਿਆ ਦੀ ਅਖੰਡਤਾ ਬਣਾਈ ਰੱਖਦੇ ਹਨ।

**Servers** ਉਹ ਸਰਵਿਸز ਹਨ ਜੋ ਸੰਦਰਭ ਅਤੇ ਖੂਬੀਆਂ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ। ਇਹ:

- ਉਪਲਬਧ ਫੀਚਰਾਂ (ਸਰੋਤ, ਪ੍ਰੌਂਪਟ, ਟੂਲ) ਨੂੰ ਰਜਿਸਟਰ ਕਰਦੇ ਹਨ।
- ਕਲਾਇੰਟ ਵੱਲੋਂ ਟੂਲ ਕਾਲਾਂ ਨੂੰ ਪ੍ਰਾਪਤ ਅਤੇ ਚਲਾਉਂਦੇ ਹਨ।
- ਮਾਡਲ ਜਵਾਬਾਂ ਨੂੰ ਬਿਹਤਰ ਬਣਾਉਣ ਲਈ ਸੰਦਰਭਿਕ ਜਾਣਕਾਰੀ ਦਿੰਦੇ ਹਨ।
- ਨਤੀਜੇ ਕਲਾਇੰਟ ਨੂੰ ਵਾਪਸ ਭੇਜਦੇ ਹਨ।
- ਜਰੂਰਤ ਪੈਣ 'ਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਦੌਰਾਨ ਸਥਿਤੀ ਨੂੰ ਕਾਇਮ ਰੱਖਦੇ ਹਨ।

Servers ਕਿਸੇ ਵੀ ਵਿਅਕਤੀ ਦੁਆਰਾ ਵਿਕਸਤ ਕੀਤੇ ਜਾ ਸਕਦੇ ਹਨ ਤਾਂ ਜੋ ਮਾਡਲ ਦੀਆਂ ਖੂਬੀਆਂ ਨੂੰ ਵਿਸ਼ੇਸ਼ਤ ਫੰਕਸ਼ਨਲਿਟੀ ਨਾਲ ਵਧਾਇਆ ਜਾ ਸਕੇ।

### 4. Server Features

ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ (MCP) ਵਿੱਚ Servers ਮੁੱਖ ਇਮਾਰਤੀ ਪੱਥਰ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ ਜੋ clients, hosts ਅਤੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ ਵਿਚਕਾਰ ਸਮ੍ਰਿੱਧ ਇੰਟਰੈਕਸ਼ਨ ਦੀ ਆਗਿਆ ਦਿੰਦੇ ਹਨ। ਇਹ ਫੀਚਰ MCP ਦੀ ਖੂਬੀਆਂ ਨੂੰ ਵਧਾਉਂਦੇ ਹਨ ਜਿਵੇਂ ਕਿ ਸਤਰਬੱਧ ਸੰਦਰਭ, ਟੂਲ ਅਤੇ ਪ੍ਰੌਂਪਟ ਪ੍ਰਦਾਨ ਕਰਨਾ।

MCP ਸਰਵਰ ਹੇਠ ਲਿਖੀਆਂ ਕਿਸੇ ਵੀ ਫੀਚਰ ਨੂੰ ਪ੍ਰਦਾਨ ਕਰ ਸਕਦੇ ਹਨ:

#### 📑 ਸਰੋਤ (Resources)

MCP ਵਿੱਚ ਸਰੋਤ ਉਹ ਵੱਖ-ਵੱਖ ਕਿਸਮਾਂ ਦੇ ਸੰਦਰਭ ਅਤੇ ਡਾਟਾ ਹਨ ਜੋ ਯੂਜ਼ਰ ਜਾਂ AI ਮਾਡਲ ਵਰਤ ਸਕਦੇ ਹਨ। ਇਹ ਵਿੱਚ ਸ਼ਾਮਿਲ ਹਨ:

- **ਸੰਦਰਭਿਕ ਡਾਟਾ**: ਜਾਣਕਾਰੀ ਅਤੇ ਸੰਦਰਭ ਜੋ ਯੂਜ਼ਰ ਜਾਂ AI ਮਾਡਲ ਫੈਸਲੇ ਕਰਨ ਅਤੇ ਕੰਮ ਕਰਨ ਲਈ ਵਰਤ ਸਕਦੇ ਹਨ।
- **ਨੋਲੇਜ ਬੇਸ ਅਤੇ ਦਸਤਾਵੇਜ਼ ਸੰਗ੍ਰਹਿ**: ਸੰਰਚਿਤ ਅਤੇ ਅਸੰਰਚਿਤ ਡਾਟਾ ਦੇ ਕਲੈਕਸ਼ਨ, ਜਿਵੇਂ ਲੇਖ, ਮੈਨੂਅਲ ਅਤੇ ਰਿਸਰਚ ਪੇਪਰ, ਜੋ ਕੀਮਤੀ ਜਾਣਕਾਰੀ ਦਿੰਦੇ ਹਨ।
- **ਲੋਕਲ ਫਾਈਲਾਂ ਅਤੇ ਡਾਟਾਬੇਸ**: ਉਹ ਡਾਟਾ ਜੋ ਸਥਾਨਕ ਜੰਤਰਾਂ ਜਾਂ ਡਾਟਾਬੇਸ ਵਿੱਚ ਸਟੋਰ ਕੀਤਾ ਗਿਆ ਹੈ, ਪ੍ਰੋਸੈਸਿੰਗ ਅਤੇ ਵਿਸ਼ਲੇਸ਼ਣ ਲਈ ਉਪਲਬਧ।
- **API ਅਤੇ ਵੈੱਬ ਸਰਵਿਸਜ਼**: ਬਾਹਰੀ ਇੰਟਰਫੇਸ ਅਤੇ ਸਰਵਿਸਜ਼ ਜੋ ਵਾਧੂ ਡਾਟਾ ਅਤੇ ਫੰਕਸ਼ਨਲਿਟੀ ਦਿੰਦੇ ਹਨ, ਵੱਖ-ਵੱਖ ਔਨਲਾਈਨ ਸਰੋਤਾਂ ਅਤੇ ਟੂਲਾਂ ਨਾਲ ਇੰਟਿਗ੍ਰੇਸ਼ਨ ਲਈ।

ਸਰੋਤ ਦਾ ਇੱਕ ਉਦਾਹਰਨ ਡਾਟਾਬੇਸ ਸਕੀਮਾ ਜਾਂ ਫਾਈਲ ਹੋ ਸਕਦੀ ਹੈ ਜਿਸ ਤਰ੍ਹਾਂ ਐਕਸੈੱਸ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ:

```text
file://log.txt
database://schema
```

### 🤖 ਪ੍ਰੌਂਪਟ (Prompts)

MCP ਵਿੱਚ ਪ੍ਰੌਂਪਟ ਵੱਖ-ਵੱਖ ਪਹਿਲਾਂ ਤੋਂ ਪਰਿਭਾਸ਼ਿਤ ਟੈਂਪਲੇਟ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਪੈਟਰਨ ਸ਼ਾਮਿਲ ਹਨ ਜੋ ਯੂਜ਼ਰ ਵਰਕਫਲੋਜ਼ ਨੂੰ ਸੁਗਮ ਬਣਾਉਂਦੇ ਹਨ ਅਤੇ ਸੰਚਾਰ ਨੂੰ ਬਿਹਤਰ ਬਣਾਉਂਦੇ ਹਨ। ਇਹ ਵਿੱਚ ਸ਼ਾਮਿਲ ਹਨ:

- **ਟੈਂਪਲੇਟ ਕੀਤੇ ਸੁਨੇਹੇ ਅਤੇ ਵਰਕਫਲੋਜ਼**: ਪਹਿਲਾਂ ਤੋਂ ਬਣਾਏ ਗਏ ਸੁਨੇਹੇ ਅਤੇ ਪ੍ਰਕਿਰਿਆਵਾਂ ਜੋ ਯੂਜ਼ਰਾਂ ਨੂੰ ਵਿਸ਼ੇਸ਼ ਕੰਮਾਂ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨਾਂ ਵਿੱਚ ਮਦਦ ਕਰਦੀਆਂ ਹਨ।
- **ਪੂਰਵ-ਨਿਰਧਾਰਤ ਇੰਟਰੈਕਸ਼ਨ ਪੈਟਰਨ**: ਐਸੇ ਸਟੈਂਡਰਡ ਕਦਮ ਅਤੇ ਜਵਾਬਾਂ ਦੇ ਲੜੀਵਾਰ ਜੋ ਲਗਾਤਾਰ ਅਤੇ ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਸੰਚਾਰ ਨੂੰ ਸੁਨਿਸ਼ਚਿਤ ਕਰਦੇ ਹਨ।
- **ਖ਼ਾਸ ਗੱਲਬਾਤ ਟੈਂਪਲੇਟ**: ਵਿਸ਼ੇਸ਼ ਕਿਸਮ ਦੀਆਂ ਗੱਲਬਾਤਾਂ ਲਈ ਕਸਟਮਾਈਜ਼ ਕਰਨ ਯੋਗ ਟੈਂਪਲੇਟ, ਜੋ ਸੰਬੰਧਿਤ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ ਤੇ ਉਚਿਤ ਇੰਟਰੈਕਸ਼ਨਾਂ ਨੂੰ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ।

ਇੱਕ ਪ੍ਰੌਂਪਟ ਟੈਂਪਲੇਟ ਇਸ ਤਰ੍ਹਾਂ ਹੋ ਸਕਦਾ ਹੈ:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ ਟੂਲ (Tools)

MCP ਵਿੱਚ ਟੂਲ ਉਹ ਫੰਕਸ਼ਨ ਹਨ ਜੋ AI ਮਾਡਲ ਵੱਲੋਂ ਕਿਸੇ ਵਿਸ਼ੇਸ਼ ਕੰਮ ਨੂੰ ਕਰਨ ਲਈ ਚਲਾਏ ਜਾ ਸਕਦੇ ਹਨ। ਇਹ ਟੂਲ AI ਮਾਡਲ ਦੀਆਂ ਖੂਬੀਆਂ ਨੂੰ ਸੰਰਚਿਤ ਅਤੇ ਭਰੋਸੇਯੋਗ ਢੰਗ ਨਾਲ ਕਾਰਜ ਕਰਨ ਲਈ ਵਧਾਉਂਦੇ ਹਨ। ਮੁੱਖ ਪੱਖਾਂ ਵਿੱਚ ਸ਼ਾਮਿਲ ਹਨ:

- **AI ਮਾਡਲ ਵੱਲੋਂ ਚਲਾਏ ਜਾਣ ਵਾਲੇ ਫੰਕਸ਼ਨ**: ਟੂਲ ਐਸੇ ਕਾਰਜ ਹਨ ਜੋ AI ਮਾਡਲ ਵੱਲੋਂ ਕਾਲ ਕੀਤੇ ਜਾ ਸਕਦੇ ਹਨ।
- **ਵੱਖਰਾ ਨਾਮ ਅਤੇ ਵੇਰਵਾ**: ਹਰ ਟੂਲ ਦਾ ਇੱਕ ਵਿਲੱਖਣ ਨਾਮ ਅਤੇ ਇਸਦੇ ਉਦੇਸ਼ ਅਤੇ ਕਾਰਜਸ਼ੀਲਤਾ ਦੀ ਵਿਸਥਾਰਿਤ ਵਰਣਨਾ ਹੁੰਦੀ ਹੈ।
- **ਪੈਰਾਮੀਟਰ ਅਤੇ ਨਤੀਜੇ**: ਟੂਲ ਖਾਸ ਪੈਰਾਮੀਟਰ ਲੈਂਦੇ ਹਨ ਅਤੇ ਸੰਰਚਿਤ ਨਤੀਜੇ ਵਾਪਸ ਕਰਦੇ ਹਨ, ਜੋ ਲਗਾਤਾਰ ਅਤੇ ਪੇਸ਼ਗੀ ਅੰਦਾਜ਼ੇਯੋਗ ਨਤੀਜੇ ਯਕੀਨੀ ਬਣਾਉਂਦੇ ਹਨ।
- **ਵੱਖ-ਵੱਖ ਫੰਕਸ਼ਨ**: ਟੂਲ ਵੈੱਬ ਖੋਜ, ਗਣਨਾ, ਡਾਟਾਬੇਸ ਕਵੈਰੀਜ਼ ਵਰਗੇ ਵੱਖ-ਵੱਖ ਕਾਰਜ ਕਰਦੇ ਹਨ।

ਇੱਕ ਉਦਾਹਰਨ ਟੂਲ ਇਸ ਤਰ੍ਹਾਂ ਹੋ ਸਕਦਾ ਹੈ:

```typescript
server.tool(
  "GetProducts"
  {
    pageSize: z.string().optional(),
    pageCount: z.string().optional()
  }, () => {
    // return results from API
  }
)
```

## Client Features

MCP ਵਿੱਚ clients ਸਰਵਰਾਂ ਨੂੰ ਕਈ ਮੁੱਖ ਖੂਬੀਆਂ ਦਿੰਦੇ ਹਨ, ਜੋ ਪ੍ਰੋਟੋਕੋਲ ਦੀ ਕੁੱਲ ਕਾਰਗੁਜ਼ਾਰੀ ਅਤੇ ਇੰਟਰੈਕਸ਼ਨ ਨੂੰ ਵਧਾਉਂਦੀਆਂ ਹਨ। ਇਨ੍ਹਾਂ ਵਿੱਚੋਂ ਇੱਕ ਪ੍ਰਮੁੱਖ ਫੀਚਰ Sampling ਹੈ।

### 👉 Sampling

- **ਸਰਵਰ-ਆਰੰਭਿਤ ਏਜੈਂਟਿਕ ਵਿਹਾਰ**: Clients ਸਰਵਰਾਂ ਨੂੰ ਖ਼ਾਸ ਕਾਰਵਾਈਆਂ ਜਾਂ ਵਿਹਾਰ ਆਟੋਮੈਟਿਕ ਸ਼ੁਰੂ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦੇ ਹਨ, ਜਿਸ ਨਾਲ ਸਿਸਟਮ ਦੀ ਗਤੀਸ਼ੀਲ ਖੂਬੀਆਂ ਵਧਦੀਆਂ ਹਨ।
- **Recursive LLM ਇੰਟਰੈਕਸ਼ਨ**: ਇਹ ਫੀਚਰ ਵੱਡੇ ਭਾਸ਼ਾ ਮਾਡਲਾਂ ਨਾਲ ਦੁਹਰਾਈ ਜਾਂਦੀ ਇੰਟਰੈਕਸ਼ਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ, ਜੋ ਕੰਮਾਂ ਦੀ ਜਟਿਲ ਅਤੇ ਮੁੜ-ਮੁੜ ਪ੍ਰਕਿਰਿਆ ਨੂੰ ਸਮਰਥਿਤ ਕਰਦਾ ਹੈ।
- **ਵਾਧੂ ਮਾਡਲ ਪੂਰਨਤਾ ਦੀ ਬੇਨਤੀ**: ਸਰਵਰ ਮਾਡਲ ਤੋਂ ਵਾਧੂ ਪੂਰਨਤਾਵਾਂ ਮੰਗ ਸਕਦੇ ਹਨ, ਜਿਸ ਨਾਲ ਜਵਾਬ ਪੂਰਨ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ ਤੇ ਸਹੀ ਹੁੰਦੇ ਹਨ।

## MCP ਵਿੱਚ ਜਾਣਕਾਰੀ ਦਾ ਪ੍ਰਵਾਹ

ਮਾਡਲ ਸੰਦਰਭ ਪ੍ਰੋਟੋਕੋਲ (MCP) Hosts, Clients, Servers ਅਤੇ ਮਾਡਲਾਂ ਵਿਚਕਾਰ ਜਾਣਕਾਰੀ ਦੇ ਸਤਰਬੱਧ ਪ੍ਰਵਾਹ ਨੂੰ ਪਰਿਭਾਸ਼ਿਤ ਕਰਦਾ ਹੈ। ਇਸ ਪ੍ਰਵਾਹ ਨੂੰ ਸਮਝਣ ਨਾਲ ਇਹ ਸਪਸ਼ਟ ਹੁੰਦਾ ਹੈ ਕਿ ਯੂਜ਼ਰ ਬੇਨਤੀਆਂ ਕਿਵੇਂ ਪ੍ਰੋਸੈਸ ਹੁੰਦੀਆਂ ਹਨ ਅਤੇ ਕਿਵੇਂ ਬਾਹਰੀ ਟੂਲ ਅਤੇ ਡਾਟਾ ਮਾਡਲ ਜਵਾਬਾਂ ਵਿੱਚ ਸ਼ਾਮਿਲ ਹੁੰਦੇ ਹਨ।

- **Host ਕਨੈਕਸ਼ਨ ਸ਼ੁਰੂ ਕਰਦਾ ਹੈ**  
  Host ਐਪਲੀਕੇਸ਼ਨ (ਜਿਵੇਂ IDE ਜਾਂ ਚੈਟ ਇੰਟਰਫੇਸ) ਆਮ ਤੌਰ 'ਤੇ STDIO, WebSocket ਜਾਂ ਹੋਰ ਸਮਰਥਿਤ ਟਰਾਂਸਪੋਰਟ ਰਾਹੀਂ MCP ਸਰਵਰ ਨਾਲ ਕਨੈਕਸ਼ਨ ਸਥਾਪਤ ਕਰਦਾ ਹੈ।

- **ਖੂਬੀ ਮੋਲ-ਤੋਲ**  
  Client (ਜੋ host ਵਿੱਚ ਇੰਬੈਡ ਕੀਤਾ ਹੁੰਦਾ ਹੈ) ਅਤੇ ਸਰਵਰ ਆਪਣੀਆਂ ਖੂਬੀਆਂ, ਟੂਲ, ਸਰੋਤ ਅਤੇ ਪ੍ਰੋਟੋਕੋਲ ਵਰਜਨਾਂ ਬਾਰੇ ਜਾਣਕਾਰੀ ਸਾਂਝੀ ਕਰਦੇ ਹਨ। ਇਸ ਨਾਲ ਦੋਹਾਂ ਪੱਖਾਂ ਨੂੰ ਪਤਾ ਲੱਗਦਾ ਹੈ ਕਿ ਕਿਹੜੀਆਂ ਖੂਬੀਆਂ ਸੈਸ਼ਨ ਲਈ ਉਪਲਬਧ ਹਨ।

- **ਯੂਜ਼ਰ ਬੇਨਤੀ**  
  ਯੂਜ਼ਰ host ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦਾ ਹੈ (ਜਿਵੇਂ ਪ੍ਰੌਂਪਟ ਜਾਂ ਕਮਾਂਡ ਦਿੰਦਾ ਹੈ)। Host ਇਹ ਇਨਪੁੱਟ ਇਕੱਤਰ ਕਰਦਾ ਹੈ ਅਤੇ ਪ੍ਰੋਸੈਸਿੰਗ ਲਈ client ਨੂੰ ਭੇਜਦਾ ਹੈ।

- **ਸਰੋਤ ਜਾਂ ਟੂਲ ਦੀ ਵਰਤੋਂ**  
  - Client ਸਰਵਰ ਤੋਂ ਵਾਧੂ ਸੰਦਰਭ ਜਾਂ ਸਰੋਤ (ਜਿਵੇਂ ਫਾਈਲਾਂ, ਡਾਟਾਬੇਸ ਐਂਟਰੀਜ਼, ਜਾਂ ਨੋਲੇਜ ਬੇਸ ਲੇਖ) ਮੰਗ ਸਕਦਾ ਹੈ ਤਾਂ ਜੋ ਮਾਡਲ ਦੀ ਸਮਝ ਨੂੰ ਧਨਵੰਤ ਕੀਤਾ ਜਾ ਸਕੇ।  
  - ਜੇ ਮਾਡਲ ਨੂੰ ਲੱਗਦਾ ਹੈ ਕਿ ਟੂਲ ਦੀ ਲੋੜ ਹੈ (ਜਿਵੇਂ ਡਾਟਾ ਲੈਣਾ, ਗਣਨਾ ਕਰਨੀ, ਜਾਂ API ਕਾਲ ਕਰਨੀ), ਤਾਂ client ਸਰਵਰ ਨੂੰ ਟੂਲ ਕਾਲ ਦੀ ਬੇਨਤੀ ਭੇਜਦਾ ਹੈ, ਜਿਸ ਵਿੱਚ ਟੂਲ ਦਾ ਨਾਮ ਅਤੇ ਪੈਰਾਮੀਟਰ ਹੁੰਦੇ ਹਨ।

- **ਸਰਵਰ ਚਲਾਉਣਾ**  
  ਸਰਵਰ ਸਰੋਤ ਜਾਂ ਟੂਲ ਦੀ ਬੇਨਤੀ ਪ੍ਰਾਪਤ ਕਰਦਾ ਹੈ, ਜਰੂਰੀ ਕਾਰਵਾਈਆਂ ਕਰਦਾ ਹੈ (ਜਿਵੇਂ ਫੰਕਸ਼ਨ ਚਲਾਉਣਾ, ਡਾਟਾਬੇਸ ਕਵੈਰੀ ਕਰਨਾ, ਜਾਂ ਫਾਈਲ ਪ੍ਰਾਪਤ ਕਰਨੀ) ਅਤੇ ਨਤੀਜੇ client ਨੂੰ ਸੰਰਚਿਤ ਰੂਪ ਵਿੱਚ ਵਾਪਸ ਭੇਜਦਾ ਹੈ।

- **ਜਵਾਬ ਬਣਾਉਣਾ**  
  Client ਸਰਵਰ ਦੇ ਜਵਾਬਾਂ (ਸਰੋਤ ਡਾਟਾ, ਟੂਲ ਨਤੀਜੇ ਆਦਿ) ਨੂੰ ਮਾਡਲ ਨਾਲ ਚੱਲ ਰਹੀ ਇੰਟਰੈਕਸ਼ਨ ਵਿੱਚ ਸ਼ਾਮਿਲ ਕਰਦਾ ਹੈ। ਮਾਡਲ ਇਸ ਜਾਣਕਾਰੀ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਇੱਕ ਵਿਸਥਾਰਿਤ ਅਤੇ ਸੰਦਰਭਿਕ ਤੌਰ ਤੇ ਉਚਿਤ ਜਵਾਬ ਤਿਆਰ ਕਰਦਾ ਹੈ।

- **ਨਤੀਜੇ ਪੇਸ਼ ਕਰਨਾ**  
  Host client ਤੋਂ ਅੰਤਿਮ ਨਤੀਜਾ ਪ੍ਰਾਪਤ ਕਰਦਾ ਹੈ ਅਤੇ ਯੂਜ਼ਰ ਨੂੰ ਦਿਖਾਉਂਦਾ ਹੈ, ਜ਼ਿਆਦਾਤਰ ਮਾਡਲ ਵੱਲੋਂ ਬਣਾਈ ਗਈ ਲਿਖਤ ਅਤੇ ਟੂਲ ਚਲਾਉਣ ਜਾਂ ਸਰੋਤ ਲੁਕਅਪ ਦੇ ਨਤੀਜੇ ਸਮੇਤ।

ਇਹ ਪ੍ਰਵਾਹ MCP ਨੂੰ ਉੱਚ-ਪੱਧਰੀ, ਇੰਟਰੈਕਟਿਵ ਅਤੇ ਸੰਦਰਭ-ਜਾਣੂ AI ਐਪਲੀਕੇਸ਼ਨਾਂ ਨੂੰ ਸਮਰਥਿਤ ਕਰਦਾ ਹੈ, ਮਾਡਲਾਂ ਨੂੰ ਬ

**ਅਸਵੀਕਾਰੋਪਣ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀਅਤ ਲਈ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਰੱਖੋ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸਮਰਥਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਆਪਣੇ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਿਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਅਸੀਂ ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਉਪਜੀਆਂ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀਆਂ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆਵਾਂ ਲਈ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।