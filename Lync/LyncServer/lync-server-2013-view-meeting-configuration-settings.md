---
title: 'Lync Server 2013: visualizzare le impostazioni di configurazione della riunione'
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
ms.openlocfilehash: 5737fbba63915501bea80105ef3509511d8cb436
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0dcb8-102">Visualizzare le impostazioni di configurazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0dcb8-102">View meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dcb8-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0dcb8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0dcb8-104">Nel pannello di controllo di Lync Server 2013 si usa l'impostazione configurazione riunione per controllare la modalità di implementazione delle riunioni nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-104">In Lync Server 2013 Control Panel, you use meeting configuration setting to control how meetings are implemented in your deployment.</span></span> <span data-ttu-id="0dcb8-105">Sono incluse le configurazioni delle riunioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0dcb8-105">This includes the following meeting configurations:</span></span>

  - <span data-ttu-id="0dcb8-106">Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="0dcb8-107">Configurazioni facoltative a livello di sito e a livello di utente che è possibile creare e usare per specificare la modalità di implementazione delle riunioni per siti o utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-107">Optional site-level and user-level configurations that you can create and use to specify how meetings are implemented for specific sites or users.</span></span>

<div>

## <a name="to-view-meeting-configuration-settings"></a><span data-ttu-id="0dcb8-108">Per visualizzare le impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="0dcb8-108">To view meeting configuration settings</span></span>

1.  <span data-ttu-id="0dcb8-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0dcb8-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0dcb8-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0dcb8-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0dcb8-112">Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-112">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="0dcb8-113">Nella pagina **Configurazione riunione** fare clic sulla configurazione della riunione che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-113">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>

5.  <span data-ttu-id="0dcb8-114">In **Modifica filtro file**selezionare la **visualizzazione dettagli...**</span><span class="sxs-lookup"><span data-stu-id="0dcb8-114">In **Edit File Filter**, select the **Show Details…**</span></span> <span data-ttu-id="0dcb8-115">casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-115">check box.</span></span>
    
    <span data-ttu-id="0dcb8-116">**Modificare la configurazione delle \<riunioni\> :** verrà visualizzata la visualizzazione delle impostazioni per il criterio selezionato.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-116">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span> <span data-ttu-id="0dcb8-117">Per informazioni dettagliate sulla configurazione delle impostazioni, vedere [creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0dcb8-117">For details about configuring the settings, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span>

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0dcb8-118">Visualizzazione delle informazioni di configurazione delle riunioni tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dcb8-118">Viewing Meeting Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0dcb8-119">Le impostazioni di configurazione della riunione possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-119">Meeting configuration settings can be viewed by using Windows PowerShell and the Get-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="0dcb8-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0dcb8-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="0dcb8-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-meeting-configuration-information"></a><span data-ttu-id="0dcb8-122">Per visualizzare le informazioni sulla configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="0dcb8-122">To view meeting configuration information</span></span>

  - <span data-ttu-id="0dcb8-123">Per visualizzare informazioni su tutte le impostazioni di configurazione della riunione, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="0dcb8-123">To view information about all your meeting configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsMeetingConfiguration
    
    <span data-ttu-id="0dcb8-124">Questo restituirà informazioni simili alla seguente:</span><span class="sxs-lookup"><span data-stu-id="0dcb8-124">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="0dcb8-125">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="0dcb8-125">For more information, see the help topic for the [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

