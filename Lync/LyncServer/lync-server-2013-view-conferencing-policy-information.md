---
title: 'Lync Server 2013: visualizzare le informazioni sui criteri di conferenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c2cccd61d710acd9d2155412ec427c65eafc2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a><span data-ttu-id="258a3-102">Visualizzare le informazioni sui criteri di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="258a3-102">View conferencing policy information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="258a3-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="258a3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="258a3-104">Nel pannello di controllo di Lync Server 2013 si usano i criteri di conferenza per controllare la modalità di implementazione delle conferenze nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="258a3-104">In Lync Server 2013 Control Panel, you use conferencing policies to control how conferencing is implemented in your deployment.</span></span> <span data-ttu-id="258a3-105">Sono inclusi i criteri di conferenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="258a3-105">This includes the following conferencing policies:</span></span>

  - <span data-ttu-id="258a3-106">Un criterio globale creato per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="258a3-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="258a3-107">Criteri facoltativi a livello di sito e a livello di utente che è possibile creare e usare per specificare la modalità di implementazione delle conferenze per siti o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="258a3-107">Optional site-level and user-level policy that you can create and use to specify how conferencing is implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-conferencing-policy-settings"></a><span data-ttu-id="258a3-108">Per visualizzare le impostazioni dei criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="258a3-108">To view conferencing policy settings</span></span>

1.  <span data-ttu-id="258a3-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="258a3-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="258a3-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="258a3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="258a3-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="258a3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="258a3-112">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="258a3-112">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="258a3-113">Nella pagina **criteri di conferenza** fare doppio clic sui criteri di conferenza che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="258a3-113">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>

5.  <span data-ttu-id="258a3-114">In **Modifica filtro file**selezionare la **visualizzazione dettagli...**</span><span class="sxs-lookup"><span data-stu-id="258a3-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="258a3-115">casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="258a3-115">check box.</span></span>
    
    <span data-ttu-id="258a3-116">**Modificare i criteri di \<conferenza\> :** viene visualizzata la visualizzazione delle impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="258a3-116">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="258a3-117">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare o modificare criteri per i servizi di conferenza in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="258a3-117">For details about configuring the settings, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="258a3-118">Visualizzazione dei criteri di conferenza tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="258a3-118">Viewing Conferencing Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="258a3-119">I criteri di conferenza possono essere visualizzati usando Windows PowerShell e il cmdlet Get-CsConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="258a3-119">Conferencing policies can be viewed by using Windows PowerShell and the Get-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="258a3-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="258a3-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="258a3-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="258a3-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-conferencing-policies"></a><span data-ttu-id="258a3-122">Per visualizzare i criteri di conferenza</span><span class="sxs-lookup"><span data-stu-id="258a3-122">To view conferencing policies</span></span>

  - <span data-ttu-id="258a3-123">Per visualizzare informazioni su tutti i criteri di conferenza, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="258a3-123">To view information about all your conferencing policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="258a3-124">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="258a3-124">That will return information similar to this:</span></span>
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

<span data-ttu-id="258a3-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) .</span><span class="sxs-lookup"><span data-stu-id="258a3-125">For more information, see the help topic for the [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

