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
ms.openlocfilehash: 5eb0d3d535a4ba5b3e8ffd9a9c712edd601fbbbc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9f893-102">Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f893-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f893-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="9f893-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="9f893-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9f893-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="9f893-106">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="9f893-107">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="9f893-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="9f893-108">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="9f893-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="9f893-109">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="9f893-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9f893-110">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="9f893-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="9f893-111">Uno di questi insiemi può essere modificato in un secondo momento utilizzando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f893-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="9f893-112">Quando si modificano le impostazioni di configurazione del trunk SIP utilizzando il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9f893-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f893-113">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="9f893-113">UI Setting</span></span></th>
<th><span data-ttu-id="9f893-114">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f893-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="9f893-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f893-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f893-116">Name</span><span class="sxs-lookup"><span data-stu-id="9f893-116">Name</span></span></p></td>
<td><p><span data-ttu-id="9f893-117">Identità</span><span class="sxs-lookup"><span data-stu-id="9f893-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="9f893-p103">Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f893-120">Description</span></span></p></td>
<td><p><span data-ttu-id="9f893-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f893-121">Description</span></span></p></td>
<td><p><span data-ttu-id="9f893-122">Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).</span><span class="sxs-lookup"><span data-stu-id="9f893-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-123">Dialoghi anticipati massimi supportati</span><span class="sxs-lookup"><span data-stu-id="9f893-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="9f893-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="9f893-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="9f893-125">Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9f893-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-126">Livello di supporto della crittografia</span><span class="sxs-lookup"><span data-stu-id="9f893-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="9f893-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="9f893-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="9f893-128">Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi.</span><span class="sxs-lookup"><span data-stu-id="9f893-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="9f893-129">Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="9f893-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="9f893-130">La configurazione multimediale viene impostata utilizzando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="9f893-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="9f893-131">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="9f893-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f893-132">Obbligatorio: è necessario utilizzare la crittografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="9f893-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="9f893-133">Facoltativo: SRTP verrà utilizzato se supportato dal gateway.</span><span class="sxs-lookup"><span data-stu-id="9f893-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="9f893-134">Non supportato: la crittografia SRTP non è supportata, pertanto non verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="9f893-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="9f893-p105">SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.</span><span class="sxs-lookup"><span data-stu-id="9f893-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-137">Supporto riferimento</span><span class="sxs-lookup"><span data-stu-id="9f893-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="9f893-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="9f893-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="9f893-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="9f893-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="9f893-140">Se impostato su <strong>Abilita l'invio del riferimento al gateway</strong>, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9f893-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="9f893-141">Se impostato su <strong>Abilita il riferimento usando il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato.</span><span class="sxs-lookup"><span data-stu-id="9f893-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="9f893-142">3PCC è noto anche come &quot;controllo di terze&quot; parti e si verifica quando viene utilizzata una terza parte per connettere una coppia di chiamanti, ad esempio un operatore che effettua una chiamata dalla persona a alla persona B.</span><span class="sxs-lookup"><span data-stu-id="9f893-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-143">Abilita bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="9f893-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="9f893-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="9f893-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="9f893-p107">Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche <strong>Elaborazione multimediale centralizzata</strong>.</span><span class="sxs-lookup"><span data-stu-id="9f893-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-147">Elaborazione multimediale centralizzata</span><span class="sxs-lookup"><span data-stu-id="9f893-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="9f893-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="9f893-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="9f893-p108">Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.</span><span class="sxs-lookup"><span data-stu-id="9f893-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-151">Abilita scatto RTP</span><span class="sxs-lookup"><span data-stu-id="9f893-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="9f893-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="9f893-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="9f893-p109">Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.</span><span class="sxs-lookup"><span data-stu-id="9f893-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-155">Abilita inoltro cronologia chiamate</span><span class="sxs-lookup"><span data-stu-id="9f893-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="9f893-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="9f893-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="9f893-157">Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-158">Abilita inoltro dati PAI</span><span class="sxs-lookup"><span data-stu-id="9f893-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="9f893-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="9f893-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="9f893-p110">Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f893-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-162">Abilita timer di failover del routing in uscita</span><span class="sxs-lookup"><span data-stu-id="9f893-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="9f893-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="9f893-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="9f893-p111">Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.</span><span class="sxs-lookup"><span data-stu-id="9f893-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-166">Utilizzo PSTN associato</span><span class="sxs-lookup"><span data-stu-id="9f893-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="9f893-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="9f893-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="9f893-168">Raccolta di utilizzi PSTN assegnati al trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-169">Numero convertito da testare</span><span class="sxs-lookup"><span data-stu-id="9f893-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="9f893-170">N/D</span><span class="sxs-lookup"><span data-stu-id="9f893-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f893-171">Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-172">Regole di conversione associate</span><span class="sxs-lookup"><span data-stu-id="9f893-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="9f893-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9f893-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9f893-174">Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).</span><span class="sxs-lookup"><span data-stu-id="9f893-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-175">Regole di conversione del numero chiamato</span><span class="sxs-lookup"><span data-stu-id="9f893-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="9f893-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9f893-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9f893-177">Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.</span><span class="sxs-lookup"><span data-stu-id="9f893-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-178">Numero di telefono da testare.</span><span class="sxs-lookup"><span data-stu-id="9f893-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="9f893-179">N/D</span><span class="sxs-lookup"><span data-stu-id="9f893-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f893-180">Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.</span><span class="sxs-lookup"><span data-stu-id="9f893-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f893-181">Numero di chiamata</span><span class="sxs-lookup"><span data-stu-id="9f893-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="9f893-182">N/D</span><span class="sxs-lookup"><span data-stu-id="9f893-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f893-183">Indica che il numero di telefono da testare è il numero di telefono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="9f893-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f893-184">Numero chiamato</span><span class="sxs-lookup"><span data-stu-id="9f893-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="9f893-185">N/D</span><span class="sxs-lookup"><span data-stu-id="9f893-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="9f893-186">Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f893-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9f893-187">I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9f893-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="9f893-188">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="9f893-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="9f893-189">Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="9f893-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9f893-190">Nel pannello di controllo di Lync Server, fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="9f893-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="9f893-p113">Nella scheda **Configurazione trunk** fare doppio clic sulle impostazioni di configurazione del trunk che si desidera modificare. È possibile modificare una sola raccolta di impostazioni per volta. Per apportare le stesse modifiche a più raccolte, utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9f893-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="9f893-194">Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f893-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="9f893-p114">La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="9f893-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="9f893-197">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f893-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="9f893-198">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f893-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

