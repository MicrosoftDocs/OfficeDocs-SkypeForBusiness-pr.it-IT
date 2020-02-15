---
title: 'Lync Server 2013: visualizzare le impostazioni di configurazione delle riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5daca87d47fdeb4bac46d83d48652037d75220b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="efa45-102">Visualizzare le impostazioni di configurazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa45-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efa45-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="efa45-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="efa45-104">Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le impostazioni di configurazione delle riunioni per controllare la modalità di implementazione delle riunioni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="efa45-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="efa45-105">Sono incluse le configurazioni di riunione seguenti:</span><span class="sxs-lookup"><span data-stu-id="efa45-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="efa45-106">Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efa45-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="efa45-107">Configurazioni facoltative a livello di sito e di utente che possono essere create e utilizzate per specificare come devono essere implementate le riunioni per siti o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="efa45-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="efa45-108">Per visualizzare le impostazioni di configurazione di riunione</span><span class="sxs-lookup"><span data-stu-id="efa45-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="efa45-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="efa45-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="efa45-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="efa45-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="efa45-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="efa45-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="efa45-112">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="efa45-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="efa45-113">Nella pagina **Configurazione riunione** fare clic sulla configurazione di riunione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="efa45-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="efa45-p103">In **Modifica filtro file** selezionare la casella di controllo **Mostra dettagli…**</span><span class="sxs-lookup"><span data-stu-id="efa45-p103">In **Edit File Filter**, select the **Show Details…** check box.</span></span>
    
    <span data-ttu-id="efa45-116">\*\*Modifica configurazione riunione- \<viene\> \*\* visualizzato il criterio per visualizzare le impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="efa45-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="efa45-117">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="efa45-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="efa45-118">Visualizzazione delle informazioni sulla configurazione delle riunioni tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="efa45-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="efa45-119">È possibile visualizzare le impostazioni di configurazione delle riunioni utilizzando Windows PowerShell e il cmdlet Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="efa45-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="efa45-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="efa45-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="efa45-121">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="efa45-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="efa45-122">Per visualizzare le informazioni sulla configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="efa45-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="efa45-123">Per visualizzare informazioni su tutte le impostazioni di configurazione delle riunioni, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="efa45-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="efa45-124">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="efa45-124">That will return information similar to this:</span></span>
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

<span data-ttu-id="efa45-125">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="efa45-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

