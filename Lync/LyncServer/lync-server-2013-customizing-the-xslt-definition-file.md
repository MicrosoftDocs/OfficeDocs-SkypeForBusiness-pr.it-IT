---
title: 'Lync Server 2013: personalizzazione del file di definizione XSLT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf2ab41ed1d9a57f3a3ad5e55e78f46055fc8e87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="8ba14-102">Personalizzazione del file di definizione XSLT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba14-102">Customizing the XSLT definition file in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ba14-103">_**Argomento Ultima modifica:** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="8ba14-103">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="8ba14-104">Il servizio di conformità registra e archivia i dati relativi a ogni conversazione di Lync Server 2013 e persistente del server di chat, anche quando un partecipante:</span><span class="sxs-lookup"><span data-stu-id="8ba14-104">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="8ba14-105">Si unisce a una chat room persistente</span><span class="sxs-lookup"><span data-stu-id="8ba14-105">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="8ba14-106">Lascia una chat room</span><span class="sxs-lookup"><span data-stu-id="8ba14-106">Leaves a chat room</span></span>

  - <span data-ttu-id="8ba14-107">Pubblica un messaggio</span><span class="sxs-lookup"><span data-stu-id="8ba14-107">Posts a message</span></span>

  - <span data-ttu-id="8ba14-108">Cronologia chat visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="8ba14-108">Views chat history</span></span>

  - <span data-ttu-id="8ba14-109">Carica un file</span><span class="sxs-lookup"><span data-stu-id="8ba14-109">Uploads a file</span></span>

  - <span data-ttu-id="8ba14-110">Download di un file</span><span class="sxs-lookup"><span data-stu-id="8ba14-110">Downloads a file</span></span>

<span data-ttu-id="8ba14-111">I dati vengono recapitati come XML, che è possibile trasformare nel formato più adatto alla propria organizzazione, usando un file di definizione XSLT.</span><span class="sxs-lookup"><span data-stu-id="8ba14-111">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file.</span></span> <span data-ttu-id="8ba14-112">Questo argomento descrive il file XML creato dal servizio conformità.</span><span class="sxs-lookup"><span data-stu-id="8ba14-112">This topic describes the XML file that the Compliance service creates.</span></span> <span data-ttu-id="8ba14-113">Vengono inoltre forniti esempi di file di definizione e di output XSLT.</span><span class="sxs-lookup"><span data-stu-id="8ba14-113">It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="8ba14-114">Formato di output</span><span class="sxs-lookup"><span data-stu-id="8ba14-114">Output Format</span></span>

<span data-ttu-id="8ba14-115">L'output del servizio di conformità è categorizzato per conversazione (l'elemento di conversazione) e quindi per messaggio (elemento Messages), come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-115">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

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

<span data-ttu-id="8ba14-116">Un elemento Conversation contiene quattro elementi (Channel, FirstMessage, StartTimeUTC e EndTimeUTC).</span><span class="sxs-lookup"><span data-stu-id="8ba14-116">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC).</span></span> <span data-ttu-id="8ba14-117">L'elemento Channel contiene l'URI (Uniform Resource Identifier) della chat room e l'elemento FirstMessage descrive il primo messaggio nell'elemento Messages.</span><span class="sxs-lookup"><span data-stu-id="8ba14-117">The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element.</span></span> <span data-ttu-id="8ba14-118">Gli elementi StartTimeUTC e EndTimeUTC consentono gli orari di inizio e di fine della conversazione, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-118">The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="8ba14-119">Un elemento Message contiene due elementi (sender e DateTimeUTC) e tre attributi (Type, Content e ID).</span><span class="sxs-lookup"><span data-stu-id="8ba14-119">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID).</span></span> <span data-ttu-id="8ba14-120">L'elemento sender rappresenta l'utente che invia il messaggio e l'elemento DateTimeUTC rappresenta quando si verifica un evento, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-120">The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="8ba14-121">La tabella seguente descrive il tipo di attributi del messaggio, il contenuto e l'ID.</span><span class="sxs-lookup"><span data-stu-id="8ba14-121">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="8ba14-122">Attributi degli elementi messages</span><span class="sxs-lookup"><span data-stu-id="8ba14-122">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ba14-123">Attributo</span><span class="sxs-lookup"><span data-stu-id="8ba14-123">Attribute</span></span></th>
<th><span data-ttu-id="8ba14-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba14-124">Description</span></span></th>
<th><span data-ttu-id="8ba14-125">Facoltativo/obbligatorio</span><span class="sxs-lookup"><span data-stu-id="8ba14-125">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="8ba14-126">Type</span></span></p></td>
<td><p><span data-ttu-id="8ba14-127">Specifica il tipo di messaggio.</span><span class="sxs-lookup"><span data-stu-id="8ba14-127">Specifies the message type.</span></span> <span data-ttu-id="8ba14-128">I tipi di messaggio sono descritti nella tabella tipi di messaggi degli elementi del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8ba14-128">The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-129">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="8ba14-129">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-130">Contenuto</span><span class="sxs-lookup"><span data-stu-id="8ba14-130">Content</span></span></p></td>
<td><p><span data-ttu-id="8ba14-131">Contiene il contenuto del messaggio.</span><span class="sxs-lookup"><span data-stu-id="8ba14-131">Contains the content of the message.</span></span> <span data-ttu-id="8ba14-132">I messaggi con un tipo di join o parte non usano questo attributo.</span><span class="sxs-lookup"><span data-stu-id="8ba14-132">Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-133">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="8ba14-133">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-134">ID</span><span class="sxs-lookup"><span data-stu-id="8ba14-134">ID</span></span></p></td>
<td><p><span data-ttu-id="8ba14-135">Specifica l'ID univoco del contenuto.</span><span class="sxs-lookup"><span data-stu-id="8ba14-135">Specifies the unique ID of the content.</span></span> <span data-ttu-id="8ba14-136">Questo attributo viene usato solo con i messaggi con un tipo di chat.</span><span class="sxs-lookup"><span data-stu-id="8ba14-136">This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-137">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="8ba14-137">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8ba14-138">Ogni elemento sender contiene cinque attributi: il nome utente, l'ID, la posta elettronica, l'interno e l'URI.</span><span class="sxs-lookup"><span data-stu-id="8ba14-138">Each Sender element contains five attributes: the user name, ID, email, internal, and URI.</span></span> <span data-ttu-id="8ba14-139">Questi attributi sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-139">These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="8ba14-140">Attributi degli elementi mittente</span><span class="sxs-lookup"><span data-stu-id="8ba14-140">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ba14-141">Attributo</span><span class="sxs-lookup"><span data-stu-id="8ba14-141">Attribute</span></span></th>
<th><span data-ttu-id="8ba14-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba14-142">Description</span></span></th>
<th><span data-ttu-id="8ba14-143">Facoltativo/obbligatorio</span><span class="sxs-lookup"><span data-stu-id="8ba14-143">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-144">Username</span><span class="sxs-lookup"><span data-stu-id="8ba14-144">Username</span></span></p></td>
<td><p><span data-ttu-id="8ba14-145">Nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-145">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-146">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="8ba14-146">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-147">ID</span><span class="sxs-lookup"><span data-stu-id="8ba14-147">ID</span></span></p></td>
<td><p><span data-ttu-id="8ba14-148">ID univoco del mittente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-148">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-149">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="8ba14-149">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-150">Posta elettronica</span><span class="sxs-lookup"><span data-stu-id="8ba14-150">Email</span></span></p></td>
<td><p><span data-ttu-id="8ba14-151">Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-151">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-152">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="8ba14-152">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-153">Interno</span><span class="sxs-lookup"><span data-stu-id="8ba14-153">Internal</span></span></p></td>
<td><p><span data-ttu-id="8ba14-154">Determina se l'utente è un utente interno o un utente federato.</span><span class="sxs-lookup"><span data-stu-id="8ba14-154">Determines whether the user is an internal user or a federated user.</span></span> <span data-ttu-id="8ba14-155">Se il valore è impostato su true, l'utente è Internal.</span><span class="sxs-lookup"><span data-stu-id="8ba14-155">If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-156">Facoltativo</span><span class="sxs-lookup"><span data-stu-id="8ba14-156">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-157">URI</span><span class="sxs-lookup"><span data-stu-id="8ba14-157">Uri</span></span></p></td>
<td><p><span data-ttu-id="8ba14-158">URI SIP dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-158">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="8ba14-159">Obbligatorio</span><span class="sxs-lookup"><span data-stu-id="8ba14-159">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8ba14-160">La tabella seguente descrive i tipi di messaggio che l'elemento Message può contenere.</span><span class="sxs-lookup"><span data-stu-id="8ba14-160">The following table describes the message types that the Messages element can contain.</span></span> <span data-ttu-id="8ba14-161">Vengono inoltre illustrati gli esempi di utilizzo di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8ba14-161">It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="8ba14-162">Tipi di messaggio di elementi messaggio</span><span class="sxs-lookup"><span data-stu-id="8ba14-162">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ba14-163">Tipo di messaggio</span><span class="sxs-lookup"><span data-stu-id="8ba14-163">Message Type</span></span></th>
<th><span data-ttu-id="8ba14-164">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba14-164">Description</span></span></th>
<th><span data-ttu-id="8ba14-165">Esempio di codice</span><span class="sxs-lookup"><span data-stu-id="8ba14-165">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-166">Partecipare a</span><span class="sxs-lookup"><span data-stu-id="8ba14-166">Join</span></span></p></td>
<td><p><span data-ttu-id="8ba14-167">Un utente partecipa a una chat room.</span><span class="sxs-lookup"><span data-stu-id="8ba14-167">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-168">Part</span><span class="sxs-lookup"><span data-stu-id="8ba14-168">Part</span></span></p></td>
<td><p><span data-ttu-id="8ba14-169">Un utente lascia una chat room.</span><span class="sxs-lookup"><span data-stu-id="8ba14-169">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-170">Chat</span><span class="sxs-lookup"><span data-stu-id="8ba14-170">Chat</span></span></p></td>
<td><p><span data-ttu-id="8ba14-171">Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="8ba14-171">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-172">Backchat</span><span class="sxs-lookup"><span data-stu-id="8ba14-172">Backchat</span></span></p></td>
<td><p><span data-ttu-id="8ba14-173">Un utente richiede contenuto dalla cronologia chat.</span><span class="sxs-lookup"><span data-stu-id="8ba14-173">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ba14-174">Caricamento di file</span><span class="sxs-lookup"><span data-stu-id="8ba14-174">File upload</span></span></p></td>
<td><p><span data-ttu-id="8ba14-175">Un utente carica un file.</span><span class="sxs-lookup"><span data-stu-id="8ba14-175">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ba14-176">Download di file</span><span class="sxs-lookup"><span data-stu-id="8ba14-176">File download</span></span></p></td>
<td><p><span data-ttu-id="8ba14-177">Un utente scarica un file.</span><span class="sxs-lookup"><span data-stu-id="8ba14-177">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="8ba14-178">XSD di output della chat persistente predefinito e la trasformazione XSL di esempio</span><span class="sxs-lookup"><span data-stu-id="8ba14-178">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="8ba14-179">L'esempio di codice seguente contiene l'output predefinito del server di conformità.</span><span class="sxs-lookup"><span data-stu-id="8ba14-179">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
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

<span data-ttu-id="8ba14-180">L'esempio di codice seguente contiene una trasformazione XSL di esempio.</span><span class="sxs-lookup"><span data-stu-id="8ba14-180">The following code sample contains a sample XSL transform.</span></span>

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

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

