---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="68c47-102">Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68c47-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68c47-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="68c47-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="68c47-104">Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="68c47-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="68c47-105">Queste impostazioni eseguono operazioni come specifica:</span><span class="sxs-lookup"><span data-stu-id="68c47-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="68c47-106">Se il bypass multimediale deve essere abilitato nei trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="68c47-107">Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="68c47-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="68c47-108">Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="68c47-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="68c47-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="68c47-110">Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="68c47-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="68c47-111">Una qualsiasi di queste raccolte può essere modificata in un secondo momento usando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68c47-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="68c47-112">Quando si modificano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="68c47-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68c47-113">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="68c47-113">UI Setting</span></span></th>
<th><span data-ttu-id="68c47-114">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="68c47-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="68c47-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68c47-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68c47-116">Nome</span><span class="sxs-lookup"><span data-stu-id="68c47-116">Name</span></span></p></td>
<td><p><span data-ttu-id="68c47-117">Identity</span><span class="sxs-lookup"><span data-stu-id="68c47-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="68c47-118">Identificatore univoco per la raccolta.</span><span class="sxs-lookup"><span data-stu-id="68c47-118">Unique identifier for the collection.</span></span> <span data-ttu-id="68c47-119">Questa proprietà è di sola lettura; non è possibile modificare l'identità di una raccolta di impostazioni di configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-119">This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68c47-120">Description</span></span></p></td>
<td><p><span data-ttu-id="68c47-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="68c47-121">Description</span></span></p></td>
<td><p><span data-ttu-id="68c47-122">Consente agli amministratori di archiviare informazioni di aggiunta sulle impostazioni, ad esempio lo scopo della configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-123">Finestre di dialogo iniziali massime supportate</span><span class="sxs-lookup"><span data-stu-id="68c47-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="68c47-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="68c47-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="68c47-125">Numero massimo di risposte a forcella un gateway PSTN, IP-PBX o SBC presso il provider di servizi può ricevere un invito inviato al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="68c47-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-126">Livello di supporto della crittografia</span><span class="sxs-lookup"><span data-stu-id="68c47-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="68c47-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="68c47-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="68c47-128">Indica il livello di supporto per la protezione del traffico multimediale tra il Mediation Server e il gateway PSTN, IP-PBX o SBC presso il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="68c47-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="68c47-129">Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="68c47-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="68c47-130">La configurazione multimediale viene impostata usando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="68c47-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="68c47-131">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="68c47-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="68c47-132">Obbligatorio: è necessario usare la crittografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="68c47-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="68c47-133">Facoltativo: SRTP verrà usato se il gateway lo supporta.</span><span class="sxs-lookup"><span data-stu-id="68c47-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="68c47-134">Non supportata: la crittografia SRTP non è supportata e pertanto non verrà usata.</span><span class="sxs-lookup"><span data-stu-id="68c47-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="68c47-135">SRTPMode viene usato solo se il gateway è configurato per l'uso di Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="68c47-135">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS).</span></span> <span data-ttu-id="68c47-136">Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) come trasporto, SRTPMode è impostato internamente su non supportato.</span><span class="sxs-lookup"><span data-stu-id="68c47-136">If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-137">Fare riferimento al supporto</span><span class="sxs-lookup"><span data-stu-id="68c47-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="68c47-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="68c47-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="68c47-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="68c47-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="68c47-140">Se impostato per <strong>abilitare l'invio, fare riferimento al gateway</strong>, indica che il trunk supporta la ricezione di richieste di riferimento dal server Mediation.</span><span class="sxs-lookup"><span data-stu-id="68c47-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="68c47-141">Se impostato per <strong>abilitare l'opzione fai riferimento tramite il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3PCC può essere usato per consentire alle chiamate trasferite di ignorare il sito ospitato.</span><span class="sxs-lookup"><span data-stu-id="68c47-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="68c47-142">3PCC è anche noto come &quot;controllo di terze&quot; parti e si verifica quando una terza parte viene usata per connettere una coppia di chiamanti (ad esempio, un operatore che effettua una chiamata dalla persona a alla persona B).</span><span class="sxs-lookup"><span data-stu-id="68c47-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-143">Abilitare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="68c47-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="68c47-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="68c47-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="68c47-145">Indica se il bypass multimediale è abilitato per il trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-145">Indicates whether media bypass is enabled for this trunk.</span></span> <span data-ttu-id="68c47-146">Il bypass multimediale può essere abilitato solo se è abilitata anche l' <strong>elaborazione media centralizzata</strong> .</span><span class="sxs-lookup"><span data-stu-id="68c47-146">Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-147">Elaborazione multimediale centralizzata</span><span class="sxs-lookup"><span data-stu-id="68c47-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="68c47-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="68c47-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="68c47-149">Indica se è presente un punto di interruzione multimediale noto.</span><span class="sxs-lookup"><span data-stu-id="68c47-149">Indicates whether there is a well-known media termination point.</span></span> <span data-ttu-id="68c47-150">Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione degli elementi multimediali ha lo stesso IP della terminazione dei segnali.</span><span class="sxs-lookup"><span data-stu-id="68c47-150">(An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-151">Abilitare l'aggancio RTP</span><span class="sxs-lookup"><span data-stu-id="68c47-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="68c47-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="68c47-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="68c47-153">Indica se i trunk SIP supportano o meno il latching RTP.</span><span class="sxs-lookup"><span data-stu-id="68c47-153">Indicates whether or not the SIP trunks support RTP latching.</span></span> <span data-ttu-id="68c47-154">Il latching RTP è una tecnologia che consente la connettività RTP/RTCP tramite un dispositivo NAT (Network Address Translator) o un firewall.</span><span class="sxs-lookup"><span data-stu-id="68c47-154">RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-155">Abilitare la cronologia delle chiamate inoltrate</span><span class="sxs-lookup"><span data-stu-id="68c47-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="68c47-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="68c47-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="68c47-157">Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-158">Abilitare inoltra P-asserzione-dati identità</span><span class="sxs-lookup"><span data-stu-id="68c47-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="68c47-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="68c47-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="68c47-160">Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="68c47-160">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="68c47-161">L'intestazione PAI consente di verificare l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="68c47-161">The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-162">Abilitare il timer di failover del routing in uscita</span><span class="sxs-lookup"><span data-stu-id="68c47-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="68c47-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="68c47-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="68c47-164">Indica se le chiamate in uscita non risposte dal gateway entro 10 secondi verranno instradate al successivo trunk disponibile. Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="68c47-164">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped.</span></span> <span data-ttu-id="68c47-165">In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.</span><span class="sxs-lookup"><span data-stu-id="68c47-165">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-166">Usi PSTN associati</span><span class="sxs-lookup"><span data-stu-id="68c47-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="68c47-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="68c47-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="68c47-168">Raccolta di utilizzi PSTN assegnati al trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-169">Numero tradotto da testare</span><span class="sxs-lookup"><span data-stu-id="68c47-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="68c47-170">N/D</span><span class="sxs-lookup"><span data-stu-id="68c47-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="68c47-171">Numero di telefono che può essere usato per eseguire un test ad hoc delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-172">Regole di traduzione associate</span><span class="sxs-lookup"><span data-stu-id="68c47-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="68c47-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="68c47-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="68c47-174">Raccolta di regole di traduzione per i numeri di telefono che si applicano alle chiamate gestite dal routing in uscita (chiamate indirizzate a destinazioni PBX o PSTN).</span><span class="sxs-lookup"><span data-stu-id="68c47-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-175">Regole di traduzione del numero chiamate</span><span class="sxs-lookup"><span data-stu-id="68c47-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="68c47-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="68c47-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="68c47-177">Raccolta di regole di conversione dei numeri in uscita assegnate al trunk.</span><span class="sxs-lookup"><span data-stu-id="68c47-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-178">Numero di telefono da testare</span><span class="sxs-lookup"><span data-stu-id="68c47-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="68c47-179">N/D</span><span class="sxs-lookup"><span data-stu-id="68c47-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="68c47-180">Numero di telefono che può essere usato per eseguire un test ad hoc sulle regole di traduzione.</span><span class="sxs-lookup"><span data-stu-id="68c47-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68c47-181">Numero chiamante</span><span class="sxs-lookup"><span data-stu-id="68c47-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="68c47-182">N/D</span><span class="sxs-lookup"><span data-stu-id="68c47-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="68c47-183">Indica che il numero di telefono da testare è il numero di telefono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="68c47-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68c47-184">Numero chiamato</span><span class="sxs-lookup"><span data-stu-id="68c47-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="68c47-185">N/D</span><span class="sxs-lookup"><span data-stu-id="68c47-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="68c47-186">Indica che il numero di telefono da testare è il numero di telefono della persona che viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="68c47-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="68c47-187">I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68c47-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="68c47-188">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="68c47-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="68c47-189">Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="68c47-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="68c47-190">Nel pannello di controllo di Lync Server fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="68c47-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="68c47-191">Nella scheda **configurazione trunk** fare doppio clic sulle impostazioni di configurazione trunk da modificare.</span><span class="sxs-lookup"><span data-stu-id="68c47-191">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified.</span></span> <span data-ttu-id="68c47-192">Tieni presente che puoi modificare solo una raccolta di impostazioni alla volta.</span><span class="sxs-lookup"><span data-stu-id="68c47-192">Note that you can only edit one collection of settings at a time.</span></span> <span data-ttu-id="68c47-193">Se si desidera apportare le stesse modifiche in più insiemi, utilizzare invece Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68c47-193">If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="68c47-194">Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68c47-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="68c47-195">La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**.</span><span class="sxs-lookup"><span data-stu-id="68c47-195">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="68c47-196">Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.</span><span class="sxs-lookup"><span data-stu-id="68c47-196">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="68c47-197">Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68c47-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="68c47-198">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="68c47-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

