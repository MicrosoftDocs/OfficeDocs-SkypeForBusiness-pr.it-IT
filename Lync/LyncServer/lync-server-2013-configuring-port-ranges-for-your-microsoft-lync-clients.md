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
ms.openlocfilehash: ea0300b042dc124f0fb8bf523221e39128cbf57a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="c22d5-102">Configurazione degli intervalli di porte per i client Microsoft Lync in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c22d5-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c22d5-103">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c22d5-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c22d5-104">Per impostazione predefinita, le applicazioni client di Lync possono utilizzare qualsiasi porta tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Ciò è dovuto al fatto che gli intervalli di porte specifici non sono abilitati automaticamente per i client.</span><span class="sxs-lookup"><span data-stu-id="c22d5-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="c22d5-105">Per poter utilizzare la qualità del servizio, tuttavia, sarà necessario riassegnare i diversi tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento file) a una serie di intervalli di porte univoci.</span><span class="sxs-lookup"><span data-stu-id="c22d5-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="c22d5-106">A tale scopo, è possibile utilizzare il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c22d5-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c22d5-107">Gli utenti finali non possono apportare queste modifiche da soli.</span><span class="sxs-lookup"><span data-stu-id="c22d5-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="c22d5-108">Le modifiche apportate alle porte possono essere eseguite solo dagli amministratori utilizzando il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c22d5-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="c22d5-109">È possibile determinare quali intervalli di porte sono attualmente utilizzati per le sessioni di comunicazione eseguendo il comando riportato di seguito dall'interno di Microsoft Lync Server 2013 Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c22d5-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="c22d5-110">Presupponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Lync Server 2013, è consigliabile recuperare le informazioni che includono i valori delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="c22d5-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="c22d5-111">Se si osserva attentamente l'output precedente, si noteranno due aspetti importanti.</span><span class="sxs-lookup"><span data-stu-id="c22d5-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="c22d5-112">Innanzitutto, la proprietà ClientMediaPortRangeEnabled è impostata su False:</span><span class="sxs-lookup"><span data-stu-id="c22d5-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="c22d5-113">Questo è importante perché, quando questa proprietà è impostata su false, i client Lync utilizzeranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Questo è vero, indipendentemente da altre impostazioni di porta, ad esempio ClientMediaPort o ClientVideoPort.</span><span class="sxs-lookup"><span data-stu-id="c22d5-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="c22d5-114">Se si desidera limitare l'utilizzo a un set specifico di porte (e questo è un elemento che si desidera eseguire se si prevede di implementare la qualità del servizio), è necessario innanzitutto abilitare gli intervalli di porte del supporto client.</span><span class="sxs-lookup"><span data-stu-id="c22d5-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="c22d5-115">Che è possibile eseguire utilizzando il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="c22d5-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c22d5-p105">Il comando precedente abilita gli intervalli di porte multimediali dei client per la raccolta globale delle impostazioni di configurazione delle conferenze. Tali impostazioni, tuttavia, possono essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio Conferencing Server). Per abilitare gli intervalli di porte multimediali dei client per un determinato sito o server, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="c22d5-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c22d5-118">In alternativa, è possibile usare questo comando per abilitare contemporaneamente gli intervalli di porte per tutte le impostazioni di configurazione delle conferenze:</span><span class="sxs-lookup"><span data-stu-id="c22d5-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="c22d5-119">Il secondo aspetto importante da osservare è l'output di esempio. Questo mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:</span><span class="sxs-lookup"><span data-stu-id="c22d5-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="c22d5-p106">Per implementare QoS, è necessario che ciascuno di questi intervalli di porte sia univoco. È ad esempio possibile configurare gli intervalli di porte in questo modo:</span><span class="sxs-lookup"><span data-stu-id="c22d5-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c22d5-122">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="c22d5-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="c22d5-123">Inizio intervallo porte</span><span class="sxs-lookup"><span data-stu-id="c22d5-123">Port Start</span></span></th>
<th><span data-ttu-id="c22d5-124">Intervallo porte</span><span class="sxs-lookup"><span data-stu-id="c22d5-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c22d5-125">Audio</span><span class="sxs-lookup"><span data-stu-id="c22d5-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="c22d5-126">50020</span><span class="sxs-lookup"><span data-stu-id="c22d5-126">50020</span></span></p></td>
<td><p><span data-ttu-id="c22d5-127">20</span><span class="sxs-lookup"><span data-stu-id="c22d5-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c22d5-128">Video</span><span class="sxs-lookup"><span data-stu-id="c22d5-128">Video</span></span></p></td>
<td><p><span data-ttu-id="c22d5-129">58000</span><span class="sxs-lookup"><span data-stu-id="c22d5-129">58000</span></span></p></td>
<td><p><span data-ttu-id="c22d5-130">20</span><span class="sxs-lookup"><span data-stu-id="c22d5-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c22d5-131">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="c22d5-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="c22d5-132">42000</span><span class="sxs-lookup"><span data-stu-id="c22d5-132">42000</span></span></p></td>
<td><p><span data-ttu-id="c22d5-133">20</span><span class="sxs-lookup"><span data-stu-id="c22d5-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c22d5-134">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="c22d5-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="c22d5-135">42020</span><span class="sxs-lookup"><span data-stu-id="c22d5-135">42020</span></span></p></td>
<td><p><span data-ttu-id="c22d5-136">20</span><span class="sxs-lookup"><span data-stu-id="c22d5-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c22d5-p107">Nella tabella precedente gli intervalli di porte dei client rappresentano un subset degli intervalli di porte configurati per i server. Sui server, ad esempio, la condivisione applicazioni è configurata in modo da usare le porte da 40803 a 49151, mentre sui computer client la condivisione applicazioni è configurata in modo da usare le porte da 42000 a 42019. Questo consente, ancora una volta, di semplificare l'amministrazione di Qualità del servizio, in quanto non è necessario che le porte dei client rappresentino un subset delle porte usate sul server. Sui computer client è ad esempio possibile configurare la condivisione applicazioni in modo da usare le porte da 10000 a 10019. È tuttavia consigliabile impostare gli intervalli di porte dei client come subset degli intervalli di porte dei server.</span><span class="sxs-lookup"><span data-stu-id="c22d5-p107">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers. For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019. This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server. (For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="c22d5-p108">Si sarà inoltre notato che sono state riservate 8348 porte per la condivisione applicazioni sui server e che solo 20 porte sono state messe da parte per la condivisione applicazioni sui client. Anche questa regola è consigliata, sebbene non sia categorica. In genere, è possibile considerare che ogni porta disponibile rappresenti una singola sessione di comunicazione: la disponibilità di 100 porte in un intervallo di porte, indica che il computer in questione può partecipare a non più di 100 sessioni di comunicazione in un dato momento. Poiché è probabile che i server verranno coinvolti in un numero di conversazioni di gran lunga superiore a quelle dei client, è ragionevole aprire molte più porte sui server che non sui client. La scelta di riservare 20 porte per la condivisione applicazioni su un client significa che un utente può partecipare contemporaneamente a 20 sessioni di condivisione applicazioni sul dispositivo specificato. Questa configurazione dovrebbe soddisfare la maggior parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c22d5-p108">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients. This, too is recommended, but is not a hard-and-fast rule. In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time. Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients. Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time. That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="c22d5-147">Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione delle conferenze, è possibile utilizzare il seguente comando di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c22d5-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c22d5-148">In alternativa, usare il comando per assegnare questi stessi intervalli di porte per tutte le impostazioni di configurazione delle conferenze:</span><span class="sxs-lookup"><span data-stu-id="c22d5-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="c22d5-149">I singoli utenti devono disconnettersi da Lync e quindi rieseguire l'accesso prima che queste modifiche siano effettivamente effettive.</span><span class="sxs-lookup"><span data-stu-id="c22d5-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c22d5-150">È anche possibile abilitare gli intervalli di porte multimediali dei client e quindi assegnarli con un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="c22d5-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="c22d5-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c22d5-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

