<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "788eb17750e970a0bc3b5e7f2e99975b",
  "translation_date": "2025-05-18T14:54:38+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "ru"
}
-->
# 📖 Основные концепции MCP: Осваиваем протокол контекста модели для интеграции ИИ

Протокол контекста модели (MCP) — это мощная стандартизированная система, которая оптимизирует взаимодействие между крупными языковыми моделями (LLM) и внешними инструментами, приложениями и источниками данных. Это SEO-оптимизированное руководство познакомит вас с ключевыми концепциями MCP, объясняя клиент-серверную архитектуру, основные компоненты, механизмы коммуникации и лучшие практики реализации.

## Обзор

В этом уроке рассматривается базовая архитектура и компоненты экосистемы протокола контекста модели (MCP). Вы узнаете о клиент-серверной архитектуре, ключевых элементах и механизмах обмена данными, обеспечивающих работу MCP.

## 👩‍🎓 Основные цели обучения

К концу урока вы:

- Поймёте клиент-серверную архитектуру MCP.
- Определите роли и обязанности Hosts, Clients и Servers.
- Проанализируете ключевые особенности, делающие MCP гибким слоем интеграции.
- Узнаете, как происходит поток информации внутри экосистемы MCP.
- Получите практические знания на примерах кода на .NET, Java, Python и JavaScript.

## 🔎 Архитектура MCP: подробный взгляд

Экосистема MCP построена на модели клиент-сервер. Такая модульная структура позволяет приложениям ИИ эффективно взаимодействовать с инструментами, базами данных, API и контекстными ресурсами. Разберём архитектуру на основные компоненты.

### 1. Hosts

В протоколе контекста модели (MCP) Hosts играют ключевую роль как основной интерфейс, через который пользователи взаимодействуют с протоколом. Hosts — это приложения или среды, которые инициируют соединения с MCP-серверами для доступа к данным, инструментам и подсказкам. Примеры Hosts: интегрированные среды разработки (IDE) вроде Visual Studio Code, ИИ-инструменты, например Claude Desktop, или специально созданные агенты для конкретных задач.

**Hosts** — это приложения с LLM, которые инициируют соединения. Они:

- Выполняют или взаимодействуют с ИИ-моделями для генерации ответов.
- Инициируют соединения с MCP-серверами.
- Управляют ходом диалога и пользовательским интерфейсом.
- Контролируют разрешения и ограничения безопасности.
- Обрабатывают согласие пользователя на обмен данными и выполнение инструментов.

### 2. Clients

Clients — важные компоненты, которые обеспечивают взаимодействие между Hosts и MCP-серверами. Они выступают посредниками, позволяя Hosts использовать функциональность MCP-серверов. Их задача — обеспечить плавную коммуникацию и эффективный обмен данными в архитектуре MCP.

**Clients** — это коннекторы внутри приложения Host. Они:

- Отправляют запросы серверам с подсказками или инструкциями.
- Согласовывают возможности с серверами.
- Управляют запросами на выполнение инструментов от моделей.
- Обрабатывают и отображают ответы пользователям.

### 3. Servers

Servers отвечают за обработку запросов от MCP-клиентов и предоставление соответствующих ответов. Они управляют операциями, такими как получение данных, выполнение инструментов и генерация подсказок. Серверы обеспечивают эффективное и надежное взаимодействие между клиентами и Hosts, сохраняя целостность процесса общения.

**Servers** — это сервисы, предоставляющие контекст и функциональность. Они:

- Регистрируют доступные функции (ресурсы, подсказки, инструменты).
- Принимают и выполняют вызовы инструментов от клиента.
- Предоставляют контекстную информацию для улучшения ответов модели.
- Возвращают результаты обратно клиенту.
- При необходимости поддерживают состояние в течение взаимодействия.

Серверы могут разрабатываться любыми разработчиками для расширения возможностей моделей специализированным функционалом.

### 4. Функции сервера

Сервера в протоколе контекста модели (MCP) предоставляют базовые строительные блоки, которые обеспечивают богатое взаимодействие между клиентами, Hosts и языковыми моделями. Эти функции предназначены для расширения возможностей MCP за счёт структурированного контекста, инструментов и подсказок.

MCP-сервера могут предлагать следующие функции:

#### 📑 Ресурсы

Ресурсы в MCP включают различные типы контекста и данных, которые могут использоваться пользователями или ИИ-моделями. К ним относятся:

- **Контекстные данные**: информация и контекст, которые помогают пользователям или моделям принимать решения и выполнять задачи.
- **Базы знаний и хранилища документов**: коллекции структурированных и неструктурированных данных, таких как статьи, руководства и научные работы, предоставляющие ценные сведения.
- **Локальные файлы и базы данных**: данные, хранящиеся локально на устройствах или в базах данных, доступные для обработки и анализа.
- **API и веб-сервисы**: внешние интерфейсы и сервисы, предоставляющие дополнительные данные и функции, позволяющие интегрироваться с различными онлайн-ресурсами и инструментами.

Пример ресурса — схема базы данных или файл, к которому можно получить доступ следующим образом:

```text
file://log.txt
database://schema
```

### 🤖 Подсказки

Подсказки в MCP включают различные заранее определённые шаблоны и модели взаимодействия, предназначенные для упрощения рабочих процессов пользователей и улучшения коммуникации. К ним относятся:

- **Шаблонные сообщения и рабочие процессы**: заранее структурированные сообщения и процессы, которые направляют пользователей при выполнении конкретных задач.
- **Предопределённые модели взаимодействия**: стандартизированные последовательности действий и ответов, обеспечивающие последовательное и эффективное общение.
- **Специализированные шаблоны диалогов**: настраиваемые шаблоны, адаптированные под определённые типы разговоров, обеспечивающие релевантное и контекстно уместное взаимодействие.

Шаблон подсказки может выглядеть так:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ Инструменты

Инструменты в MCP — это функции, которые ИИ-модель может выполнять для решения конкретных задач. Они созданы для расширения возможностей модели за счёт структурированных и надёжных операций. Основные характеристики:

- **Функции для выполнения моделью**: инструменты — это исполняемые функции, которые модель может вызывать для выполнения различных задач.
- **Уникальное имя и описание**: каждый инструмент имеет уникальное имя и подробное описание, объясняющее его назначение и функциональность.
- **Параметры и результаты**: инструменты принимают определённые параметры и возвращают структурированные результаты, обеспечивая последовательность и предсказуемость.
- **Отдельные функции**: инструменты выполняют отдельные операции, например, веб-поиск, вычисления или запросы к базе данных.

Пример инструмента может выглядеть так:

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

## Функции клиента

В MCP клиенты предоставляют серверам несколько ключевых функций, расширяя общую функциональность и взаимодействие в протоколе. Одной из таких функций является Sampling.

### 👉 Sampling

- **Инициируемые сервером агентные действия**: клиенты позволяют серверам самостоятельно инициировать определённые действия или поведения, повышая динамичность системы.
- **Рекурсивное взаимодействие с LLM**: эта функция поддерживает рекурсивные взаимодействия с крупными языковыми моделями, позволяя более сложную и итеративную обработку задач.
- **Запрос дополнительных завершений модели**: серверы могут запрашивать у модели дополнительные ответы, чтобы обеспечить полноту и контекстную релевантность результатов.

## Поток информации в MCP

Протокол контекста модели (MCP) определяет структурированный поток информации между Hosts, Clients, Servers и моделями. Понимание этого процесса помогает разобраться, как обрабатываются запросы пользователей и как внешние инструменты и данные интегрируются в ответы модели.

- **Host инициирует соединение**  
  Приложение Host (например, IDE или чат-интерфейс) устанавливает соединение с MCP-сервером, обычно через STDIO, WebSocket или другой поддерживаемый транспорт.

- **Согласование возможностей**  
  Клиент (встроенный в Host) и сервер обмениваются информацией о поддерживаемых функциях, инструментах, ресурсах и версиях протокола. Это гарантирует, что обе стороны понимают доступные возможности для сессии.

- **Запрос пользователя**  
  Пользователь взаимодействует с Host (например, вводит подсказку или команду). Host собирает ввод и передаёт его клиенту для обработки.

- **Использование ресурса или инструмента**  
  - Клиент может запросить у сервера дополнительные контекстные данные или ресурсы (например, файлы, записи базы данных или статьи из базы знаний) для обогащения понимания модели.
  - Если модель определяет необходимость использования инструмента (например, для получения данных, вычислений или вызова API), клиент отправляет серверу запрос на вызов инструмента с указанием имени и параметров.

- **Выполнение на сервере**  
  Сервер получает запрос на ресурс или инструмент, выполняет необходимые операции (запуск функции, запрос к базе данных, получение файла) и возвращает результаты клиенту в структурированном виде.

- **Генерация ответа**  
  Клиент интегрирует ответы сервера (данные ресурсов, результаты инструментов и т. п.) в текущую модельную сессию. Модель использует эту информацию для создания полного и контекстно релевантного ответа.

- **Представление результата**  
  Host получает итоговый вывод от клиента и отображает его пользователю, часто включая сгенерированный текст модели и результаты выполнения инструментов или поиска ресурсов.

Этот процесс позволяет MCP поддерживать продвинутые, интерактивные и контекстно осведомлённые приложения ИИ, бесшовно соединяя модели с внешними инструментами и источниками данных.

## Детали протокола

MCP (Model Context Protocol) построен на базе [JSON-RPC 2.0](https://www.jsonrpc.org/), предоставляя стандартизированный, независимый от языка формат сообщений для общения между Hosts, Clients и Servers. Эта основа обеспечивает надёжное, структурированное и расширяемое взаимодействие на различных платформах и языках программирования.

### Ключевые особенности протокола

MCP расширяет JSON-RPC 2.0 дополнительными соглашениями для вызова инструментов, доступа к ресурсам и управления подсказками. Он поддерживает несколько транспортных уровней (STDIO, WebSocket, SSE) и обеспечивает безопасную, расширяемую и независимую от языка коммуникацию между компонентами.

#### 🧢 Базовый протокол

- **Формат сообщений JSON-RPC**: все запросы и ответы используют спецификацию JSON-RPC 2.0, гарантируя единообразную структуру вызовов методов, параметров, результатов и обработки ошибок.
- **Состояние соединения**: сессии MCP сохраняют состояние между запросами, поддерживая непрерывные диалоги, накопление контекста и управление ресурсами.
- **Согласование возможностей**: при установлении соединения клиенты и серверы обмениваются информацией о поддерживаемых функциях, версиях протокола, доступных инструментах и ресурсах. Это обеспечивает взаимное понимание возможностей и адаптацию.

#### ➕ Дополнительные утилиты

Ниже перечислены дополнительные утилиты и расширения протокола MCP, которые улучшают опыт разработчиков и поддерживают сложные сценарии:

- **Опции конфигурации**: MCP позволяет динамически настраивать параметры сессии, такие как разрешения на инструменты, доступ к ресурсам и настройки модели, адаптированные под каждое взаимодействие.
- **Отслеживание прогресса**: долгие операции могут сообщать о ходе выполнения, обеспечивая отзывчивый интерфейс и лучший пользовательский опыт при сложных задачах.
- **Отмена запросов**: клиенты могут отменять текущие запросы, позволяя пользователям прерывать операции, которые больше не нужны или занимают слишком много времени.
- **Отчёты об ошибках**: стандартизированные сообщения об ошибках и коды помогают диагностировать проблемы, корректно обрабатывать сбои и предоставлять полезную обратную связь пользователям и разработчикам.
- **Логирование**: и клиенты, и серверы могут создавать структурированные логи для аудита, отладки и мониторинга взаимодействий протокола.

Используя эти возможности протокола, MCP обеспечивает надёжное, безопасное и гибкое взаимодействие между языковыми моделями и внешними инструментами или источниками данных.

### 🔐 Вопросы безопасности

Реализации MCP должны соблюдать несколько ключевых принципов безопасности для обеспечения безопасного и надёжного взаимодействия:

- **Согласие и контроль пользователя**: пользователи должны явно согласиться на доступ к данным или выполнение операций. У них должен быть чёткий контроль над тем, какие данные передаются и какие действия разрешены, поддерживаемый удобными интерфейсами для просмотра и подтверждения активности.

- **Конфиденциальность данных**: данные пользователей должны передаваться только с их явного согласия и защищаться соответствующими мерами доступа. Реализации MCP должны предотвращать несанкционированную передачу данных и обеспечивать сохранность конфиденциальности во всех взаимодействиях.

- **Безопасность инструментов**: перед вызовом любого инструмента требуется явное согласие пользователя. Пользователи должны чётко понимать функционал каждого инструмента, а также должны соблюдаться строгие меры безопасности, чтобы предотвратить нежелательное или небезопасное выполнение инструментов.

Следуя этим принципам, MCP обеспечивает доверие пользователей, защиту их приватности и безопасность во всех взаимодействиях протокола.

## Примеры кода: ключевые компоненты

Ниже представлены примеры кода на популярных языках программирования, демонстрирующие, как реализовать основные компоненты MCP-сервера и инструменты.

### Пример на .NET: создание простого MCP-сервера с инструментами

Практический пример на .NET показывает, как реализовать простой MCP-сервер с пользовательскими инструментами. В этом примере показано, как определить и зарегистрировать инструменты, обрабатывать запросы и подключить сервер с использованием протокола контекста модели.

```csharp
using System;
using System.Threading.Tasks;
using ModelContextProtocol.Server;
using ModelContextProtocol.Server.Transport;
using ModelContextProtocol.Server.Tools;

public class WeatherServer
{
    public static async Task Main(string[] args)
    {
        // Create an MCP server
        var server = new McpServer(
            name: "Weather MCP Server",
            version: "1.0.0"
        );
        
        // Register our custom weather tool
        server.AddTool<string, WeatherData>("weatherTool", 
            description: "Gets current weather for a location",
            execute: async (location) => {
                // Call weather API (simplified)
                var weatherData = await GetWeatherDataAsync(location);
                return weatherData;
            });
        
        // Connect the server using stdio transport
        var transport = new StdioServerTransport();
        await server.ConnectAsync(transport);
        
        Console.WriteLine("Weather MCP Server started");
        
        // Keep the server running until process is terminated
        await Task.Delay(-1);
    }
    
    private static async Task<WeatherData> GetWeatherDataAsync(string location)
    {
        // This would normally call a weather API
        // Simplified for demonstration
        await Task.Delay(100); // Simulate API call
        return new WeatherData { 
            Temperature = 72.5,
            Conditions = "Sunny",
            Location = location
        };
    }
}

public class WeatherData
{
    public double Temperature { get; set; }
    public string Conditions { get; set; }
    public string Location { get; set; }
}
```

### Пример на Java: компоненты MCP-сервера

Этот пример демонстрирует тот же MCP-сервер и регистрацию инструментов, что и в примере на .NET, но реализован на Java.

```java
import io.modelcontextprotocol.server.McpServer;
import io.modelcontextprotocol.server.McpToolDefinition;
import io.modelcontextprotocol.server.transport.StdioServerTransport;
import io.modelcontextprotocol.server.tool.ToolExecutionContext;
import io.modelcontextprotocol.server.tool.ToolResponse;

public class WeatherMcpServer {
    public static void main(String[] args) throws Exception {
        // Create an MCP server
        McpServer server = McpServer.builder()
            .name("Weather MCP Server")
            .version("1.0.0")
            .build();
            
        // Register a weather tool
        server.registerTool(McpToolDefinition.builder("weatherTool")
            .description("Gets current weather for a location")
            .parameter("location", String.class)
            .execute((ToolExecutionContext ctx) -> {
                String location = ctx.getParameter("location", String.class);
                
                // Get weather data (simplified)
                WeatherData data = getWeatherData(location);
                
                // Return formatted response
                return ToolResponse.content(
                    String.format("Temperature: %.1f°F, Conditions: %s, Location: %s", 
                    data.getTemperature(), 
                    data.getConditions(), 
                    data.getLocation())
                );
            })
            .build());
        
        // Connect the server using stdio transport
        try (StdioServerTransport transport = new StdioServerTransport()) {
            server.connect(transport);
            System.out.println("Weather MCP Server started");
            // Keep server running until process is terminated
            Thread.currentThread().join();
        }
    }
    
    private static WeatherData getWeatherData(String location) {
        // Implementation would call a weather API
        // Simplified for example purposes
        return new WeatherData(72.5, "Sunny", location);
    }
}

class WeatherData {
    private double temperature;
    private String conditions;
    private String location;
    
    public WeatherData(double temperature, String conditions, String location) {
        this.temperature = temperature;
        this.conditions = conditions;
        this.location = location;
    }
    
    public double getTemperature() {
        return temperature;
    }
    
    public String getConditions() {
        return conditions;
    }
    
    public String getLocation() {
        return location;
    }
}
```

### Пример на Python: создание MCP-сервера

В этом примере показано, как построить MCP-сервер на Python. Также продемонстрированы два разных способа создания инструментов.

```python
#!/usr/bin/env python3
import asyncio
from mcp.server.fastmcp import FastMCP
from mcp.server.transports.stdio import serve_stdio

# Create a FastMCP server
mcp = FastMCP(
    name="Weather MCP Server",
    version="1.0.0"
)

@mcp.tool()
def get_weather(location: str) -> dict:
    """Gets current weather for a location."""
    # This would normally call a weather API
    # Simplified for demonstration
    return {
        "temperature": 72.5,
        "conditions": "Sunny",
        "location": location
    }

# Alternative approach using a class
class WeatherTools:
    @mcp.tool()
    def forecast(self, location: str, days: int = 1) -> dict:
        """Gets weather forecast for a location for the specified number of days."""
        # This would normally call a weather API forecast endpoint
        # Simplified for demonstration
        return {
            "location": location,
            "forecast": [
                {"day": i+1, "temperature": 70 + i, "conditions": "Partly Cloudy"}
                for i in range(days)
            ]
        }

# Initialize class for its methods to be registered as tools
weather_tools = WeatherTools()

if __name__ == "__main__":
    # Start the server with stdio transport
    print("Weather MCP Server starting...")
    asyncio.run(serve_stdio(mcp))
```

### Пример на JavaScript: создание MCP-сервера

Этот пример показывает создание MCP-сервера на JavaScript и регистрацию двух инструментов, связанных с погодой.

```javascript
// Using the official Model Context Protocol SDK
import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
import { z } from "zod"; // For parameter validation

// Create an MCP server
const server = new McpServer({
  name: "Weather MCP Server",
  version: "1.0.0"
});

// Define a weather tool
server.tool(
  "weatherTool",
  {
    location: z.string().describe("The location to get weather for")
  },
  async ({ location }) => {
    // This would normally call a weather API
    // Simplified for demonstration
    const weatherData = await getWeatherData(location);
    
    return {
      content: [
        { 
          type: "text", 
          text: `Temperature: ${weatherData.temperature}°F, Conditions: ${weatherData.conditions}, Location: ${weatherData.location}` 
        }
      ]
    };
  }
);

// Define a forecast tool
server.tool(
  "forecastTool",
  {
    location: z.string(),
    days: z.number().default(3).describe("Number of days for forecast")
  },
  async ({ location, days }) => {
    // This would normally call a weather API
    // Simplified for demonstration
    const forecast = await getForecastData(location, days);
    
    return {
      content: [
        { 
          type: "text", 
          text: `${days}-day forecast for ${location}: ${JSON.stringify(forecast)}` 
        }
      ]
    };
  }
);

// Helper functions
async function getWeatherData(location) {
  // Simulate API call
  return {
    temperature: 72.5,
    conditions: "Sunny",
    location: location
  };
}

async function getForecastData(location, days) {
  // Simulate API call
  return Array.from({ length: days }, (_, i) => ({
    day: i + 1,
    temperature: 70 + Math.floor(Math.random() * 10),
    conditions: i % 2 === 0 ? "Sunny" : "Partly Cloudy"
  }));
}

// Connect the server using stdio transport
const transport = new StdioServerTransport();
server.connect(transport).catch(console.error);

console.log("Weather MCP Server started");
```

Пример на JavaScript демонстрирует, как создать MCP-клиента, который подключается к серверу, отправляет подсказку и обрабатывает ответ, включая вызовы инструментов.

## Безопасность и авторизация

MCP включает несколько встроенных концепций и механизмов для управления безопасностью и авторизацией в протоколе:

1. **Контроль разрешений на инструменты**  
   Клиенты могут указывать, какими инструментами модель может пользоваться в ходе сессии. Это гарантирует доступ только к явно разрешённым инструментам, снижая риск нежелательных или небезопасных операций. Разрешения могут настраиваться динамически с учётом предпочтений пользователя, политик организации или контекста взаимодействия.

2. **Аутентификация**  
   Серверы могут требовать аутентификацию перед предоставлением доступа к инструментам, ресурсам или чувствительным операциям. Это может включать API-ключи, OAuth-токены или другие схемы аутентификации. Корректная аутентификация гарантирует, что только доверенные клиенты и пользователи могут вызывать серверные возможности.

3. **Валидация**  
   Параметры всех вызовов инструментов проходят проверку. Каждый инструмент определяет ожидаемые типы, форматы и ограничения параметров, и сервер валидирует входящие запросы соответственно. Это предотвращает попадание некорректных или вредоносных данных в реализации инструментов и помогает сохранять целостность операций.

4. **Ограничение частоты запросов**  
   Чтобы предотвратить злоупотребления и обеспечить справедливое использование ресурсов сервера, MCP-серверы могут внедрять ограничение частоты вызовов инструментов и доступа к ресурсам. Ограничения могут применяться по пользователю, сессии или глобально, защищая от атак типа отказа в обслуживании и чрезмерного потребления ресурсов.

Объединяя эти механизмы, MCP обеспечивает безопасную основу для интеграции языковых моделей с внешними инструментами и источниками данных, предоставляя пользователям и разработчикам точный контроль над доступом и использованием.

## Сообщения протокола

В MCP для обеспечения чётких и надёжных взаимодействий между клиентами, серверами и моделями используются структурированные JSON-сообщения. Основные типы сообщений:

- **Запрос клиента**  
  Отправляется клиентом серверу, обычно содержит:
  - Подсказку или команду пользователя
  - Историю диалога для контекста
  - Конфигурацию и разрешения инструментов
  - Дополнительные метаданные или информацию о сессии

- **Ответ модели**  
  Возвращается моделью (через клиента), содержит:
  - Сгенерированный текст или завершение на основе подсказки и контекста
  - Опциональные инструкции по вызову инструментов, если модель определила необходимость
  - Ссылки на ресурсы или дополнительный контекст при необходимости

- **Запрос инструмента**  
  Отправляется клиентом серверу при необходимости выполнить инструмент. Содержит:
  - Имя инструмента для вызова
  - Параметры, необходимые инструменту (валидируются по схеме инструмента)
  - Контекстную информацию или идентификаторы для отслеживания запроса

- **Ответ инструмента**  
  Возвращается сервером после выполнения инструмента. Включает:
  - Результаты выполнения инструмента (структ

**Отказ от ответственности**:  
Этот документ был переведен с помощью сервиса автоматического перевода [Co-op Translator](https://github.com/Azure/co-op-translator). Несмотря на наши усилия по обеспечению точности, пожалуйста, имейте в виду, что автоматические переводы могут содержать ошибки или неточности. Оригинальный документ на его исходном языке следует считать авторитетным источником. Для критически важной информации рекомендуется использовать профессиональный человеческий перевод. Мы не несем ответственности за любые недоразумения или неправильные толкования, возникшие в результате использования данного перевода.