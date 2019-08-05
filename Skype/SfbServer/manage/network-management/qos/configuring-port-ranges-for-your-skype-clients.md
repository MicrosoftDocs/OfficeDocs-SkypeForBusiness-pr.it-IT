---
title: Configurazione di intervalli di porte e criteri di qualità dei servizi per i clienti
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Questo articolo descrive come configurare gli intervalli di porte per i clienti e configurare i criteri di qualità dei servizi in Skype for Business Server per i client in Windows 10.
ms.openlocfilehash: 4d7999634864e222dd627ea3b46a3a3da5c67fe5
ms.sourcegitcommit: 67282b5f2f1aac3e675c4a485f4846deba15deb4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "36196066"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="436d3-103">Configurazione di intervalli di porte e di criteri di qualità dei servizi per i clienti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="436d3-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="436d3-104">Questo articolo descrive come configurare gli intervalli di porte per i clienti e configurare i criteri di qualità dei servizi in Skype for Business Server per i client in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="436d3-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="436d3-105">Configurare gli intervalli di porte</span><span class="sxs-lookup"><span data-stu-id="436d3-105">Configure port ranges</span></span>

<span data-ttu-id="436d3-106">Per impostazione predefinita, le applicazioni client Skype for business possono usare qualsiasi porta tra le porte 1024 e 65535 quando si partecipa a una sessione di comunicazione; il motivo è che gli intervalli di porte specifici non vengono abilitati automaticamente per i client.</span><span class="sxs-lookup"><span data-stu-id="436d3-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="436d3-107">Per poter usare la qualità del servizio, è tuttavia necessario riassegnare i vari tipi di traffico (audio, video, multimediale, condivisione applicazioni e trasferimento di file) a una serie di intervalli di porte univoci.</span><span class="sxs-lookup"><span data-stu-id="436d3-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="436d3-108">Questa operazione può essere eseguita usando il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="436d3-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="436d3-109">Gli utenti finali non possono apportare queste modifiche.</span><span class="sxs-lookup"><span data-stu-id="436d3-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="436d3-110">Le modifiche alle porte possono essere eseguite solo dagli amministratori tramite il cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="436d3-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="436d3-111">Puoi determinare gli intervalli di porte attualmente usati per le sessioni di comunicazione eseguendo il comando seguente dall'interno di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="436d3-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="436d3-112">Supponendo che non siano state apportate modifiche alle impostazioni di conferenza dopo l'installazione di Skype for Business Server, è consigliabile recuperare le informazioni che includono questi valori di proprietà:</span><span class="sxs-lookup"><span data-stu-id="436d3-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="436d3-113">Se si osserva attentamente l'output precedente, verranno visualizzati due elementi importanti.</span><span class="sxs-lookup"><span data-stu-id="436d3-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="436d3-114">Prima di tutto, la proprietà ClientMediaPortRangeEnabled è impostata su false:</span><span class="sxs-lookup"><span data-stu-id="436d3-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="436d3-115">Questo è importante perché, quando questa proprietà è impostata su false, i client Skype for Business useranno qualsiasi porta disponibile tra le porte 1024 e 65535 quando sono coinvolte in una sessione di comunicazione; Questo vale indipendentemente da qualsiasi altra impostazione della porta, ad esempio ClientMediaPort o ClientVideoPort.</span><span class="sxs-lookup"><span data-stu-id="436d3-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="436d3-116">Se si vuole limitare l'utilizzo a un set di porte specificato (e si vuole eseguire questa operazione se si prevede di implementare la qualità del servizio), è necessario prima di tutto abilitare gli intervalli di porta del supporto client.</span><span class="sxs-lookup"><span data-stu-id="436d3-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="436d3-117">Questa operazione può essere eseguita usando il comando di Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="436d3-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="436d3-118">Il comando precedente consente di abilitare gli intervalli di porta multimediali del client per la raccolta globale delle impostazioni di configurazione delle conferenze; Queste impostazioni possono tuttavia essere applicate anche all'ambito del sito e/o all'ambito del servizio (solo per il servizio di conferenza Server).</span><span class="sxs-lookup"><span data-stu-id="436d3-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="436d3-119">Per abilitare gli intervalli della porta multimediale client per un sito o un server specifico, specificare l'identità del sito o del server quando si chiama Set-CsConferencingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="436d3-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="436d3-120">In alternativa, puoi usare questo comando per abilitare simultaneamente gli intervalli di porta per tutte le impostazioni di configurazione della conferenza:</span><span class="sxs-lookup"><span data-stu-id="436d3-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="436d3-121">La seconda cosa importante che si noterà è che l'output di esempio mostra che, per impostazione predefinita, gli intervalli di porte multimediali impostati per ogni tipo di traffico di rete sono identici:</span><span class="sxs-lookup"><span data-stu-id="436d3-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="436d3-122">Per implementare QoS, ognuno di questi intervalli di porte dovrà essere univoco.</span><span class="sxs-lookup"><span data-stu-id="436d3-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="436d3-123">Ad esempio, è possibile configurare gli intervalli di porte come questo:</span><span class="sxs-lookup"><span data-stu-id="436d3-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="436d3-124">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="436d3-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="436d3-125">Inizio porta</span><span class="sxs-lookup"><span data-stu-id="436d3-125">Port Start</span></span></th>
<th><span data-ttu-id="436d3-126">Intervallo di porte</span><span class="sxs-lookup"><span data-stu-id="436d3-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="436d3-127">Audio</span><span class="sxs-lookup"><span data-stu-id="436d3-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="436d3-128">50020</span><span class="sxs-lookup"><span data-stu-id="436d3-128">50020</span></span></p></td>
<td><p><span data-ttu-id="436d3-129">20</span><span class="sxs-lookup"><span data-stu-id="436d3-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="436d3-130">Video</span><span class="sxs-lookup"><span data-stu-id="436d3-130">Video</span></span></p></td>
<td><p><span data-ttu-id="436d3-131">58000</span><span class="sxs-lookup"><span data-stu-id="436d3-131">58000</span></span></p></td>
<td><p><span data-ttu-id="436d3-132">20</span><span class="sxs-lookup"><span data-stu-id="436d3-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="436d3-133">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="436d3-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="436d3-134">42000</span><span class="sxs-lookup"><span data-stu-id="436d3-134">42000</span></span></p></td>
<td><p><span data-ttu-id="436d3-135">20</span><span class="sxs-lookup"><span data-stu-id="436d3-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="436d3-136">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="436d3-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="436d3-137">42020</span><span class="sxs-lookup"><span data-stu-id="436d3-137">42020</span></span></p></td>
<td><p><span data-ttu-id="436d3-138">20</span><span class="sxs-lookup"><span data-stu-id="436d3-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="436d3-139">Nella tabella precedente gli intervalli di porte client rappresentano un sottoinsieme degli intervalli di porte configurati per i server.</span><span class="sxs-lookup"><span data-stu-id="436d3-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="436d3-140">Ad esempio, nei server la condivisione delle applicazioni è stata configurata per l'uso delle porte da 40803 a 49151; nei computer client la condivisione delle applicazioni è configurata per l'uso delle porte da 42000 a 42019.</span><span class="sxs-lookup"><span data-stu-id="436d3-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="436d3-141">Anche questa operazione viene eseguita principalmente per semplificare l'amministrazione di QoS: le porte client non devono rappresentare un sottoinsieme delle porte usate nel server.</span><span class="sxs-lookup"><span data-stu-id="436d3-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="436d3-142">Ad esempio, nei computer client è possibile configurare la condivisione delle applicazioni per usare, per dire, le porte da 10000 a 10019. Tuttavia, è consigliabile rendere gli intervalli della porta del client un sottoinsieme degli intervalli di porte del server.</span><span class="sxs-lookup"><span data-stu-id="436d3-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="436d3-143">Inoltre, potresti aver notato che le porte di 8348 sono state accantonate per la condivisione delle applicazioni sui server, ma solo 20 porte sono state accantonate per la condivisione delle applicazioni nei client.</span><span class="sxs-lookup"><span data-stu-id="436d3-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="436d3-144">È consigliabile anche questo, ma non è una regola difficile e veloce.</span><span class="sxs-lookup"><span data-stu-id="436d3-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="436d3-145">In generale, è possibile prendere in considerazione ogni porta disponibile per rappresentare una singola sessione di comunicazione: se sono disponibili porte di 100 in un intervallo di porte, significa che il computer in questione può partecipare, al massimo, a 100 sessioni di comunicazione in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="436d3-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="436d3-146">Poiché i server probabilmente parteciperanno a molte più conversazioni rispetto ai client, è opportuno aprire molte più porte nei server che nei client.</span><span class="sxs-lookup"><span data-stu-id="436d3-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="436d3-147">L'impostazione di 20 porte per la condivisione delle applicazioni in un client significa che un utente può partecipare a 20 sessioni di condivisione applicazioni nel dispositivo specificato e contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="436d3-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="436d3-148">Questo dovrebbe risultare sufficiente per la stragrande maggioranza degli utenti.</span><span class="sxs-lookup"><span data-stu-id="436d3-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="436d3-149">Per assegnare gli intervalli di porte precedenti alla raccolta globale di impostazioni di configurazione per i servizi di conferenza, è possibile usare il comando di gestione shell di Skype for Business Server seguente:</span><span class="sxs-lookup"><span data-stu-id="436d3-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="436d3-150">In alternativa, usare questo comando per assegnare gli stessi intervalli di porte per tutte le impostazioni di configurazione per i servizi di conferenza:</span><span class="sxs-lookup"><span data-stu-id="436d3-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="436d3-151">I singoli utenti devono disconnettersi da Skype for business e quindi accedere di nuovo prima che le modifiche abbiano effetto.</span><span class="sxs-lookup"><span data-stu-id="436d3-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="436d3-152">Puoi anche abilitare gli intervalli di porta multimediali del client e quindi assegnare questi intervalli di porte usando un singolo comando.</span><span class="sxs-lookup"><span data-stu-id="436d3-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="436d3-153">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="436d3-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="436d3-154">Configurare i criteri di qualità dei servizi per i client in uso in Windows 10</span><span class="sxs-lookup"><span data-stu-id="436d3-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="436d3-155">Oltre a specificare gli intervalli di porte per l'uso da parte dei client Skype for business, devi anche creare criteri di qualità distinti per i servizi che verranno applicati ai computer client.</span><span class="sxs-lookup"><span data-stu-id="436d3-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="436d3-156">I criteri di qualità dei servizi creati per le conferenze, le applicazioni e i server di mediazione non devono essere applicati ai computer client. Queste informazioni si applicano solo ai computer che eseguono il client Skype for business e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="436d3-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="436d3-157">Nell'esempio seguente viene usato questo set di intervalli di porte per creare un criterio audio e un criterio video:</span><span class="sxs-lookup"><span data-stu-id="436d3-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="436d3-158">Tipo di traffico client</span><span class="sxs-lookup"><span data-stu-id="436d3-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="436d3-159">Inizio porta</span><span class="sxs-lookup"><span data-stu-id="436d3-159">Port Start</span></span></th>
<th><span data-ttu-id="436d3-160">Intervallo di porte</span><span class="sxs-lookup"><span data-stu-id="436d3-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="436d3-161">Audio</span><span class="sxs-lookup"><span data-stu-id="436d3-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="436d3-162">50020</span><span class="sxs-lookup"><span data-stu-id="436d3-162">50020</span></span></p></td>
<td><p><span data-ttu-id="436d3-163">20</span><span class="sxs-lookup"><span data-stu-id="436d3-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="436d3-164">Video</span><span class="sxs-lookup"><span data-stu-id="436d3-164">Video</span></span></p></td>
<td><p><span data-ttu-id="436d3-165">58000</span><span class="sxs-lookup"><span data-stu-id="436d3-165">58000</span></span></p></td>
<td><p><span data-ttu-id="436d3-166">20</span><span class="sxs-lookup"><span data-stu-id="436d3-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="436d3-167">Condivisione applicazioni</span><span class="sxs-lookup"><span data-stu-id="436d3-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="436d3-168">42000</span><span class="sxs-lookup"><span data-stu-id="436d3-168">42000</span></span></p></td>
<td><p><span data-ttu-id="436d3-169">20</span><span class="sxs-lookup"><span data-stu-id="436d3-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="436d3-170">Trasferimento di file</span><span class="sxs-lookup"><span data-stu-id="436d3-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="436d3-171">42020</span><span class="sxs-lookup"><span data-stu-id="436d3-171">42020</span></span></p></td>
<td><p><span data-ttu-id="436d3-172">20</span><span class="sxs-lookup"><span data-stu-id="436d3-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="436d3-173">Per creare un criterio di qualità dei servizi audio per i computer Windows 10, accedere prima a un computer in cui è stata installata la gestione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="436d3-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="436d3-174">Aprire Gestione criteri di gruppo (fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Gestione criteri di gruppo**) e quindi completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="436d3-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="436d3-175">In Gestione criteri di gruppo individuare il contenitore in cui deve essere creato il nuovo criterio.</span><span class="sxs-lookup"><span data-stu-id="436d3-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="436d3-176">Ad esempio, se tutti i computer client si trovano in un'unità organizzativa denominata clients, è necessario creare il nuovo criterio nell'unità organizzativa client.</span><span class="sxs-lookup"><span data-stu-id="436d3-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="436d3-177">Fare clic con il pulsante destro del mouse sul contenitore appropriato e quindi scegliere **Crea un GPO in questo dominio e collegarlo qui**.</span><span class="sxs-lookup"><span data-stu-id="436d3-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="436d3-178">Nella finestra di dialogo **nuovo GPO** Digitare un nome per il nuovo oggetto Criteri di gruppo nella casella **nome** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="436d3-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="436d3-179">Fare clic con il pulsante destro del mouse sul criterio appena creato e quindi scegliere **modifica**.</span><span class="sxs-lookup"><span data-stu-id="436d3-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="436d3-180">In Editor gestione criteri di gruppo espandere **Configurazione computer**, espandere **impostazioni di Windows**, fare clic con il pulsante destro del mouse su **QoS basata su criteri**e quindi scegliere **Crea nuovo criterio**.</span><span class="sxs-lookup"><span data-stu-id="436d3-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="436d3-181">Nella pagina di apertura della finestra di dialogo **QoS basata sui criteri** Digitare un nome per il nuovo criterio nella casella **nome** .</span><span class="sxs-lookup"><span data-stu-id="436d3-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="436d3-182">Selezionare **Specifica valore DSCP** e impostare il valore su **46**.</span><span class="sxs-lookup"><span data-stu-id="436d3-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="436d3-183">Lascia **specificare la frequenza di accelerazione in uscita** deselezionata e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="436d3-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="436d3-184">Nella pagina successiva selezionare **solo le applicazioni con il nome eseguibile**, immettere **Lync. exe** come nome e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="436d3-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="436d3-185">Questa impostazione indica al criterio di assegnare la priorità solo al traffico corrispondente dal client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="436d3-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="436d3-186">Nella terza pagina verificare che sia selezionato l'indirizzo IP di **origine** e **qualsiasi indirizzo IP di destinazione** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="436d3-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="436d3-187">Queste due impostazioni assicurano che i pacchetti vengano gestiti indipendentemente da quale computer (indirizzo IP) ha inviato i pacchetti e quale computer (indirizzo IP) riceverà tali pacchetti.</span><span class="sxs-lookup"><span data-stu-id="436d3-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="436d3-188">Nella pagina quattro selezionare **TCP e UDP** dal pulsante **Seleziona il protocollo questo criterio di QoS si applica all'elenco a** discesa.</span><span class="sxs-lookup"><span data-stu-id="436d3-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="436d3-189">TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) sono i due protocolli di rete usati più comunemente da Skype for Business Server e dalle sue applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="436d3-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="436d3-190">Sotto l'intestazione **specificare il numero della porta di origine**, selezionare **dalla porta o dall'intervallo di origine**.</span><span class="sxs-lookup"><span data-stu-id="436d3-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="436d3-191">Nella casella di testo associata digitare l'intervallo di porte riservato per le trasmissioni audio.</span><span class="sxs-lookup"><span data-stu-id="436d3-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="436d3-192">Ad esempio, se hai riservato le porte 50020 tramite le porte 50039 per il traffico audio, immetti l'intervallo di porte usando questo formato: **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="436d3-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="436d3-193">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="436d3-193">Click **Finish**.</span></span>

<span data-ttu-id="436d3-194">Dopo aver creato i criteri QoS per l'audio, è necessario creare un secondo criterio per il video.</span><span class="sxs-lookup"><span data-stu-id="436d3-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="436d3-195">Per creare un criterio per il video, seguire la stessa procedura di base seguita durante la creazione dei criteri audio, eseguendo queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="436d3-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="436d3-196">Usare un nome di criterio diverso (e univoco).</span><span class="sxs-lookup"><span data-stu-id="436d3-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="436d3-197">Impostare il valore DSCP su **34** anziché su 46.</span><span class="sxs-lookup"><span data-stu-id="436d3-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="436d3-198">Come indicato in precedenza, non è necessario usare il valore DSCP 34; devi semplicemente assegnare un valore DSCP diverso rispetto a quello usato per l'audio.</span><span class="sxs-lookup"><span data-stu-id="436d3-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="436d3-199">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="436d3-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="436d3-200">Ad esempio, se sono state riservate le porte da 58000 a 58019 per il video, impostare l'intervallo di porte su questo: **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="436d3-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="436d3-201">Se si decide di creare un criterio per la gestione del traffico di condivisione delle applicazioni, eseguire queste sostituzioni:</span><span class="sxs-lookup"><span data-stu-id="436d3-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="436d3-202">Usa un nome di criterio diverso (e univoco), ad esempio la **condivisione delle applicazioni di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="436d3-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="436d3-203">Impostare il valore DSCP su **24** anziché su 46.</span><span class="sxs-lookup"><span data-stu-id="436d3-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="436d3-204">(Anche in questo caso, il valore non deve essere 24; è semplicemente diverso dai valori DSCP usati per l'audio e per il video.)</span><span class="sxs-lookup"><span data-stu-id="436d3-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="436d3-205">Usa l'intervallo di porte configurato in precedenza per il traffico video.</span><span class="sxs-lookup"><span data-stu-id="436d3-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="436d3-206">Ad esempio, se si hanno le porte riservate da 42000 a 42019 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="436d3-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="436d3-207">Per un criterio di trasferimento file:</span><span class="sxs-lookup"><span data-stu-id="436d3-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="436d3-208">Usare un nome di criterio diverso (e univoco), ad esempio **trasferimenti di file di Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="436d3-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="436d3-209">Imposta il valore DSCP su **14**.</span><span class="sxs-lookup"><span data-stu-id="436d3-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="436d3-210">(Anche in questo caso, il valore non deve essere 14, ma è semplicemente un codice DSCP univoco).</span><span class="sxs-lookup"><span data-stu-id="436d3-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="436d3-211">Usa l'intervallo di porte configurato in precedenza per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="436d3-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="436d3-212">Ad esempio, se si hanno le porte riservate da 42020 a 42039 per la condivisione delle applicazioni, impostare l'intervallo di porte su questo: **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="436d3-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="436d3-213">I nuovi criteri creati non avranno effetto finché i criteri di gruppo non saranno stati aggiornati nei computer client.</span><span class="sxs-lookup"><span data-stu-id="436d3-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="436d3-214">Anche se i criteri di gruppo vengono periodicamente aggiornati autonomamente, è possibile forzare l'aggiornamento immediato eseguendo il comando seguente in ogni computer in cui è necessario aggiornare i criteri di gruppo:</span><span class="sxs-lookup"><span data-stu-id="436d3-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="436d3-215">Questo comando può essere eseguito da qualsiasi finestra di comando in esecuzione in credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="436d3-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="436d3-216">Per eseguire una finestra di comando in credenziali di amministratore, fare clic su **Start**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="436d3-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="436d3-217">Tieni presente che questi criteri devono essere mirati verso i computer client.</span><span class="sxs-lookup"><span data-stu-id="436d3-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="436d3-218">Non devono essere applicati ai server che eseguono Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="436d3-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="436d3-219">Per assicurarti che i pacchetti di rete siano contrassegnati con il valore DSCP appropriato, devi anche creare una nuova voce del registro di sistema in ogni computer completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="436d3-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="436d3-220">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="436d3-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="436d3-221">Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="436d3-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="436d3-222">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="436d3-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="436d3-223">Fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="436d3-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="436d3-224">Dopo la creazione della nuova chiave del registro di sistema, digitare **QoS**e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="436d3-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="436d3-225">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="436d3-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="436d3-226">Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA**, quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="436d3-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="436d3-227">Fare doppio clic su non **usare NLA**.</span><span class="sxs-lookup"><span data-stu-id="436d3-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="436d3-228">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="436d3-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="436d3-229">Chiudere l'editor del registro di sistema e eboot il computer.</span><span class="sxs-lookup"><span data-stu-id="436d3-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="436d3-230">Configurare la qualità del servizio nei computer con più schede di rete</span><span class="sxs-lookup"><span data-stu-id="436d3-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="436d3-231">Se si dispone di un computer in cui sono presenti più schede di rete, è possibile che venga eseguito occasionalmente un problema in cui i valori DSCP sono visualizzati come 0x00 invece del valore configurato.</span><span class="sxs-lookup"><span data-stu-id="436d3-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="436d3-232">Ciò si verifica in genere nei computer in cui una o più schede di rete non sono in grado di accedere al dominio Active Directory, ad esempio se questi adapter vengono usati per una rete privata.</span><span class="sxs-lookup"><span data-stu-id="436d3-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="436d3-233">In casi come questo, i valori DSCP verranno contrassegnati per gli adapter che possono accedere al dominio, ma non verranno contrassegnati per gli adapter che non possono accedere al dominio.</span><span class="sxs-lookup"><span data-stu-id="436d3-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="436d3-234">Se si vuole contrassegnare i valori DSCP per tutte le schede di rete in un computer, inclusi gli adapter che non hanno accesso al dominio, è necessario aggiungere e configurare un valore nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="436d3-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="436d3-235">Questa operazione può essere eseguita completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="436d3-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="436d3-236">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="436d3-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="436d3-237">Nella finestra di dialogo **Esegui** Digitare **Regedit**e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="436d3-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="436d3-238">Nell'editor del registro di sistema **espandere\_HKEY\_computer locale**, espandere **System**, espandere **CurrentControlSet**, espandere **Servizi**e quindi espandere **Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="436d3-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="436d3-239">Se non viene visualizzata una chiave del registro di sistema con l'etichetta **QoS** , fare clic con il pulsante destro del mouse su **Tcpip**, scegliere **nuovo**e quindi fare clic su **chiave**.</span><span class="sxs-lookup"><span data-stu-id="436d3-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="436d3-240">Dopo aver creato la nuova chiave, digitare **QoS**e quindi premere INVIO per rinominare la chiave.</span><span class="sxs-lookup"><span data-stu-id="436d3-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="436d3-241">Fare clic con il pulsante destro del mouse su **QoS**, scegliere **nuovo**e quindi fare clic su **valore stringa**.</span><span class="sxs-lookup"><span data-stu-id="436d3-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="436d3-242">Dopo la creazione del nuovo valore del registro di sistema, digitare non **usare NLA**, quindi premere INVIO per rinominare il valore.</span><span class="sxs-lookup"><span data-stu-id="436d3-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="436d3-243">Fare doppio clic su non **usare NLA**.</span><span class="sxs-lookup"><span data-stu-id="436d3-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="436d3-244">Nella finestra di dialogo **Modifica stringa** Digitare **1** nella casella **dati valore** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="436d3-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="436d3-245">Dopo aver creato e configurato il nuovo valore del registro di sistema, sarà necessario riavviare il computer per applicare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="436d3-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="436d3-246">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="436d3-246">See also</span></span>

[<span data-ttu-id="436d3-247">Creare un oggetto Criteri di gruppo in Windows 10</span><span class="sxs-lookup"><span data-stu-id="436d3-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
