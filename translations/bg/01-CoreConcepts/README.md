<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "788eb17750e970a0bc3b5e7f2e99975b",
  "translation_date": "2025-05-18T15:35:35+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "bg"
}
-->
# 📖 Основни концепции на MCP: Майсторство в Model Context Protocol за интеграция на AI

Model Context Protocol (MCP) е мощна, стандартизирана рамка, която оптимизира комуникацията между големи езикови модели (LLMs) и външни инструменти, приложения и източници на данни. Това SEO-оптимизирано ръководство ще ви преведе през основните концепции на MCP, като гарантира, че разбирате клиент-сървърната архитектура, ключовите компоненти, механизмите за комуникация и най-добрите практики за внедряване.

## Преглед

Този урок разглежда фундаменталната архитектура и компоненти, които съставляват екосистемата на Model Context Protocol (MCP). Ще научите за клиент-сървърната архитектура, ключовите компоненти и комуникационните механизми, които задвижват взаимодействията в MCP.

## 👩‍🎓 Основни учебни цели

В края на този урок ще можете:

- Да разбирате клиент-сървърната архитектура на MCP.
- Да идентифицирате ролите и отговорностите на Hosts, Clients и Servers.
- Да анализирате основните характеристики, които правят MCP гъвкав слой за интеграция.
- Да научите как тече информацията в екосистемата на MCP.
- Да придобиете практически знания чрез кодови примери на .NET, Java, Python и JavaScript.

## 🔎 Архитектура на MCP: По-задълбочен поглед

Екосистемата на MCP е изградена върху клиент-сървърен модел. Тази модулна структура позволява на AI приложенията ефективно да взаимодействат с инструменти, бази данни, API-та и контекстуални ресурси. Нека разгледаме архитектурата и нейните основни компоненти.

### 1. Hosts

В Model Context Protocol (MCP) Hosts играят ключова роля като основния интерфейс, чрез който потребителите взаимодействат с протокола. Hosts са приложения или среди, които инициират връзки със MCP сървъри за достъп до данни, инструменти и подсказки. Примери за Hosts са интегрирани среди за разработка (IDE) като Visual Studio Code, AI инструменти като Claude Desktop или агенти, създадени специално за конкретни задачи.

**Hosts** са LLM приложения, които инициират връзки. Те:

- Изпълняват или взаимодействат с AI модели за генериране на отговори.
- Инициират връзки с MCP сървъри.
- Управляват потока на разговора и потребителския интерфейс.
- Контролират разрешения и ограничения за сигурност.
- Обработват съгласието на потребителя за споделяне на данни и изпълнение на инструменти.

### 2. Clients

Clients са съществени компоненти, които улесняват взаимодействието между Hosts и MCP сървъри. Clients действат като посредници, позволявайки на Hosts да достъпват и използват функционалностите, предоставяни от MCP сървърите. Те играят ключова роля за осигуряване на гладка комуникация и ефективен обмен на данни в архитектурата на MCP.

**Clients** са конектори в рамките на хост приложението. Те:

- Изпращат заявки към сървърите с подсказки/инструкции.
- Договарят възможностите със сървърите.
- Управляват заявки за изпълнение на инструменти от моделите.
- Обработват и показват отговорите на потребителите.

### 3. Servers

Servers отговарят за обработката на заявки от MCP clients и предоставянето на подходящи отговори. Те управляват различни операции като извличане на данни, изпълнение на инструменти и генериране на подсказки. Servers гарантират, че комуникацията между clients и Hosts е ефективна и надеждна, поддържайки целостта на процеса на взаимодействие.

**Servers** са услуги, които предоставят контекст и възможности. Те:

- Регистрират налични функции (ресурси, подсказки, инструменти).
- Получават и изпълняват повиквания на инструменти от клиента.
- Предоставят контекстуална информация за подобряване на отговорите на модела.
- Връщат резултати обратно на клиента.
- Поддържат състояние между взаимодействията, когато е необходимо.

Servers могат да бъдат разработвани от всеки, за да разширят възможностите на модела със специализирана функционалност.

### 4. Функции на сървъра

Сървърите в Model Context Protocol (MCP) предоставят основни градивни елементи, които позволяват богати взаимодействия между clients, hosts и езиковите модели. Тези функции са създадени да разширят възможностите на MCP, предлагайки структурирани контекст, инструменти и подсказки.

MCP сървърите могат да предлагат някоя от следните функции:

#### 📑 Ресурси

Ресурсите в Model Context Protocol (MCP) обхващат различни видове контекст и данни, които могат да бъдат използвани от потребители или AI модели. Те включват:

- **Контекстуални данни**: Информация и контекст, които потребителите или AI моделите могат да използват за вземане на решения и изпълнение на задачи.
- **Бази знания и хранилища с документи**: Колекции от структурирани и неструктурирани данни, като статии, ръководства и научни трудове, които предоставят ценна информация и прозрения.
- **Локални файлове и бази данни**: Данни, съхранявани локално на устройства или в бази данни, достъпни за обработка и анализ.
- **API-та и уеб услуги**: Външни интерфейси и услуги, които предлагат допълнителни данни и функционалности, позволяващи интеграция с различни онлайн ресурси и инструменти.

Пример за ресурс може да бъде схема на база данни или файл, достъпен по следния начин:

```text
file://log.txt
database://schema
```

### 🤖 Подсказки

Подсказките в Model Context Protocol (MCP) включват различни предварително дефинирани шаблони и модели на взаимодействие, създадени да улеснят работните потоци на потребителите и да подобрят комуникацията. Те включват:

- **Шаблонирани съобщения и работни потоци**: Предварително структурирани съобщения и процеси, които водят потребителите през конкретни задачи и взаимодействия.
- **Предварително дефинирани модели на взаимодействие**: Стандартизирани последователности от действия и отговори, които улесняват последователна и ефективна комуникация.
- **Специализирани шаблони за разговори**: Персонализирани шаблони, пригодени за конкретни типове разговори, осигуряващи релевантни и контекстуално подходящи взаимодействия.

Шаблон за подсказка може да изглежда така:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ Инструменти

Инструментите в Model Context Protocol (MCP) са функции, които AI моделът може да изпълни, за да извърши конкретни задачи. Тези инструменти са проектирани да разширят възможностите на AI модела, като предоставят структурирани и надеждни операции. Основните характеристики включват:

- **Функции за изпълнение от AI модела**: Инструментите са изпълними функции, които AI моделът може да извика, за да извърши различни задачи.
- **Уникално име и описание**: Всеки инструмент има уникално име и подробно описание, което обяснява целта и функционалността му.
- **Параметри и изходни данни**: Инструментите приемат конкретни параметри и връщат структурирани резултати, осигурявайки последователни и предвидими резултати.
- **Отделни функции**: Инструментите изпълняват отделни функции като уеб търсения, изчисления и заявки към бази данни.

Примерен инструмент може да изглежда така:

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

## Функции на клиента

В Model Context Protocol (MCP) клиентите предлагат няколко ключови функции на сървърите, които подобряват цялостната функционалност и взаимодействие в протокола. Една от забележителните функции е Sampling.

### 👉 Sampling

- **Сървърно инициирани агентни поведения**: Клиентите позволяват на сървърите да инициират специфични действия или поведения автономно, разширявайки динамичните възможности на системата.
- **Рекурсивни взаимодействия с LLM**: Тази функция позволява рекурсивни взаимодействия с големи езикови модели (LLM), осигурявайки по-сложна и итеративна обработка на задачи.
- **Заявка за допълнителни завършвания на модела**: Сървърите могат да поискат допълнителни завършвания от модела, гарантирайки, че отговорите са изчерпателни и контекстуално релевантни.

## Поток на информацията в MCP

Model Context Protocol (MCP) дефинира структуриран поток на информация между hosts, clients, servers и модели. Разбирането на този поток помага да се изясни как се обработват потребителските заявки и как външните инструменти и данни се интегрират в отговорите на модела.

- **Host инициира връзка**  
  Хост приложението (например IDE или чат интерфейс) установява връзка със MCP сървър, обикновено чрез STDIO, WebSocket или друг поддържан транспорт.

- **Договаряне на възможности**  
  Клиентът (вграден в хоста) и сървърът обменят информация за поддържаните функции, инструменти, ресурси и версии на протокола. Това гарантира, че и двете страни разбират наличните възможности за сесията.

- **Потребителска заявка**  
  Потребителят взаимодейства с хоста (например въвежда подсказка или команда). Хостът събира този вход и го предава на клиента за обработка.

- **Използване на ресурс или инструмент**  
  - Клиентът може да поиска допълнителен контекст или ресурси от сървъра (като файлове, записи в база данни или статии от база знания) за обогатяване на разбирането на модела.
  - Ако моделът определи, че е необходим инструмент (например за извличане на данни, извършване на изчисление или повикване на API), клиентът изпраща заявка за извикване на инструмента към сървъра, посочвайки името на инструмента и параметрите.

- **Изпълнение от сървъра**  
  Сървърът получава заявката за ресурс или инструмент, изпълнява необходимите операции (като стартиране на функция, заявка към база данни или извличане на файл) и връща резултатите на клиента в структурирана форма.

- **Генериране на отговор**  
  Клиентът интегрира отговорите от сървъра (данни от ресурси, резултати от инструменти и т.н.) в текущото взаимодействие с модела. Моделът използва тази информация, за да генерира изчерпателен и контекстуално релевантен отговор.

- **Представяне на резултата**  
  Хостът получава крайния резултат от клиента и го представя на потребителя, често включително както генерирания текст от модела, така и резултатите от изпълнението на инструменти или търсения в ресурси.

Този поток позволява на MCP да поддържа усъвършенствани, интерактивни и контекстуално осъзнати AI приложения чрез безпроблемно свързване на модели с външни инструменти и източници на данни.

## Детайли за протокола

MCP (Model Context Protocol) е изграден върху [JSON-RPC 2.0](https://www.jsonrpc.org/), предоставяйки стандартизиран, езиконезависим формат на съобщения за комуникация между hosts, clients и servers. Тази основа осигурява надеждни, структурирани и разширяеми взаимодействия между различни платформи и програмни езици.

### Ключови характеристики на протокола

MCP разширява JSON-RPC 2.0 с допълнителни конвенции за извикване на инструменти, достъп до ресурси и управление на подсказки. Поддържа множество транспортни слоеве (STDIO, WebSocket, SSE) и позволява сигурна, разширяема и езиконезависима комуникация между компонентите.

#### 🧢 Основен протокол

- **Формат на съобщения JSON-RPC**: Всички заявки и отговори използват спецификацията JSON-RPC 2.0, осигурявайки последователна структура за методови повиквания, параметри, резултати и обработка на грешки.
- **Състояниеви връзки**: MCP сесиите поддържат състояние през множество заявки, поддържайки текущи разговори, акумулиране на контекст и управление на ресурси.
- **Договаряне на възможности**: По време на установяване на връзка клиентите и сървърите обменят информация за поддържаните функции, версии на протокола, налични инструменти и ресурси. Това гарантира, че и двете страни разбират възможностите една на друга и могат да се адаптират.

#### ➕ Допълнителни помощни средства

По-долу са изброени някои допълнителни помощни средства и разширения на протокола, които MCP предоставя за подобряване на разработчиците и позволяване на напреднали сценарии:

- **Опции за конфигурация**: MCP позволява динамична конфигурация на параметрите на сесията, като разрешения за инструменти, достъп до ресурси и настройки на модела, пригодени за всяко взаимодействие.
- **Проследяване на напредъка**: Дълготрайни операции могат да докладват за напредъка си, позволявайки отзивчиви потребителски интерфейси и по-добро потребителско изживяване при сложни задачи.
- **Отмяна на заявки**: Клиентите могат да отменят текущи заявки, позволявайки на потребителите да прекъсват операции, които вече не са необходими или отнемат прекалено много време.
- **Отчитане на грешки**: Стандартизирани съобщения за грешки и кодове помагат за диагностициране на проблеми, обработка на неуспехи по грациозен начин и предоставяне на полезна обратна връзка на потребителите и разработчиците.
- **Логване**: Как клиентите, така и сървърите могат да излъчват структурирани логове за одит, отстраняване на грешки и мониторинг на взаимодействията в протокола.

Чрез използване на тези функции MCP осигурява стабилна, сигурна и гъвкава комуникация между езиковите модели и външни инструменти или източници на данни.

### 🔐 Съображения за сигурността

Имплементациите на MCP трябва да спазват няколко ключови принципа за сигурност, за да гарантират безопасни и надеждни взаимодействия:

- **Съгласие и контрол от потребителя**: Потребителите трябва да дадат изрично съгласие преди достъп до данни или извършване на операции. Те трябва да имат ясен контрол върху това какви данни се споделят и кои действия са разрешени, подкрепени от интуитивни потребителски интерфейси за преглед и одобрение на дейностите.

- **Поверителност на данните**: Данните на потребителите трябва да се разкриват само със съгласието им и да са защитени с подходящи контролни механизми за достъп. Имплементациите на MCP трябва да предпазват от неоторизиран трансфер на данни и да гарантират запазването на поверителността през всички взаимодействия.

- **Безопасност на инструментите**: Преди извикване на инструмент е необходимо изрично съгласие от потребителя. Потребителите трябва да разбират ясно функционалността на всеки инструмент, а сигурни граници трябва да се налагат, за да се предотврати неволно или опасно изпълнение на инструменти.

Следвайки тези принципи, MCP гарантира, че доверието, поверителността и безопасността на потребителите се поддържат във всички взаимодействия по протокола

**Отказ от отговорност**:  
Този документ е преведен с помощта на AI преводаческа услуга [Co-op Translator](https://github.com/Azure/co-op-translator). Въпреки че се стремим към точност, моля, имайте предвид, че автоматизираните преводи могат да съдържат грешки или неточности. Оригиналният документ на неговия език трябва да се счита за авторитетен източник. За критична информация се препоръчва професионален човешки превод. Ние не носим отговорност за недоразумения или погрешни тълкувания, произтичащи от използването на този превод.