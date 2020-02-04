---
title: 'Lync Server 2013: configurazione degli intervalli di porte per i client Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6405ff6738315476efb7ee65f6d5e020a7cf28a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="a60d2-102">Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a60d2-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a60d2-103">_**Argomento Ultima modifica:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="a60d2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="a60d2-104">Per impostazione predefinita, le applicazioni client di Lync possono usare una qualsiasi porta tra le porte 1024 e 65535 quando si partecipa a una sessione di comunicazione; il motivo è che gli intervalli di porte specifici non vengono abilitati automaticamente per i client.</span><span class="sxs-lookup"><span data-stu-id="a60d2-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="a60d2-105">Per poter usare la qualità del servizio, è tuttavia necessario riassegnare i vari tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento di file) a una serie di intervalli di porte univoci.</span><span class="sxs-lookup"><span data-stu-id="a60d2-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="a60d2-106">Questa operazione può essere eseguita usando il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a60d2-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a60d2-107">Gli utenti finali non possono apportare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="a60d2-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="a60d2-108">Le modifiche alle porte possono essere eseguite solo dagli amministratori tramite il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="a60d2-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="a60d2-109">Per determinare gli intervalli di porte attualmente usati per le sessioni di comunicazione, è possibile eseguire il comando seguente all'interno di Microsoft Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="a60d2-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="a60d2-110">Supponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Lync Server 2013, è consigliabile recuperare le informazioni che includono questi valori di proprietà:</span><span class="sxs-lookup"><span data-stu-id="a60d2-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="a60d2-111">Se si osserva attentamente l'output precedente, verranno visualizzati due elementi importanti.</span><span class="sxs-lookup"><span data-stu-id="a60d2-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="a60d2-112">Prima di tutto, la proprietà ClientMediaPortRangeEnabled è impostata su false:</span><span class="sxs-lookup"><span data-stu-id="a60d2-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="a60d2-113">Questo è importante perché, quando questa proprietà è impostata su false, i client Lync useranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione; Questo vale indipendentemente da qualsiasi altra impostazione della porta, ad esempio ClientMediaPort o ClientVideoPort.</span><span class="sxs-lookup"><span data-stu-id="a60d2-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="a60d2-114">Se si vuole limitare l'utilizzo a un set di porte specificato (e si vuole eseguire questa operazione se si prevede di implementare la qualità del servizio), è necessario prima di tutto abilitare gli intervalli di porta del supporto client.</span><span class="sxs-lookup"><span data-stu-id="a60d2-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="a60d2-115">Questa operazione può essere eseguita usando il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="a60d2-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a60d2-116">Il comando precedente consente di abilitare gli intervalli di porta multimediali del client per la raccolta globale delle impostazioni di configurazione delle conferenze; Queste impostazioni possono tuttavia essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio di conferenza Server).</span><span class="sxs-lookup"><span data-stu-id="a60d2-116">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="a60d2-117">Per abilitare gli intervalli della porta multimediale client per un sito o un server specifico, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="a60d2-117">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a60d2-118">In alternativa, puoi usare questo comando per abilitare simultaneamente gli intervalli di porta per tutte le impostazioni di configurazione della conferenza:</span><span class="sxs-lookup"><span data-stu-id="a60d2-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a60d2-119">La seconda cosa importante che si noterà è che l'output di esempio mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:</span><span class="sxs-lookup"><span data-stu-id="a60d2-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="a60d2-120">Per implementare QoS, ognuno di questi intervalli di porte dovrà essere univoco.</span><span class="sxs-lookup"><span data-stu-id="a60d2-120">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="a60d2-121">Ad esempio, è possibile configurare gli intervalli di porte come questo:</span><span class="sxs-lookup"><span data-stu-id="a60d2-121">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a60d2-122">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="a60d2-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="a60d2-123">Inizio porta</span><span class="sxs-lookup"><span data-stu-id="a60d2-123">Port Start</span></span></th>
<th><span data-ttu-id="a60d2-124">Intervallo di porte</span><span class="sxs-lookup"><span data-stu-id="a60d2-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a60d2-125">Audio</span><span class="sxs-lookup"><span data-stu-id="a60d2-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="a60d2-126">50020</span><span class="sxs-lookup"><span data-stu-id="a60d2-126">50020</span></span></p></td>
<td><p><span data-ttu-id="a60d2-127">20</span><span class="sxs-lookup"><span data-stu-id="a60d2-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a60d2-128">Video</span><span class="sxs-lookup"><span data-stu-id="a60d2-128">Video</span></span></p></td>
<td><p><span data-ttu-id="a60d2-129">58000</span><span class="sxs-lookup"><span data-stu-id="a60d2-129">58000</span></span></p></td>
<td><p><span data-ttu-id="a60d2-130">20</span><span class="sxs-lookup"><span data-stu-id="a60d2-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a60d2-131">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="a60d2-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a60d2-132">42000</span><span class="sxs-lookup"><span data-stu-id="a60d2-132">42000</span></span></p></td>
<td><p><span data-ttu-id="a60d2-133">20</span><span class="sxs-lookup"><span data-stu-id="a60d2-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a60d2-134">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="a60d2-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="a60d2-135">42020</span><span class="sxs-lookup"><span data-stu-id="a60d2-135">42020</span></span></p></td>
<td><p><span data-ttu-id="a60d2-136">20</span><span class="sxs-lookup"><span data-stu-id="a60d2-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a60d2-137">Nella tabella precedente gli intervalli di porte client rappresentano un sottoinsieme degli intervalli di porte configurati per i server.</span><span class="sxs-lookup"><span data-stu-id="a60d2-137">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="a60d2-138">Ad esempio, nei server la condivisione delle applicazioni è stata configurata per l'uso delle porte da 40803 a 49151; nei computer client la condivisione delle applicazioni è configurata per l'uso delle porte da 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="a60d2-138">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="a60d2-139">Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione di QoS: le porte client non devono rappresentare un sottoinsieme delle porte usate nel server.</span><span class="sxs-lookup"><span data-stu-id="a60d2-139">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="a60d2-140">Ad esempio, nei computer client è possibile configurare la condivisione delle applicazioni per usare, per dire, le porte da 10000 a 10019. Tuttavia, è consigliabile rendere gli intervalli della porta del client un sottoinsieme degli intervalli di porte del server.</span><span class="sxs-lookup"><span data-stu-id="a60d2-140">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="a60d2-141">Inoltre, potresti aver notato che le porte di 8348 sono state accantonate per la condivisione delle applicazioni sui server, ma solo 20 porte sono state accantonate per la condivisione delle applicazioni nei client.</span><span class="sxs-lookup"><span data-stu-id="a60d2-141">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="a60d2-142">Anche questo è consigliato, ma non è una regola difficile e veloce.</span><span class="sxs-lookup"><span data-stu-id="a60d2-142">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="a60d2-143">In generale, è possibile considerare ogni porta disponibile per rappresentare una singola sessione di comunicazione: se sono disponibili porte di 100 in un intervallo di porte che significa che il computer in questione può partecipare, al massimo, a 100 sessioni di comunicazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="a60d2-143">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="a60d2-144">Poiché i server probabilmente parteciperanno a molte più conversazioni rispetto ai client, è opportuno aprire molte più porte nei server che nei client.</span><span class="sxs-lookup"><span data-stu-id="a60d2-144">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="a60d2-145">L'impostazione di 20 porte per la condivisione delle applicazioni in un client significa che un utente può partecipare a 20 sessioni di condivisione applicazioni nel dispositivo specificato e contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a60d2-145">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="a60d2-146">Questo dovrebbe risultare sufficiente per la stragrande maggioranza degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a60d2-146">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="a60d2-147">Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione per i servizi di conferenza, è possibile usare il comando Lync Server Management Shell seguente:</span><span class="sxs-lookup"><span data-stu-id="a60d2-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="a60d2-148">In alternativa, usare questo comando per assegnare gli stessi intervalli di porte per tutte le impostazioni di configurazione per i servizi di conferenza:</span><span class="sxs-lookup"><span data-stu-id="a60d2-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="a60d2-149">I singoli utenti devono disconnettersi da Lync e quindi eseguire nuovamente l'accesso prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="a60d2-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a60d2-150">Puoi anche abilitare gli intervalli di porta multimediali del client e quindi assegnare questi intervalli di porte usando un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="a60d2-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="a60d2-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a60d2-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

