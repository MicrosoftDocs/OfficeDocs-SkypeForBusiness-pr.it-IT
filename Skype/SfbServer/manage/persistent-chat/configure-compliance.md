---
title: Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Riepilogo: informazioni su come configurare il servizio di conformità del server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: ee7dbc3ad8e7eedcadcc60850e35b753c5fadb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815066"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ffa21-103">Configurare il servizio di conformità per il server Chat persistente in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ffa21-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>

<span data-ttu-id="ffa21-104">**Riepilogo:** Informazioni su come configurare il servizio di conformità del server Chat persistente in Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffa21-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>

<span data-ttu-id="ffa21-105">La conformità a chat persistente consente agli amministratori di gestire un archivio dei messaggi di Persistent Chat e delle attività.</span><span class="sxs-lookup"><span data-stu-id="ffa21-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="ffa21-106">Il servizio di conformità registra e archivia i dati relativi a ogni conversazione del server Chat persistente, anche quando un partecipante:</span><span class="sxs-lookup"><span data-stu-id="ffa21-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>

- <span data-ttu-id="ffa21-107">Aggiunge una chat room persistente</span><span class="sxs-lookup"><span data-stu-id="ffa21-107">Joins a Persistent Chat room</span></span>

- <span data-ttu-id="ffa21-108">Lascia una chat room</span><span class="sxs-lookup"><span data-stu-id="ffa21-108">Leaves a chat room</span></span>

- <span data-ttu-id="ffa21-109">Invia un messaggio</span><span class="sxs-lookup"><span data-stu-id="ffa21-109">Posts a message</span></span>

- <span data-ttu-id="ffa21-110">Visualizza la cronologia della chat</span><span class="sxs-lookup"><span data-stu-id="ffa21-110">Views chat history</span></span>

- <span data-ttu-id="ffa21-111">Carica un file</span><span class="sxs-lookup"><span data-stu-id="ffa21-111">Uploads a file</span></span>

- <span data-ttu-id="ffa21-112">Scarica un file</span><span class="sxs-lookup"><span data-stu-id="ffa21-112">Downloads a file</span></span>

<span data-ttu-id="ffa21-113">Tali informazioni possono essere recuperate dal database SQL compliance in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ffa21-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 

> [!NOTE]
> <span data-ttu-id="ffa21-114">La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ffa21-114">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ffa21-115">La stessa funzionalità è disponibile in teams.</span><span class="sxs-lookup"><span data-stu-id="ffa21-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="ffa21-116">Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="ffa21-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ffa21-117">Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ffa21-117">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="ffa21-118">Configurare il servizio di conformità tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffa21-118">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="ffa21-119">Dopo che il servizio di conformità è stato abilitato mediante il generatore di topologie, è possibile configurare il servizio utilizzando il cmdlet **set-CsPersistenChatComplianceConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="ffa21-119">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="ffa21-120">o</span><span class="sxs-lookup"><span data-stu-id="ffa21-120">or</span></span>

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="ffa21-121">È possibile impostare i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ffa21-121">You can set the following parameters:</span></span>

- <span data-ttu-id="ffa21-122">AdapterType: consente di specificare il tipo di adattatore.</span><span class="sxs-lookup"><span data-stu-id="ffa21-122">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="ffa21-123">Un adattatore è un prodotto di terze parti che converte i dati nel database di conformità in un formato specifico.</span><span class="sxs-lookup"><span data-stu-id="ffa21-123">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="ffa21-124">XML è il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ffa21-124">XML is the default.</span></span>

- <span data-ttu-id="ffa21-125">OneChatRoomPerOutputFile-questo parametro consente di specificare che i report distinti devono essere creati per ogni chat room.</span><span class="sxs-lookup"><span data-stu-id="ffa21-125">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>

- <span data-ttu-id="ffa21-126">AddChatRoomDetails-se abilitato, questo parametro consente di registrare ulteriori informazioni su ogni chat room nel database.</span><span class="sxs-lookup"><span data-stu-id="ffa21-126">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="ffa21-127">Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ffa21-127">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="ffa21-128">AddUserDetails-se abilitato, questo parametro consente di registrare ulteriori dettagli su ogni utente della chat room nel database.</span><span class="sxs-lookup"><span data-stu-id="ffa21-128">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="ffa21-129">Poiché questa impostazione può aumentare notevolmente le dimensioni del database, è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ffa21-129">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>

- <span data-ttu-id="ffa21-130">Identity-questo parametro consente di applicare le impostazioni di conformità a un determinato insieme, inclusi i livelli globale, del sito e del servizio.</span><span class="sxs-lookup"><span data-stu-id="ffa21-130">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="ffa21-131">Il valore predefinito è il livello globale.</span><span class="sxs-lookup"><span data-stu-id="ffa21-131">The default is the global level.</span></span> 

- <span data-ttu-id="ffa21-132">RunInterval-questo parametro determina la quantità di tempo prima che il server crei il file di output di conformità successivo (il valore predefinito è 15 minuti).</span><span class="sxs-lookup"><span data-stu-id="ffa21-132">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>

## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="ffa21-133">Utilizzare un adattatore di conformità personalizzato</span><span class="sxs-lookup"><span data-stu-id="ffa21-133">Use a customized compliance adapter</span></span>

<span data-ttu-id="ffa21-134">È possibile scrivere un adattatore personalizzato anziché utilizzare XmlAdapter installato con il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-134">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="ffa21-135">A tale scopo, è necessario fornire un assembly .NET Framework che contenga una classe pubblica che implementi l'interfaccia **IComplianceAdapter** .</span><span class="sxs-lookup"><span data-stu-id="ffa21-135">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="ffa21-136">È necessario inserire questo assembly nella cartella di installazione del server Chat persistente di ogni server nel pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-136">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="ffa21-137">Uno qualsiasi dei server di conformità è in grado di fornire i dati di conformità alla scheda, ma i server di conformità non forniranno i dati di conformità duplicati a più istanze della scheda.</span><span class="sxs-lookup"><span data-stu-id="ffa21-137">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>

<span data-ttu-id="ffa21-138">L'interfaccia è definita nell'assembly Compliance.dll nello spazio dei nomi  `Microsoft.Rtc.Internal.Chat.Server.Compliance` .</span><span class="sxs-lookup"><span data-stu-id="ffa21-138">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="ffa21-139">L'interfaccia definisce due metodi che devono essere implementati dall'adattatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ffa21-139">The interface defines two methods that your custom adapter must implement.</span></span>

<span data-ttu-id="ffa21-140">Il server di conformità di Persistent Chat chiamerà il metodo seguente quando l'adattatore viene caricato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="ffa21-140">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="ffa21-141">`AdapterConfig`Contiene la configurazione di conformità di Persistent Chat pertinente per la scheda di conformità:</span><span class="sxs-lookup"><span data-stu-id="ffa21-141">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>

```cpp
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="ffa21-142">Il server di conformità di Persistent Chat chiama il metodo seguente a intervalli periodici finché sono presenti nuovi dati da tradurre.</span><span class="sxs-lookup"><span data-stu-id="ffa21-142">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="ffa21-143">Questo intervallo di tempo è uguale al  `RunInterval` set nella configurazione di conformità di Persistent Chat:</span><span class="sxs-lookup"><span data-stu-id="ffa21-143">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>

```cpp
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="ffa21-144">`ConversationCollection`Contiene le informazioni di conversazione raccolte dall'ultima volta che è stato chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="ffa21-144">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>

## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="ffa21-145">Personalizzare il file di definizione XSLT</span><span class="sxs-lookup"><span data-stu-id="ffa21-145">Customize the XSLT definition file</span></span>

<span data-ttu-id="ffa21-146">I dati di conformità vengono recapitati come XML, che è possibile trasformare nel formato più adatto alla propria organizzazione, utilizzando un file di definizione XSLT.</span><span class="sxs-lookup"><span data-stu-id="ffa21-146">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="ffa21-147">Questo argomento descrive il file XML creato dal servizio di conformità.</span><span class="sxs-lookup"><span data-stu-id="ffa21-147">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="ffa21-148">Sono inoltre disponibili esempi dei file di definizione XSLT e dei file di output.</span><span class="sxs-lookup"><span data-stu-id="ffa21-148">It also provides samples of XSLT definition and output files.</span></span>

### <a name="output-format"></a><span data-ttu-id="ffa21-149">Formato di output</span><span class="sxs-lookup"><span data-stu-id="ffa21-149">Output format</span></span>

<span data-ttu-id="ffa21-150">L'output del servizio di conformità è suddiviso in categorie tramite la conversazione (elemento di conversazione) e quindi in base al messaggio (elemento Messages), come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ffa21-150">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>

```XML
<?xml version="1.0" encoding="utf-8" ?> 
<Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Conversation>
    <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
    <!--FirstMessage goes here --!>
    <Messages> 
      <!—Messages go here--!>
    </Messages>
    <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
  </Conversation>
</Conversations>
```

<span data-ttu-id="ffa21-151">Un elemento Conversation contiene quattro elementi (Channel, FirstMessage, StartTimeUTC e EndTimeUTC).</span><span class="sxs-lookup"><span data-stu-id="ffa21-151">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="ffa21-152">L'elemento Channel contiene l'URI (Uniform Resource Identifier) della chat room e l'elemento FirstMessage descrive il primo messaggio nell'elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="ffa21-152">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="ffa21-153">Gli elementi StartTimeUTC e EndTimeUTC forniscono gli orari di inizio e di fine per la conversazione, come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ffa21-153">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="ffa21-154">Un elemento Messages contiene due elementi (Sender e DateTimeUTC) e tre attributi (Type, Content e ID).</span><span class="sxs-lookup"><span data-stu-id="ffa21-154">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="ffa21-155">L'elemento sender rappresenta l'utente che invia il messaggio e l'elemento DateTimeUTC rappresenta quando si verifica un evento, come illustrato nell'esempio di codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ffa21-155">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="ffa21-156">Nella tabella seguente vengono descritti gli attributi del messaggio Type, Content e ID.</span><span class="sxs-lookup"><span data-stu-id="ffa21-156">The following table describes the message attributes Type, Content, and ID.</span></span>

<span data-ttu-id="ffa21-157">**Attributi dell'elemento Messages**</span><span class="sxs-lookup"><span data-stu-id="ffa21-157">**Messages Element Attributes**</span></span>

|<span data-ttu-id="ffa21-158">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="ffa21-158">**Attribute**</span></span>|<span data-ttu-id="ffa21-159">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ffa21-159">**Description**</span></span>|<span data-ttu-id="ffa21-160">**Facoltativo/obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="ffa21-160">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ffa21-161">Tipo</span><span class="sxs-lookup"><span data-stu-id="ffa21-161">Type</span></span>  <br/> |<span data-ttu-id="ffa21-p114">Specifica il tipo di messaggio. I tipi di messaggio sono descritti nella tabella Tipi di messaggio dell'elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="ffa21-p114">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="ffa21-164">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffa21-164">Required</span></span>  <br/> |
|<span data-ttu-id="ffa21-165">Contenuto</span><span class="sxs-lookup"><span data-stu-id="ffa21-165">Content</span></span>  <br/> |<span data-ttu-id="ffa21-p115">Contenuto del messaggio. Questo attributo non è utilizzato per i messaggi con Type Join o Part.</span><span class="sxs-lookup"><span data-stu-id="ffa21-p115">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="ffa21-168">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="ffa21-168">Optional</span></span>  <br/> |
|<span data-ttu-id="ffa21-169">ID</span><span class="sxs-lookup"><span data-stu-id="ffa21-169">ID</span></span>  <br/> |<span data-ttu-id="ffa21-p116">Specifica l'ID univoco del contenuto. Questo attributo è utilizzato solo con i messaggi con Type Chat.</span><span class="sxs-lookup"><span data-stu-id="ffa21-p116">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="ffa21-172">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="ffa21-172">Optional</span></span>  <br/> |

<span data-ttu-id="ffa21-p117">Ogni elemento Sender contiene cinque attributi, ovvero Username, ID, Email, Internal e Uri. Questi attributi sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-p117">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

<span data-ttu-id="ffa21-175">**Attributi dell'elemento Sender**</span><span class="sxs-lookup"><span data-stu-id="ffa21-175">**Sender Element Attributes**</span></span>

|<span data-ttu-id="ffa21-176">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="ffa21-176">**Attribute**</span></span>|<span data-ttu-id="ffa21-177">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ffa21-177">**Description**</span></span>|<span data-ttu-id="ffa21-178">**Facoltativo/obbligatorio**</span><span class="sxs-lookup"><span data-stu-id="ffa21-178">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ffa21-179">Nome utente</span><span class="sxs-lookup"><span data-stu-id="ffa21-179">Username</span></span>  <br/> |<span data-ttu-id="ffa21-180">Nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-180">The name of the sender.</span></span>  <br/> |<span data-ttu-id="ffa21-181">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="ffa21-181">Optional</span></span>  <br/> |
|<span data-ttu-id="ffa21-182">ID</span><span class="sxs-lookup"><span data-stu-id="ffa21-182">ID</span></span>  <br/> |<span data-ttu-id="ffa21-183">ID univoco del mittente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-183">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="ffa21-184">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffa21-184">Required</span></span>  <br/> |
|<span data-ttu-id="ffa21-185">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ffa21-185">Email</span></span>  <br/> |<span data-ttu-id="ffa21-186">Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-186">The sender's email address.</span></span>  <br/> |<span data-ttu-id="ffa21-187">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="ffa21-187">Optional</span></span>  <br/> |
|<span data-ttu-id="ffa21-188">Interno</span><span class="sxs-lookup"><span data-stu-id="ffa21-188">Internal</span></span>  <br/> |<span data-ttu-id="ffa21-p118">Determina se l'utente è interno o federato. Se il valore è impostato su true, l'utente è interno.</span><span class="sxs-lookup"><span data-stu-id="ffa21-p118">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="ffa21-191">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="ffa21-191">Optional</span></span>  <br/> |
|<span data-ttu-id="ffa21-192">URI</span><span class="sxs-lookup"><span data-stu-id="ffa21-192">Uri</span></span>  <br/> |<span data-ttu-id="ffa21-193">URI SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-193">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="ffa21-194">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="ffa21-194">Required</span></span>  <br/> |

<span data-ttu-id="ffa21-195">Negli esempi seguenti vengono illustrati i tipi di messaggio che possono essere contenuti nell'elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="ffa21-195">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="ffa21-196">Sono inoltre disponibili esempi di utilizzo per ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="ffa21-196">It also provides examples of how each element is used.</span></span>

<span data-ttu-id="ffa21-197">Join-un utente si unisce a una chat room.</span><span class="sxs-lookup"><span data-stu-id="ffa21-197">Join - A user joins a chat room.</span></span>

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="ffa21-198">Parte-un utente lascia una chat room.</span><span class="sxs-lookup"><span data-stu-id="ffa21-198">Part - A user leaves a chat room.</span></span>

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="ffa21-199">Chat: l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="ffa21-199">Chat - The sender's email address.</span></span>

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="ffa21-200">Backchat-un utente richiede contenuto dalla cronologia chat.</span><span class="sxs-lookup"><span data-stu-id="ffa21-200">Backchat - A user requests content from chat history.</span></span>

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="ffa21-201">Caricamento file-un utente carica un file.</span><span class="sxs-lookup"><span data-stu-id="ffa21-201">File upload - A user uploads a file.</span></span>

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="ffa21-202">Download di file-un utente scarica un file.</span><span class="sxs-lookup"><span data-stu-id="ffa21-202">File download - A user downloads a file.</span></span>

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="ffa21-203">XSD di output predefinito di chat persistente e trasformazione XSL di esempio</span><span class="sxs-lookup"><span data-stu-id="ffa21-203">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="ffa21-204">Nell'esempio di codice seguente è incluso l'output predefinito del server Compliance:</span><span class="sxs-lookup"><span data-stu-id="ffa21-204">The following code sample contains the default output from the Compliance Server:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
   <xs:simpleType name="ComplianceMessageType">
      <xs:restriction base="xs:string">
        <xs:enumeration value="JOIN"/>
        <xs:enumeration value="PART"/>
        <xs:enumeration value="CHAT"/>
        <xs:enumeration value="BACKCHAT"/>
        <xs:enumeration value="FILEUPLOAD"/>
        <xs:enumeration value="FILEDOWNLOAD"/>
      </xs:restriction>
    </xs:simpleType>

  <xs:element name="Sender">
    <xs:complexType>
      <xs:attribute name="UserName" type="xs:string" />
      <xs:attribute name="id" type="xs:int" />
      <xs:attribute name="email" type="xs:string" use="optional" />
      <xs:attribute name="internal" type="xs:boolean" use="optional" >
        <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
      </xs:attribute>
      <xs:attribute name="uri" type="xs:anyURI" use="optional" />
    </xs:complexType>
  </xs:element>
  <xs:element name="DateTimeUTC">
    <xs:complexType>
      <xs:attribute name="since1970" type="xs:long" />
      <xs:attribute name="string" type="xs:string" />
      <xs:attribute name="long" type="xs:long" />
    </xs:complexType>
  </xs:element>
  <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
    <xs:complexType>
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element ref="Sender" />
        <xs:element ref="DateTimeUTC" />
        <xs:element name="Conversation">
          <xs:complexType>
            <xs:sequence>
              <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="uri" type="xs:anyURI" />
                  <xs:attribute name="name" type="xs:string" use="optional" />
                </xs:complexType>
              </xs:element>
              <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                    <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                  </xs:sequence>
                  <xs:attribute name="type" type="ComplianceMessageType" />
                  <xs:attribute name="content" type="xs:string" />
                  <xs:attribute name="id" type="xs:int" />
                </xs:complexType>
              </xs:element>
              <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:sequence>
                    <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                      <xs:complexType>
                        <xs:sequence>
                          <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                          <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                        </xs:sequence>
                        <xs:attribute name="type" type="ComplianceMessageType" />
                        <xs:attribute name="content" type="xs:string" />
                        <xs:attribute name="id" type="xs:int" />
                      </xs:complexType>
                    </xs:element>
                  </xs:sequence>
                </xs:complexType>
              </xs:element>
              <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
              <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                  <xs:attribute name="since1970" type="xs:long" />
                  <xs:attribute name="string" type="xs:string" />
                  <xs:attribute name="long" type="xs:long" />
                </xs:complexType>
              </xs:element>
            </xs:sequence>
          </xs:complexType>
        </xs:element>
      </xs:choice>
    </xs:complexType>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="ffa21-205">Nell'esempio di codice seguente è inclusa una trasformazione XSL di esempio:</span><span class="sxs-lookup"><span data-stu-id="ffa21-205">The following code sample contains a sample XSL transform:</span></span>

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
   <xsl:output method="xml" encoding="UTF-8" indent="yes" />

   <xsl:template match="/">
      <FileDump>
         <xsl:apply-templates />
      </FileDump>
   </xsl:template>

   <xsl:template match="Conversation">
      <xsl:variable name="chanName" select="Channel/@name" />
      <Conversation Perspective="{$chanName}_group_channel">
         <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
         <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
         <xsl:apply-templates />
         <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
      </Conversation>
   </xsl:template>

   <xsl:template match="Message">
      <xsl:choose>
         <xsl:when test="@type='JOIN'">
            <ParticipantEntered>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantEntered>
         </xsl:when>

         <xsl:when test="@type='PART'">
            <ParticipantLeft>
               <xsl:call-template name="DateTimeAndLogin" />
               <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
               <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
               <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
            </ParticipantLeft>
         </xsl:when>

         <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
            <FileTransferStarted>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
            </FileTransferStarted>
            <FileTransferEnded>
               <xsl:call-template name="DateTimeAndLogin" />
               <FileName><xsl:value-of select="@content" /></FileName>
               <Status>Completed</Status>
            </FileTransferEnded>
         </xsl:when>

         <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
            <Message>
               <xsl:call-template name="DateTimeAndLogin" />
               <Content><xsl:value-of select="@content" /></Content>
            </Message>
         </xsl:when>

         <xsl:otherwise />
      </xsl:choose>
   </xsl:template>

   <xsl:template name="DateTimeAndLogin">
      <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
      <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
   </xsl:template>
</xsl:stylesheet>
```
