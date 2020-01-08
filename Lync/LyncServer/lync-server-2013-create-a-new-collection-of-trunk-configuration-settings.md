---
title: 'Lync Server 2013: creare una nuova raccolta di impostazioni di configurazione trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="6f1c1-102">Creare una nuova raccolta di impostazioni di configurazione trunk in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f1c1-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f1c1-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6f1c1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6f1c1-104">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="6f1c1-105">Queste impostazioni eseguono operazioni come specifica:</span><span class="sxs-lookup"><span data-stu-id="6f1c1-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="6f1c1-106">Se il bypass multimediale deve essere abilitato nei trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="6f1c1-107">Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="6f1c1-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="6f1c1-108">Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="6f1c1-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="6f1c1-110">Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="6f1c1-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="6f1c1-111">Quando si creano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f1c1-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f1c1-112">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="6f1c1-112">UI Setting</span></span></th>
<th><span data-ttu-id="6f1c1-113">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f1c1-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="6f1c1-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f1c1-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-115">Nome</span><span class="sxs-lookup"><span data-stu-id="6f1c1-115">Name</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-116">Identity</span><span class="sxs-lookup"><span data-stu-id="6f1c1-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-117">Identificatore univoco per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-117">Unique identifier for the collection.</span></span> <span data-ttu-id="6f1c1-118">Questa proprietà è di sola lettura; non è possibile modificare l'identità di una raccolta di impostazioni di configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-118">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f1c1-119">Description</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f1c1-120">Description</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-121">Consente agli amministratori di archiviare informazioni di aggiunta sulle impostazioni, ad esempio lo scopo della configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-122">Finestre di dialogo iniziali massime supportate</span><span class="sxs-lookup"><span data-stu-id="6f1c1-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="6f1c1-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-124">Numero massimo di risposte a forcella un gateway PSTN, IP-PBX o SBC presso il provider di servizi può ricevere un invito inviato al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-125">Livello di supporto della crittografia</span><span class="sxs-lookup"><span data-stu-id="6f1c1-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="6f1c1-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-127">Indica il livello di supporto per la protezione del traffico multimediale tra il Mediation Server e il gateway PSTN, IP-PBX o SBC presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="6f1c1-128">Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="6f1c1-129">La configurazione multimediale viene impostata usando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="6f1c1-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="6f1c1-130">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="6f1c1-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="6f1c1-131">Obbligatorio: è necessario usare la crittografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="6f1c1-132">Facoltativo: SRTP verrà usato se il gateway lo supporta.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="6f1c1-133">Non supportata: la crittografia SRTP non è supportata e pertanto non verrà usata.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="6f1c1-134">SRTPMode viene usato solo se il gateway è configurato per l'uso di Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="6f1c1-134">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="6f1c1-135">Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) come trasporto, SRTPMode è impostato internamente su non supportato.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-135">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-136">Fare riferimento al supporto</span><span class="sxs-lookup"><span data-stu-id="6f1c1-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="6f1c1-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="6f1c1-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="6f1c1-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-139">Se impostato per <strong>abilitare l'invio, fare riferimento al gateway</strong>, indica che il trunk supporta la ricezione di richieste di riferimento dal server Mediation.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="6f1c1-140">Se impostato per <strong>abilitare l'opzione fai riferimento tramite il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3PCC può essere usato per consentire alle chiamate trasferite di ignorare il sito ospitato.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="6f1c1-141">3PCC è anche noto come &quot;controllo di terze&quot; parti e si verifica quando una terza parte viene usata per connettere una coppia di chiamanti (ad esempio, un operatore che effettua una chiamata dalla persona a alla persona B).</span><span class="sxs-lookup"><span data-stu-id="6f1c1-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-142">Abilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="6f1c1-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="6f1c1-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-144">Indica se il bypass multimediale è abilitato per il trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-144">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="6f1c1-145">Il bypass multimediale può essere abilitato solo se è abilitata anche l' <strong>elaborazione media centralizzata</strong> .</span><span class="sxs-lookup"><span data-stu-id="6f1c1-145">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-146">Elaborazione multimediale centralizzata</span><span class="sxs-lookup"><span data-stu-id="6f1c1-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="6f1c1-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-148">Indica se è presente un punto di interruzione multimediale noto.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-148">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="6f1c1-149">Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione degli elementi multimediali ha lo stesso IP della terminazione dei segnali.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-149">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-150">Abilitare l'aggancio RTP</span><span class="sxs-lookup"><span data-stu-id="6f1c1-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="6f1c1-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-152">Indica se i trunk SIP supportano o meno il latching RTP.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-152">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="6f1c1-153">Il latching RTP è una tecnologia che consente la connettività RTP/RTCP tramite un dispositivo NAT (Network Address Translator) o un firewall.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-153">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-154">Abilitare la cronologia delle chiamate inoltrate</span><span class="sxs-lookup"><span data-stu-id="6f1c1-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="6f1c1-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-156">Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-157">Abilitare inoltra P-asserzione-dati identità</span><span class="sxs-lookup"><span data-stu-id="6f1c1-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="6f1c1-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-159">Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-159">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="6f1c1-160">L'intestazione PAI consente di verificare l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-160">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-161">Abilitare il timer di failover del routing in uscita</span><span class="sxs-lookup"><span data-stu-id="6f1c1-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="6f1c1-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-163">Indica se le chiamate in uscita non risposte dal gateway entro 10 secondi verranno instradate al successivo trunk disponibile. Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-163">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="6f1c1-164">In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-164">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-165">Usi PSTN associati</span><span class="sxs-lookup"><span data-stu-id="6f1c1-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="6f1c1-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-167">Raccolta di utilizzi PSTN assegnati al trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-168">Numero tradotto da testare</span><span class="sxs-lookup"><span data-stu-id="6f1c1-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-169">N/D</span><span class="sxs-lookup"><span data-stu-id="6f1c1-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-170">Numero di telefono che può essere usato per eseguire un test ad hoc delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-171">Regole di traduzione associate</span><span class="sxs-lookup"><span data-stu-id="6f1c1-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="6f1c1-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-173">Raccolta di regole di traduzione per i numeri di telefono che si applicano alle chiamate gestite dal routing in uscita (chiamate indirizzate a destinazioni PBX o PSTN).</span><span class="sxs-lookup"><span data-stu-id="6f1c1-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-174">Regole di traduzione del numero chiamate</span><span class="sxs-lookup"><span data-stu-id="6f1c1-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="6f1c1-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-176">Raccolta di regole di conversione dei numeri in uscita assegnate al trunk.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-177">Numero di telefono da testare</span><span class="sxs-lookup"><span data-stu-id="6f1c1-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-178">N/D</span><span class="sxs-lookup"><span data-stu-id="6f1c1-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-179">Numero di telefono che può essere usato per eseguire un test ad hoc sulle regole di traduzione.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f1c1-180">Numero chiamante</span><span class="sxs-lookup"><span data-stu-id="6f1c1-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-181">N/D</span><span class="sxs-lookup"><span data-stu-id="6f1c1-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-182">Indica che il numero di telefono da testare è il numero di telefono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f1c1-183">Numero chiamato</span><span class="sxs-lookup"><span data-stu-id="6f1c1-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-184">N/D</span><span class="sxs-lookup"><span data-stu-id="6f1c1-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="6f1c1-185">Indica che il numero di telefono da testare è il numero di telefono della persona che viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6f1c1-186">I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="6f1c1-187">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="6f1c1-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="6f1c1-188">Per creare nuove impostazioni di configurazione trunk tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="6f1c1-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6f1c1-189">Nel pannello di controllo di Lync Server fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="6f1c1-190">Nella scheda **configurazione trunk** fare clic su **nuovo**e quindi su **Trunk sito** per creare le nuove impostazioni nell'ambito del sito o trunk del **pool** per creare le nuove impostazioni nell'ambito del servizio.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="6f1c1-191">Nella finestra di dialogo **Seleziona un sito** o **Seleziona un servizio** (la finestra di dialogo visualizzata dipende dal fatto che si stiano creando impostazioni con ambito del sito o con ambito servizio) selezionare la posizione per le nuove impostazioni di configurazione e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-191">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**.</span></span> <span data-ttu-id="6f1c1-192">Se la finestra di dialogo è vuota, significa che non è disponibile alcuna posizione per creare le nuove impostazioni. ad esempio, se la finestra di dialogo **Seleziona sito** è vuota, significa che tutti i siti sono già stati assegnati a una raccolta di siti di configurazione trunk e ogni sito (e ogni servizio) può ospitare solo una di queste raccolte.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-192">If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection.</span></span> <span data-ttu-id="6f1c1-193">In questo caso, puoi eliminare la raccolta esistente e creare una nuova raccolta oppure semplicemente modificare la raccolta esistente.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-193">In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="6f1c1-194">Nella finestra di dialogo **nuova configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="6f1c1-195">La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="6f1c1-196">Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="6f1c1-197">Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="6f1c1-198">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6f1c1-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

