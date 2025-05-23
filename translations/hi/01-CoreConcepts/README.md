<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "788eb17750e970a0bc3b5e7f2e99975b",
  "translation_date": "2025-05-18T15:04:17+00:00",
  "source_file": "01-CoreConcepts/README.md",
  "language_code": "hi"
}
-->
# 📖 MCP कोर अवधारणाएँ: AI इंटीग्रेशन के लिए मॉडल कॉन्टेक्स्ट प्रोटोकॉल में महारत हासिल करना

मॉडल कॉन्टेक्स्ट प्रोटोकॉल (MCP) एक शक्तिशाली, मानकीकृत फ्रेमवर्क है जो बड़े भाषा मॉडलों (LLMs) और बाहरी टूल्स, एप्लिकेशन, और डेटा स्रोतों के बीच संचार को अनुकूलित करता है। यह SEO-अनुकूलित गाइड आपको MCP के मूलभूत सिद्धांतों से परिचित कराएगा, जिससे आप इसके क्लाइंट-सर्वर आर्किटेक्चर, आवश्यक घटकों, संचार तंत्र, और कार्यान्वयन की सर्वोत्तम प्रथाओं को समझ सकेंगे।

## अवलोकन

यह पाठ MCP पारिस्थितिकी तंत्र की मूलभूत संरचना और घटकों की पड़ताल करता है। आप क्लाइंट-सर्वर आर्किटेक्चर, मुख्य घटक, और संचार तंत्र के बारे में जानेंगे जो MCP इंटरैक्शन को संचालित करते हैं।

## 👩‍🎓 मुख्य सीखने के उद्देश्य

इस पाठ के अंत तक, आप:

- MCP क्लाइंट-सर्वर आर्किटेक्चर को समझेंगे।
- Hosts, Clients, और Servers की भूमिकाओं और जिम्मेदारियों की पहचान करेंगे।
- MCP को एक लचीले इंटीग्रेशन लेयर बनाने वाली मुख्य विशेषताओं का विश्लेषण करेंगे।
- MCP पारिस्थितिकी तंत्र में सूचना प्रवाह को समझेंगे।
- .NET, Java, Python, और JavaScript में कोड उदाहरणों के माध्यम से व्यावहारिक ज्ञान प्राप्त करेंगे।

## 🔎 MCP आर्किटेक्चर: एक गहन दृष्टि

MCP पारिस्थितिकी तंत्र क्लाइंट-सर्वर मॉडल पर आधारित है। यह मॉड्यूलर संरचना AI एप्लिकेशन को टूल्स, डेटाबेस, APIs, और संदर्भ संसाधनों के साथ कुशलता से संवाद करने की अनुमति देती है। आइए इस आर्किटेक्चर को इसके मुख्य घटकों में विभाजित करें।

### 1. Hosts

मॉडल कॉन्टेक्स्ट प्रोटोकॉल (MCP) में, Hosts एक महत्वपूर्ण भूमिका निभाते हैं क्योंकि ये प्राथमिक इंटरफेस होते हैं जिनके माध्यम से उपयोगकर्ता प्रोटोकॉल के साथ इंटरैक्ट करते हैं। Hosts वे एप्लिकेशन या वातावरण होते हैं जो MCP सर्वरों के साथ कनेक्शन शुरू करते हैं ताकि डेटा, टूल्स, और प्रॉम्प्ट्स तक पहुँच सकें। Hosts के उदाहरणों में Visual Studio Code जैसे इंटीग्रेटेड डेवलपमेंट एनवायरनमेंट (IDEs), Claude Desktop जैसे AI टूल्स, या विशिष्ट कार्यों के लिए बनाए गए कस्टम एजेंट शामिल हैं।

**Hosts** वे LLM एप्लिकेशन होते हैं जो कनेक्शन शुरू करते हैं। वे:

- AI मॉडल्स के साथ इंटरैक्ट या निष्पादित करके प्रतिक्रियाएँ उत्पन्न करते हैं।
- MCP सर्वरों के साथ कनेक्शन शुरू करते हैं।
- बातचीत के प्रवाह और उपयोगकर्ता इंटरफेस का प्रबंधन करते हैं।
- अनुमति और सुरक्षा प्रतिबंधों को नियंत्रित करते हैं।
- डेटा साझा करने और टूल निष्पादन के लिए उपयोगकर्ता की सहमति संभालते हैं।

### 2. Clients

Clients ऐसे आवश्यक घटक हैं जो Hosts और MCP सर्वरों के बीच इंटरैक्शन को सक्षम बनाते हैं। Clients मध्यस्थ के रूप में कार्य करते हैं, जिससे Hosts MCP सर्वरों द्वारा प्रदान की गई कार्यक्षमताओं का उपयोग कर पाते हैं। वे MCP आर्किटेक्चर के भीतर सुचारू संचार और कुशल डेटा विनिमय सुनिश्चित करने में महत्वपूर्ण भूमिका निभाते हैं।

**Clients** होस्ट एप्लिकेशन के भीतर कनेक्टर्स होते हैं। वे:

- प्रॉम्प्ट्स/निर्देशों के साथ सर्वरों को अनुरोध भेजते हैं।
- सर्वरों के साथ क्षमताओं पर बातचीत करते हैं।
- मॉडलों से टूल निष्पादन अनुरोधों का प्रबंधन करते हैं।
- उपयोगकर्ताओं को प्रतिक्रियाएँ संसाधित करके दिखाते हैं।

### 3. Servers

Servers MCP क्लाइंट्स से अनुरोधों को संभालने और उपयुक्त प्रतिक्रियाएँ प्रदान करने के लिए जिम्मेदार होते हैं। वे डेटा पुनः प्राप्ति, टूल निष्पादन, और प्रॉम्प्ट जनरेशन जैसी विभिन्न प्रक्रियाओं का प्रबंधन करते हैं। Servers सुनिश्चित करते हैं कि क्लाइंट्स और Hosts के बीच संचार प्रभावी और विश्वसनीय हो, जिससे इंटरैक्शन प्रक्रिया की अखंडता बनी रहे।

**Servers** वे सेवाएँ हैं जो संदर्भ और क्षमताएँ प्रदान करती हैं। वे:

- उपलब्ध फीचर्स (संसाधन, प्रॉम्प्ट, टूल्स) का पंजीकरण करते हैं।
- क्लाइंट से टूल कॉल प्राप्त करते हैं और निष्पादित करते हैं।
- मॉडल प्रतिक्रियाओं को बेहतर बनाने के लिए संदर्भ जानकारी प्रदान करते हैं।
- आउटपुट क्लाइंट को वापस भेजते हैं।
- आवश्यकतानुसार इंटरैक्शन के दौरान स्थिति बनाए रखते हैं।

Servers किसी भी व्यक्ति द्वारा विकसित किए जा सकते हैं ताकि मॉडल क्षमताओं को विशेष कार्यक्षमता के साथ बढ़ाया जा सके।

### 4. Server Features

MCP में Servers ऐसे बुनियादी घटक प्रदान करते हैं जो क्लाइंट्स, Hosts, और भाषा मॉडलों के बीच समृद्ध इंटरैक्शन को सक्षम बनाते हैं। ये फीचर्स MCP की क्षमताओं को संरचित संदर्भ, टूल्स, और प्रॉम्प्ट्स प्रदान करके बढ़ाते हैं।

MCP सर्वर निम्नलिखित में से कोई भी फीचर प्रदान कर सकते हैं:

#### 📑 Resources

MCP में Resources विभिन्न प्रकार के संदर्भ और डेटा होते हैं जिन्हें उपयोगकर्ता या AI मॉडल उपयोग कर सकते हैं। इनमें शामिल हैं:

- **संदर्भात्मक डेटा**: जानकारी और संदर्भ जिसे उपयोगकर्ता या AI मॉडल निर्णय लेने और कार्य निष्पादन के लिए उपयोग कर सकते हैं।
- **ज्ञान आधार और दस्तावेज़ संग्रह**: संरचित और असंरचित डेटा का संग्रह, जैसे लेख, मैनुअल, और शोध पत्र, जो मूल्यवान अंतर्दृष्टि और जानकारी प्रदान करते हैं।
- **स्थानीय फाइलें और डेटाबेस**: डिवाइस पर या डेटाबेस में स्थानीय रूप से संग्रहीत डेटा, जिसे प्रोसेसिंग और विश्लेषण के लिए एक्सेस किया जा सकता है।
- **APIs और वेब सेवाएं**: बाहरी इंटरफेस और सेवाएं जो अतिरिक्त डेटा और कार्यक्षमता प्रदान करती हैं, जिससे विभिन्न ऑनलाइन संसाधनों और टूल्स के साथ इंटीग्रेशन संभव होता है।

एक संसाधन का उदाहरण हो सकता है कोई डेटाबेस स्कीमा या फाइल जिसे इस तरह एक्सेस किया जा सकता है:

```text
file://log.txt
database://schema
```

### 🤖 Prompts

MCP में Prompts विभिन्न पूर्व-परिभाषित टेम्प्लेट और इंटरैक्शन पैटर्न होते हैं जो उपयोगकर्ता के वर्कफ़्लो को सरल बनाने और संचार को बेहतर बनाने के लिए डिज़ाइन किए गए हैं। इनमें शामिल हैं:

- **टेम्प्लेटेड संदेश और वर्कफ़्लो**: पूर्व-निर्मित संदेश और प्रक्रियाएँ जो उपयोगकर्ताओं को विशिष्ट कार्यों और इंटरैक्शन के माध्यम से मार्गदर्शन करती हैं।
- **पूर्व-परिभाषित इंटरैक्शन पैटर्न**: मानकीकृत क्रियाओं और प्रतिक्रियाओं के अनुक्रम जो सुसंगत और प्रभावी संचार को सक्षम बनाते हैं।
- **विशेषीकृत बातचीत टेम्प्लेट**: विशिष्ट प्रकार की बातचीत के लिए अनुकूलित टेम्प्लेट, जो प्रासंगिक और संदर्भानुकूल इंटरैक्शन सुनिश्चित करते हैं।

एक प्रॉम्प्ट टेम्प्लेट इस प्रकार दिख सकता है:

```markdown
Generate a product slogan based on the following {{product}} with the following {{keywords}}
```

#### ⛏️ Tools

MCP में Tools वे फ़ंक्शंस होते हैं जिन्हें AI मॉडल विशिष्ट कार्य करने के लिए निष्पादित कर सकता है। ये टूल AI मॉडल की क्षमताओं को बढ़ाने के लिए संरचित और विश्वसनीय ऑपरेशन प्रदान करते हैं। मुख्य पहलू हैं:

- **AI मॉडल के लिए निष्पादित करने योग्य फ़ंक्शन**: टूल्स निष्पादित होने वाले फ़ंक्शन होते हैं जिन्हें AI मॉडल विभिन्न कार्यों को पूरा करने के लिए कॉल कर सकता है।
- **विशिष्ट नाम और विवरण**: प्रत्येक टूल का एक अलग नाम और विस्तृत विवरण होता है जो उसके उद्देश्य और कार्यक्षमता को समझाता है।
- **पैरामीटर और आउटपुट**: टूल विशिष्ट पैरामीटर स्वीकार करते हैं और संरचित आउटपुट लौटाते हैं, जिससे परिणाम सुसंगत और पूर्वानुमानित होते हैं।
- **स्वतंत्र फ़ंक्शन**: टूल्स वेब खोज, गणना, और डेटाबेस क्वेरी जैसे अलग-अलग कार्य करते हैं।

एक उदाहरण टूल इस तरह दिख सकता है:

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

MCP में क्लाइंट्स सर्वरों को कई महत्वपूर्ण फीचर्स प्रदान करते हैं, जो प्रोटोकॉल के भीतर समग्र कार्यक्षमता और इंटरैक्शन को बढ़ाते हैं। इनमें से एक प्रमुख फीचर Sampling है।

### 👉 Sampling

- **सर्वर-प्रारंभित एजेंटिक व्यवहार**: क्लाइंट्स सर्वरों को स्वायत्त रूप से विशिष्ट क्रियाएँ या व्यवहार शुरू करने की अनुमति देते हैं, जिससे सिस्टम की गतिशील क्षमताएँ बढ़ती हैं।
- **पुनरावर्ती LLM इंटरैक्शन**: यह फीचर बड़े भाषा मॉडलों (LLMs) के साथ पुनरावर्ती इंटरैक्शन की अनुमति देता है, जिससे जटिल और पुनरावृत्त कार्यों की प्रक्रिया संभव होती है।
- **अतिरिक्त मॉडल पूर्णता का अनुरोध**: सर्वर मॉडल से अतिरिक्त पूर्णताएँ मांग सकते हैं, यह सुनिश्चित करते हुए कि प्रतिक्रियाएँ व्यापक और संदर्भानुकूल हों।

## MCP में सूचना प्रवाह

MCP एक संरचित सूचना प्रवाह परिभाषित करता है जो Hosts, Clients, Servers, और Models के बीच होता है। इस प्रवाह को समझना यह स्पष्ट करता है कि उपयोगकर्ता अनुरोध कैसे संसाधित होते हैं और बाहरी टूल्स और डेटा मॉडल प्रतिक्रियाओं में कैसे एकीकृत होते हैं।

- **Host कनेक्शन शुरू करता है**  
  Host एप्लिकेशन (जैसे IDE या चैट इंटरफेस) आमतौर पर STDIO, WebSocket, या अन्य समर्थित ट्रांसपोर्ट के माध्यम से MCP सर्वर से कनेक्शन स्थापित करता है।

- **क्षमता बातचीत**  
  क्लाइंट (जो होस्ट में एम्बेडेड होता है) और सर्वर अपने समर्थित फीचर्स, टूल्स, संसाधन, और प्रोटोकॉल संस्करणों के बारे में जानकारी साझा करते हैं। इससे दोनों पक्ष सत्र के लिए उपलब्ध क्षमताओं को समझते हैं।

- **उपयोगकर्ता अनुरोध**  
  उपयोगकर्ता होस्ट के साथ इंटरैक्ट करता है (जैसे प्रॉम्प्ट या कमांड दर्ज करता है)। होस्ट इस इनपुट को एकत्र करता है और क्लाइंट को प्रसंस्करण के लिए भेजता है।

- **संसाधन या टूल का उपयोग**  
  - क्लाइंट सर्वर से अतिरिक्त संदर्भ या संसाधन (जैसे फाइलें, डेटाबेस एंट्री, या ज्ञान आधार लेख) का अनुरोध कर सकता है ताकि मॉडल की समझ समृद्ध हो सके।  
  - यदि मॉडल को लगता है कि टूल की आवश्यकता है (जैसे डेटा प्राप्त करना, गणना करना, या API कॉल करना), तो क्लाइंट टूल नाम और पैरामीटर निर्दिष्ट करते हुए टूल इनवोकेशन अनुरोध सर्वर को भेजता है।

- **सर्वर निष्पादन**  
  सर्वर संसाधन या टूल अनुरोध प्राप्त करता है, आवश्यक ऑपरेशन करता है (जैसे फ़ंक्शन चलाना, डेटाबेस क्वेरी करना, या फाइल पुनः प्राप्त करना), और परिणामों को संरचित रूप में क्लाइंट को वापस भेजता है।

- **प्रतिक्रिया निर्माण**  
  क्लाइंट सर्वर की प्रतिक्रियाओं (संसाधन डेटा, टूल आउटपुट आदि) को मौजूदा मॉडल इंटरैक्शन में एकीकृत करता है। मॉडल इस जानकारी का उपयोग एक व्यापक और संदर्भानुकूल प्रतिक्रिया उत्पन्न करने के लिए करता है।

- **परिणाम प्रस्तुति**  
  होस्ट अंतिम आउटपुट क्लाइंट से प्राप्त करता है और उपयोगकर्ता को प्रस्तुत करता है, जिसमें अक्सर मॉडल द्वारा उत्पन्न पाठ और टूल निष्पादन या संसाधन खोज के परिणाम शामिल होते हैं।

यह प्रवाह MCP को उन्नत, इंटरैक्टिव, और संदर्भ-सचेत AI एप्लिकेशन का समर्थन करने में सक्षम बनाता है, जिससे मॉडल्स को बाहरी टूल्स और डेटा स्रोतों से सहजता से जोड़ा जा सकता है।

## प्रोटोकॉल विवरण

MCP [JSON-RPC 2.0](https://www.jsonrpc.org/) के ऊपर बनाया गया है, जो Hosts, Clients, और Servers के बीच संचार के लिए एक मानकीकृत, भाषा-agnostic संदेश प्रारूप प्रदान करता है। यह आधार विभिन्न प्लेटफार्मों और प्रोग्रामिंग भाषाओं में विश्वसनीय, संरचित, और विस्तारित इंटरैक्शन सक्षम बनाता है।

### प्रमुख प्रोटोकॉल फीचर्स

MCP JSON-RPC 2.0 को टूल इनवोकेशन, संसाधन एक्सेस, और प्रॉम्प्ट प्रबंधन के लिए अतिरिक्त कन्वेंशंस के साथ बढ़ाता है। यह कई ट्रांसपोर्ट लेयर्स (STDIO, WebSocket, SSE) का समर्थन करता है और घटकों के बीच सुरक्षित, विस्तारित, और भाषा-agnostic संचार सक्षम बनाता है।

#### 🧢 बेस प्रोटोकॉल

- **JSON-RPC संदेश प्रारूप**: सभी अनुरोध और प्रतिक्रियाएँ JSON-RPC 2.0 विनिर्देश का उपयोग करती हैं, जिससे मेथड कॉल, पैरामीटर, परिणाम, और त्रुटि प्रबंधन के लिए सुसंगत संरचना सुनिश्चित होती है।
- **स्टेटफुल कनेक्शन**: MCP सत्र कई अनुरोधों में स्थिति बनाए रखते हैं, जिससे निरंतर बातचीत, संदर्भ संचय, और संसाधन प्रबंधन संभव होता है।
- **क्षमता बातचीत**: कनेक्शन सेटअप के दौरान, क्लाइंट और सर्वर समर्थित फीचर्स, प्रोटोकॉल संस्करण, उपलब्ध टूल्स, और संसाधनों के बारे में जानकारी साझा करते हैं। यह सुनिश्चित करता है कि दोनों पक्ष एक-दूसरे की क्षमताओं को समझें और तदनुसार अनुकूलित हों।

#### ➕ अतिरिक्त यूटिलिटीज़

नीचे कुछ अतिरिक्त यूटिलिटीज़ और प्रोटोकॉल एक्सटेंशंस हैं जो MCP डेवलपर अनुभव को बेहतर बनाने और उन्नत परिदृश्यों को सक्षम करने के लिए प्रदान करता है:

- **कॉन्फ़िगरेशन विकल्प**: MCP सत्र पैरामीटर जैसे टूल अनुमतियाँ, संसाधन एक्सेस, और मॉडल सेटिंग्स को गतिशील रूप से कॉन्फ़िगर करने की अनुमति देता है, जो प्रत्येक इंटरैक्शन के लिए अनुकूलित होते हैं।
- **प्रगति ट्रैकिंग**: लंबी चलने वाली प्रक्रियाएँ प्रगति अपडेट रिपोर्ट कर सकती हैं, जिससे जटिल कार्यों के दौरान उत्तरदायी उपयोगकर्ता इंटरफेस और बेहतर अनुभव मिलता है।
- **अनुरोध रद्द करना**: क्लाइंट इन-फ्लाइट अनुरोधों को रद्द कर सकते हैं, जिससे उपयोगकर्ता उन ऑपरेशनों को रोक सकते हैं जो अब आवश्यक नहीं हैं या बहुत समय ले रहे हैं।
- **त्रुटि रिपोर्टिंग**: मानकीकृत त्रुटि संदेश और कोड समस्याओं का निदान करने, विफलताओं को सहजता से संभालने, और उपयोगकर्ताओं तथा डेवलपर्स को क्रियाशील प्रतिक्रिया प्रदान करने में मदद करते हैं।
- **लॉगिंग**: क्लाइंट और सर्वर दोनों ऑडिटिंग, डिबगिंग, और प्रोटोकॉल इंटरैक्शन की निगरानी के लिए संरचित लॉग जारी कर सकते हैं।

इन प्रोटोकॉल फीचर्स का उपयोग करके, MCP भाषा मॉडलों और बाहरी टूल्स या डेटा स्रोतों के बीच मजबूत, सुरक्षित, और लचीले संचार को सुनिश्चित करता है।

### 🔐 सुरक्षा विचार

MCP इम्प्लीमेंटेशन को सुरक्षित और विश्वसनीय इंटरैक्शन सुनिश्चित करने के लिए कई प्रमुख सुरक्षा सिद्धांतों का पालन करना चाहिए:

- **उपयोगकर्ता सहमति और नियंत्रण**: किसी भी डेटा एक्सेस या ऑपरेशन से पहले उपयोगकर्ताओं से स्पष्ट सहमति आवश्यक है। उन्हें यह स्पष्ट नियंत्रण होना चाहिए कि कौन सा डेटा साझा किया जा रहा है और कौन से क्रियाकलाप अधिकृत हैं, साथ ही गतिविधियों की समीक्षा और अनुमोदन के लिए सहज उपयोगकर्ता इंटरफेस प्रदान किए जाने चाहिए।

- **डेटा गोपनीयता**: उपयोगकर्ता डेटा केवल स्पष्ट सहमति के साथ ही एक्सपोज़ किया जाना चाहिए और उपयुक्त एक्सेस नियंत्रण द्वारा सुरक्षित रहना चाहिए। MCP इम्प्लीमेंटेशन अनधिकृत डेटा ट्रांसमिशन से बचाव करें और सभी इंटरैक्शन के दौरान गोपनीयता बनाए रखें।

- **टूल सुरक्षा**: किसी भी टूल को कॉल करने से पहले स्पष्ट उपयोगकर्ता सहमति आवश्यक है। उपयोगकर्ताओं को प्रत्येक टूल की कार्यक्षमता की स्पष्ट समझ होनी चाहिए, और अनचाहे या असुरक्षित टूल निष्पादन को रोकने के लिए मजबूत सुरक्षा सीमाएं लागू होनी चाहिए।

इन सिद्धांतों का पालन करके, MCP उपयोगकर्ता विश्वास, गोपनीयता, और सुरक्षा को सभी प्रोटोकॉल इंटरैक्शन में बनाए रखता है।

## कोड उदाहरण: मुख्य घटक

नीचे कुछ लोकप्रिय प्रोग्रामिंग भाषाओं में कोड उदाहरण दिए गए हैं जो MCP सर्वर के मुख्य घटकों और टूल्स को लागू करने के तरीके को दर्शाते हैं।

### .NET उदाहरण: टूल्स के साथ सरल MCP सर्वर बनाना

यह एक व्यावहारिक .NET कोड उदाहरण है जो दिखाता है कि कैसे एक सरल MCP सर्वर को कस्टम टूल्स के साथ बनाया जा सकता है। यह उदाहरण टूल्स को परिभाषित और पंजीकृत करने, अनुरोधों को संभालने, और Model Context Protocol के साथ सर्वर को कनेक्ट करने का तरीका दिखाता है।

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

### Java उदाहरण: MCP सर्वर घटक

यह उदाहरण ऊपर दिए गए .NET उदाहरण के समान MCP सर्वर और टूल पंजीकरण को दर्शाता है, लेकिन इसे Java में लागू किया गया है।

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

### Python उदाहरण: MCP सर्वर बनाना

इस उदाहरण में हम दिखाते

**अस्वीकरण**:  
इस दस्तावेज़ का अनुवाद AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) का उपयोग करके किया गया है। जबकि हम सटीकता के लिए प्रयासरत हैं, कृपया ध्यान दें कि स्वचालित अनुवादों में त्रुटियाँ या असंगतियाँ हो सकती हैं। मूल दस्तावेज़ अपनी मूल भाषा में ही आधिकारिक स्रोत माना जाना चाहिए। महत्वपूर्ण जानकारी के लिए, पेशेवर मानव अनुवाद की सलाह दी जाती है। इस अनुवाद के उपयोग से उत्पन्न किसी भी गलतफहमी या गलत व्याख्या के लिए हम जिम्मेदार नहीं हैं।