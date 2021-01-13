---
title: Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In questo articolo viene descritto come configurare gli intervalli di porte per i client e la configurazione dei criteri di qualità del servizio in Skype for Business Server per i client in esecuzione in Windows 10.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814206"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="f6e5d-103">Configurazione degli intervalli di porte e dei criteri di qualità del servizio per i client in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f6e5d-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="f6e5d-104">In questo articolo viene descritto come configurare gli intervalli di porte per i client e la configurazione dei criteri di qualità del servizio in Skype for Business Server per i client in esecuzione in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="f6e5d-105">Configurare gli intervalli di porte</span><span class="sxs-lookup"><span data-stu-id="f6e5d-105">Configure port ranges</span></span>

<span data-ttu-id="f6e5d-106">Per impostazione predefinita, le applicazioni client Skype for business possono utilizzare qualsiasi porta tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Ciò è dovuto al fatto che gli intervalli di porte specifici non sono abilitati automaticamente per i client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="f6e5d-107">Per poter utilizzare la qualità del servizio, tuttavia, sarà necessario riassegnare i diversi tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento file) a una serie di intervalli di porte univoci.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="f6e5d-108">A tale scopo, è possibile utilizzare il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="f6e5d-109">Gli utenti finali non possono apportare queste modifiche da soli.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="f6e5d-110">Le modifiche apportate alle porte possono essere eseguite solo dagli amministratori utilizzando il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="f6e5d-111">È possibile determinare quali intervalli di porte sono attualmente utilizzati per le sessioni di comunicazione eseguendo il comando riportato di seguito dall'interno della shell di gestione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="f6e5d-112">Presupponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Skype for Business Server, è consigliabile recuperare le informazioni che includono i valori delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="f6e5d-113">Se si osserva attentamente l'output precedente, si noteranno due aspetti importanti.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="f6e5d-114">Innanzitutto, la proprietà ClientMediaPortRangeEnabled è impostata su False:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="f6e5d-115">Questo è importante perché, quando questa proprietà è impostata su false, i client Skype for business utilizzeranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione. Questo è vero, indipendentemente da altre impostazioni di porta, ad esempio ClientMediaPort o ClientVideoPort.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="f6e5d-116">Se si desidera limitare l'utilizzo a un set specifico di porte e si desidera eseguire questa operazione se si prevede di implementare la qualità del servizio, è necessario innanzitutto abilitare gli intervalli di porte del supporto client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="f6e5d-117">Che è possibile eseguire utilizzando il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f6e5d-p105">Il comando precedente abilita gli intervalli di porte multimediali dei client per la raccolta globale delle impostazioni di configurazione delle conferenze. Tali impostazioni, tuttavia, possono essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio Conferencing Server). Per abilitare gli intervalli di porte multimediali dei client per un determinato sito o server, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p105">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only). To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f6e5d-120">In alternativa, è possibile usare questo comando per abilitare contemporaneamente gli intervalli di porte per tutte le impostazioni di configurazione delle conferenze:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="f6e5d-121">Il secondo aspetto importante da osservare è l'output di esempio. Questo mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="f6e5d-p106">Per implementare QoS, è necessario che ciascuno di questi intervalli di porte sia univoco. È ad esempio possibile configurare gli intervalli di porte in questo modo:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p106">In order to implement QoS, each of these port ranges will need to be unique. For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e5d-124">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="f6e5d-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f6e5d-125">Inizio intervallo porte</span><span class="sxs-lookup"><span data-stu-id="f6e5d-125">Port Start</span></span></th>
<th><span data-ttu-id="f6e5d-126">Intervallo porte</span><span class="sxs-lookup"><span data-stu-id="f6e5d-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e5d-127">Audio</span><span class="sxs-lookup"><span data-stu-id="f6e5d-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-128">50020</span><span class="sxs-lookup"><span data-stu-id="f6e5d-128">50020</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-129">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e5d-130">Video</span><span class="sxs-lookup"><span data-stu-id="f6e5d-130">Video</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-131">58000</span><span class="sxs-lookup"><span data-stu-id="f6e5d-131">58000</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-132">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e5d-133">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="f6e5d-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-134">42000</span><span class="sxs-lookup"><span data-stu-id="f6e5d-134">42000</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-135">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e5d-136">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="f6e5d-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-137">42020</span><span class="sxs-lookup"><span data-stu-id="f6e5d-137">42020</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-138">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f6e5d-139">Nella tabella precedente gli intervalli di porte dei client rappresentano un subset degli intervalli di porte configurati per i server.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="f6e5d-140">Sui server, ad esempio, la condivisione applicazioni è configurata in modo da usare le porte da 40803 a 49151, mentre sui computer client la condivisione applicazioni è configurata in modo da usare le porte da 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="f6e5d-141">Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione del QoS: le porte client non devono rappresentare un sottoinsieme delle porte utilizzate sul server.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="f6e5d-142">Ad esempio, nei computer client è possibile configurare la condivisione delle applicazioni in modo da utilizzare le porte da 10000 a 10019. Tuttavia, si consiglia di rendere gli intervalli di porte client un sottoinsieme degli intervalli di porte del server.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="f6e5d-143">Si sarà inoltre notato che sono state riservate 8348 porte per la condivisione applicazioni sui server e che solo 20 porte sono state messe da parte per la condivisione applicazioni sui client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="f6e5d-144">È consigliabile anche questo, ma non è una regola di duro e veloce.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="f6e5d-145">In generale, è possibile considerare tutte le porte disponibili per rappresentare una singola sessione di comunicazione: se si dispone di 100 porte disponibili in un intervallo di porte, significa che il computer in questione può partecipare al massimo a 100 sessioni di comunicazione in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="f6e5d-146">Poiché è probabile che i server verranno coinvolti in un numero di conversazioni di gran lunga superiore a quelle dei client, è ragionevole aprire molte più porte sui server che non sui client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="f6e5d-147">La scelta di riservare 20 porte per la condivisione applicazioni su un client significa che un utente può partecipare contemporaneamente a 20 sessioni di condivisione applicazioni sul dispositivo specificato.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="f6e5d-148">Questa configurazione dovrebbe soddisfare la maggior parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="f6e5d-149">Per assegnare gli intervalli di porte precedenti alla raccolta globale delle impostazioni di configurazione delle conferenze, è possibile utilizzare il seguente comando di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f6e5d-150">In alternativa, usare il comando per assegnare questi stessi intervalli di porte per tutte le impostazioni di configurazione delle conferenze:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="f6e5d-151">I singoli utenti devono disconnettersi da Skype for business e quindi rieseguire l'accesso prima che queste modifiche siano effettivamente effettive.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="f6e5d-152">È anche possibile abilitare gli intervalli di porte multimediali dei client e quindi assegnarli con un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="f6e5d-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="f6e5d-154">Configurazione dei criteri di qualità del servizio per i client in esecuzione in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f6e5d-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="f6e5d-155">Oltre a specificare gli intervalli di porte per l'utilizzo da parte dei client Skype for business, è inoltre necessario creare criteri di qualità del servizio distinti che verranno applicati ai computer client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="f6e5d-156">I criteri di qualità dei servizi creati per le conferenze, l'applicazione e i Mediation Server non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Skype for business e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="f6e5d-157">Nell'esempio seguente viene utilizzato questo set di intervalli di porte per creare un criterio audio e un criterio video:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6e5d-158">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="f6e5d-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="f6e5d-159">Inizio intervallo porte</span><span class="sxs-lookup"><span data-stu-id="f6e5d-159">Port Start</span></span></th>
<th><span data-ttu-id="f6e5d-160">Intervallo porte</span><span class="sxs-lookup"><span data-stu-id="f6e5d-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6e5d-161">Audio</span><span class="sxs-lookup"><span data-stu-id="f6e5d-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-162">50020</span><span class="sxs-lookup"><span data-stu-id="f6e5d-162">50020</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-163">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e5d-164">Video</span><span class="sxs-lookup"><span data-stu-id="f6e5d-164">Video</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-165">58000</span><span class="sxs-lookup"><span data-stu-id="f6e5d-165">58000</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-166">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6e5d-167">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="f6e5d-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-168">42000</span><span class="sxs-lookup"><span data-stu-id="f6e5d-168">42000</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-169">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6e5d-170">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="f6e5d-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-171">42020</span><span class="sxs-lookup"><span data-stu-id="f6e5d-171">42020</span></span></p></td>
<td><p><span data-ttu-id="f6e5d-172">20</span><span class="sxs-lookup"><span data-stu-id="f6e5d-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="f6e5d-173">Per creare criteri audio di qualità del servizio per i computer con Windows 10, è necessario prima accedere a un computer in cui è stata installata la gestione criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="f6e5d-174">Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione** e quindi fare clic su **Gestione criteri di gruppo**) e quindi eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="f6e5d-175">In Gestione Criteri di gruppo, individuare il contenitore in cui creare il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="f6e5d-176">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata clients, è necessario creare il nuovo criterio nell'unità organizzativa client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="f6e5d-177">Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi fare clic su **Crea un oggetto Criteri di gruppo in questo dominio e collegarlo qui**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="f6e5d-178">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="f6e5d-179">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="f6e5d-180">In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri** e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="f6e5d-181">Nella pagina apertura della finestra di dialogo **QoS basata su criteri** Digitare un nome per il nuovo criterio nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="f6e5d-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="f6e5d-182">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="f6e5d-183">Lasciare non selezionata l'opzione **Specifica velocità in uscita**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="f6e5d-184">Nella pagina successiva selezionare **solo le applicazioni con il nome eseguibile**, immettere **Lync.exe** come nome e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="f6e5d-185">Questa impostazione indica al criterio di assegnare la priorità solo al traffico corrispondente proveniente dal client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="f6e5d-186">Nella terza pagina, verificare che siano selezionati tutti gli indirizzi IP di **origine** e **qualsiasi indirizzo IP di destinazione** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="f6e5d-187">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente dal computer (indirizzo IP) di provenienza e dal computer (indirizzo IP) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="f6e5d-188">Nella quarta pagina selezionare **TCP e UDP** dall'elenco a discesa **Seleziona il protocollo a cui si applica questo criterio QoS**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="f6e5d-189">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete più comunemente usati da Skype for Business Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="f6e5d-p117">Sotto l'intestazione **Specifica il numero della porta di origine** selezionare **Da questo numero di porta o intervallo di porte di origine**. Nella casella di testo abbinata digitare l'intervallo di porte riservato alle trasmissioni audio. Se ad esempio è stato riservato al traffico audio l'intervallo di porte compreso tra la 50020 e la 50039, immettere l'intervallo di porte utilizzando questo formato: **50020:50039**. Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p117">Under the heading **Specify the source port number**, select **From this source port or range**. In the accompanying text box, type the port range reserved for audio transmissions. For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**. Click **Finish**.</span></span>

<span data-ttu-id="f6e5d-p118">Dopo aver creato il criterio QoS per l'audio, è necessario creare un secondo criterio per il video. Per creare un criterio per il video, seguire la stessa procedura base osservata per creare il criterio audio, apportandovi le modifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p118">After you have created the QoS policy for audio you should then create a second policy for video. To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="f6e5d-196">Utilizzare un nome di criterio diverso (e univoco).</span><span class="sxs-lookup"><span data-stu-id="f6e5d-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="f6e5d-p119">Impostare il valore DSCP su **34** anziché su 46. Come accennato, non è necessario utilizzare il valore DSCP 34, bensì è sufficiente utilizzare un valore diverso da quello specificato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p119">Set the DSCP value to **34** instead of 46. (As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="f6e5d-199">Utilizzare l'intervallo di porte configurata in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f6e5d-200">Ad esempio, se si dispone delle porte riservate da 58000 a 58019 per il video, impostare l'intervallo di porte su questo: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="f6e5d-201">Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, effettuare queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="f6e5d-202">Utilizzare un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="f6e5d-p121">Impostare il valore DSCP su **24** anziché su 46. Di nuovo, non è rilevante che questo valore sia 24, bensì è sufficiente che sia diverso dai valori utilizzati per l'audio e per il video.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p121">Set the DSCP value to **24** instead of 46. (Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="f6e5d-205">Utilizzare l'intervallo di porte configurata in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="f6e5d-206">Ad esempio, se si dispone delle porte riservate da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="f6e5d-207">Per un criterio di trasferimento file:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="f6e5d-208">Utilizzare un nome di criterio diverso (e univoco), ad esempio i **trasferimenti di file di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="f6e5d-209">Impostare il valore DSCP su **14**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="f6e5d-210">Di nuovo, non è rilevante che questo valore sia 14, bensì è sufficiente che sia un codice DSCP univoco.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="f6e5d-211">Utilizzare l'intervallo di porte configurata in precedenza per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="f6e5d-212">Ad esempio, se si dispone delle porte riservate da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="f6e5d-p125">I nuovi criteri creati non saranno effettivi finché Criteri di gruppo non verrà aggiornato nei computer client. Benché Criteri di gruppo venga aggiornato automaticamente a intervalli regolari, è possibile effettuare un aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare Criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p125">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers. Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="f6e5d-p126">Questo comando può essere eseguito da qualsiasi finestra dei comandi eseguita con credenziali di amministratore. Per eseguire una finestra dei comandi con credenziali di amministratore, fare clic sul pulsante **Start**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-p126">This command can be run from any command window that is running under administrator credentials. To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="f6e5d-217">Tenere presente che questi criteri devono essere indirizzati verso i computer client.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="f6e5d-218">Non devono essere applicati ai server che eseguono Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="f6e5d-219">Per assicurare che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, è consigliabile creare una nuova voce del Registro di sistema su ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="f6e5d-220">Fare clic su **Start** quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f6e5d-221">Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f6e5d-222">Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi** e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f6e5d-223">Fare clic con il pulsante destro **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f6e5d-224">Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f6e5d-225">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f6e5d-226">Dopo aver creato il nuovo valore del registro di sistema, digitare non **utilizzare NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f6e5d-227">Fare doppio clic su **Do not use NLA**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="f6e5d-228">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="f6e5d-229">Chiudere l'editor del registro di sistema e eboot il computer.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="f6e5d-230">Configurare la qualità del servizio nei computer con più schede di rete</span><span class="sxs-lookup"><span data-stu-id="f6e5d-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="f6e5d-231">Se si dispone di un computer che dispone di più schede di rete, è possibile che occasionalmente venga eseguito un problema in cui i valori DSCP sono visualizzati come 0x00 anziché come valore configurato.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="f6e5d-232">Questo solitamente si verifica nei computer in cui una o più schede di rete non sono in grado di accedere al dominio di Active Directory, come avviene ad esempio nel caso delle schede utilizzate per una rete privata.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="f6e5d-233">In questi casi i valori DSCP verranno assegnati alle schede che possono accedere al dominio, ma non alle altre.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="f6e5d-234">Se si desidera contrassegnare i valori di DSCP per tutte le schede di rete di un computer, incluse le schede che non dispongono dell'accesso al proprio dominio, è necessario aggiungere e configurare un valore per il registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="f6e5d-235">A tale scopo, effettuare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f6e5d-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="f6e5d-236">Fare clic su **Start** quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="f6e5d-237">Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="f6e5d-238">Nell'editor del registro di sistema **espandere \_ HKEY \_ computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi** e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="f6e5d-239">Se non è presente una chiave del Registro di sistema denominata **QoS**, fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **Nuovo** e quindi fare clic su **Chiave**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="f6e5d-240">Dopo aver creato la nuova chiave, digitare **QoS** e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="f6e5d-241">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **Nuovo** e quindi **Valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="f6e5d-242">Dopo aver creato il nuovo valore del registro di sistema, digitare non **utilizzare NLA** e quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="f6e5d-243">Fare doppio clic su **Do not use NLA**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="f6e5d-244">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="f6e5d-245">Dopo aver creato e configurato il nuovo valore del registro di sistema, sarà necessario riavviare il computer per rendere effettive le modifiche.</span><span class="sxs-lookup"><span data-stu-id="f6e5d-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6e5d-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6e5d-246">See also</span></span>

[<span data-ttu-id="f6e5d-247">Creare un oggetto Criteri di gruppo in Windows 10</span><span class="sxs-lookup"><span data-stu-id="f6e5d-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
