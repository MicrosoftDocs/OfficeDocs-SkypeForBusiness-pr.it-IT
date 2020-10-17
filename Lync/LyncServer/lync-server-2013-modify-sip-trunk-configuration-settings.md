---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del trunk SIP'
description: 'Lync Server 2013: modificare le impostazioni di configurazione del trunk SIP.'
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
ms.openlocfilehash: 42cb213211a11494a96b5a762734a2b5db49dfbb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562142"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="efe50-103">Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efe50-103">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efe50-104">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="efe50-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="efe50-p101">Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="efe50-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="efe50-107">Se abilitare il bypass multimediale nei trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-107">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="efe50-108">Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).</span><span class="sxs-lookup"><span data-stu-id="efe50-108">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="efe50-109">Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).</span><span class="sxs-lookup"><span data-stu-id="efe50-109">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="efe50-110">Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="efe50-110">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="efe50-111">Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="efe50-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="efe50-112">Uno di questi insiemi può essere modificato in un secondo momento utilizzando il pannello di controllo di Lync Server o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efe50-112">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="efe50-113">Quando si modificano le impostazioni di configurazione del trunk SIP utilizzando il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="efe50-113">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efe50-114">Impostazione dell'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="efe50-114">UI Setting</span></span></th>
<th><span data-ttu-id="efe50-115">Parametro di PowerShell</span><span class="sxs-lookup"><span data-stu-id="efe50-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="efe50-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efe50-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efe50-117">Nome</span><span class="sxs-lookup"><span data-stu-id="efe50-117">Name</span></span></p></td>
<td><p><span data-ttu-id="efe50-118">Identità</span><span class="sxs-lookup"><span data-stu-id="efe50-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="efe50-p103">Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efe50-121">Description</span></span></p></td>
<td><p><span data-ttu-id="efe50-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="efe50-122">Description</span></span></p></td>
<td><p><span data-ttu-id="efe50-123">Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).</span><span class="sxs-lookup"><span data-stu-id="efe50-123">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-124">Dialoghi anticipati massimi supportati</span><span class="sxs-lookup"><span data-stu-id="efe50-124">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="efe50-125">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="efe50-125">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="efe50-126">Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="efe50-126">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-127">Livello di supporto della crittografia</span><span class="sxs-lookup"><span data-stu-id="efe50-127">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="efe50-128">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="efe50-128">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="efe50-129">Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi.</span><span class="sxs-lookup"><span data-stu-id="efe50-129">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="efe50-130">Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="efe50-130">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="efe50-131">La configurazione multimediale viene impostata utilizzando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="efe50-131">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="efe50-132">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="efe50-132">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="efe50-133">Obbligatorio: è necessario utilizzare la crittografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="efe50-133">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="efe50-134">Facoltativo: SRTP verrà utilizzato se supportato dal gateway.</span><span class="sxs-lookup"><span data-stu-id="efe50-134">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="efe50-135">Non supportato: la crittografia SRTP non è supportata, pertanto non verrà utilizzata.</span><span class="sxs-lookup"><span data-stu-id="efe50-135">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="efe50-p105">SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.</span><span class="sxs-lookup"><span data-stu-id="efe50-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-138">Supporto riferimento</span><span class="sxs-lookup"><span data-stu-id="efe50-138">Refer support</span></span></p></td>
<td><p><span data-ttu-id="efe50-139">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="efe50-139">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="efe50-140">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="efe50-140">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="efe50-141">Se impostato su <strong>Abilita l'invio del riferimento al gateway</strong>, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="efe50-141">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="efe50-142">Se impostato su <strong>Abilita il riferimento usando il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato.</span><span class="sxs-lookup"><span data-stu-id="efe50-142">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="efe50-143">3PCC è noto anche come controllo di terze &quot; parti &quot; e si verifica quando viene utilizzata una terza parte per connettere una coppia di chiamanti, ad esempio un operatore che effettua una chiamata dalla persona a alla persona B.</span><span class="sxs-lookup"><span data-stu-id="efe50-143">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-144">Abilita bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="efe50-144">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="efe50-145">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="efe50-145">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="efe50-p107">Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche <strong>Elaborazione multimediale centralizzata</strong>.</span><span class="sxs-lookup"><span data-stu-id="efe50-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-148">Elaborazione multimediale centralizzata</span><span class="sxs-lookup"><span data-stu-id="efe50-148">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="efe50-149">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="efe50-149">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="efe50-p108">Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.</span><span class="sxs-lookup"><span data-stu-id="efe50-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-152">Abilita scatto RTP</span><span class="sxs-lookup"><span data-stu-id="efe50-152">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="efe50-153">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="efe50-153">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="efe50-p109">Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.</span><span class="sxs-lookup"><span data-stu-id="efe50-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-156">Abilita inoltro cronologia chiamate</span><span class="sxs-lookup"><span data-stu-id="efe50-156">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="efe50-157">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="efe50-157">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="efe50-158">Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-158">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-159">Abilita inoltro dati PAI</span><span class="sxs-lookup"><span data-stu-id="efe50-159">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="efe50-160">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="efe50-160">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="efe50-p110">Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.</span><span class="sxs-lookup"><span data-stu-id="efe50-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-163">Abilita timer di failover del routing in uscita</span><span class="sxs-lookup"><span data-stu-id="efe50-163">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="efe50-164">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="efe50-164">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="efe50-p111">Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.</span><span class="sxs-lookup"><span data-stu-id="efe50-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-167">Utilizzo PSTN associato</span><span class="sxs-lookup"><span data-stu-id="efe50-167">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="efe50-168">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="efe50-168">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="efe50-169">Raccolta di utilizzi PSTN assegnati al trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-169">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-170">Numero convertito da testare</span><span class="sxs-lookup"><span data-stu-id="efe50-170">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="efe50-171">N/D</span><span class="sxs-lookup"><span data-stu-id="efe50-171">N/A</span></span></p></td>
<td><p><span data-ttu-id="efe50-172">Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-172">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-173">Regole di conversione associate</span><span class="sxs-lookup"><span data-stu-id="efe50-173">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="efe50-174">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="efe50-174">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="efe50-175">Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).</span><span class="sxs-lookup"><span data-stu-id="efe50-175">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-176">Regole di conversione del numero chiamato</span><span class="sxs-lookup"><span data-stu-id="efe50-176">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="efe50-177">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="efe50-177">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="efe50-178">Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.</span><span class="sxs-lookup"><span data-stu-id="efe50-178">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-179">Numero di telefono da testare.</span><span class="sxs-lookup"><span data-stu-id="efe50-179">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="efe50-180">N/D</span><span class="sxs-lookup"><span data-stu-id="efe50-180">N/A</span></span></p></td>
<td><p><span data-ttu-id="efe50-181">Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.</span><span class="sxs-lookup"><span data-stu-id="efe50-181">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe50-182">Numero di chiamata</span><span class="sxs-lookup"><span data-stu-id="efe50-182">Calling number</span></span></p></td>
<td><p><span data-ttu-id="efe50-183">N/D</span><span class="sxs-lookup"><span data-stu-id="efe50-183">N/A</span></span></p></td>
<td><p><span data-ttu-id="efe50-184">Indica che il numero di telefono da testare è il numero di telefono del chiamante.</span><span class="sxs-lookup"><span data-stu-id="efe50-184">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe50-185">Numero chiamato</span><span class="sxs-lookup"><span data-stu-id="efe50-185">Called number</span></span></p></td>
<td><p><span data-ttu-id="efe50-186">N/D</span><span class="sxs-lookup"><span data-stu-id="efe50-186">N/A</span></span></p></td>
<td><p><span data-ttu-id="efe50-187">Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.</span><span class="sxs-lookup"><span data-stu-id="efe50-187">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="efe50-188">I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efe50-188">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="efe50-189">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="efe50-189">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="efe50-190">Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="efe50-190">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="efe50-191">Nel pannello di controllo di Lync Server, fare clic su **routing vocale**e quindi su **configurazione trunk**.</span><span class="sxs-lookup"><span data-stu-id="efe50-191">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="efe50-p113">Nella scheda **Configurazione trunk** fare doppio clic sulle impostazioni di configurazione del trunk che si desidera modificare. È possibile modificare una sola raccolta di impostazioni per volta. Per apportare le stesse modifiche a più raccolte, utilizzare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efe50-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="efe50-195">Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="efe50-195">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="efe50-p114">La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="efe50-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="efe50-198">Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="efe50-198">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="efe50-199">Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="efe50-199">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

