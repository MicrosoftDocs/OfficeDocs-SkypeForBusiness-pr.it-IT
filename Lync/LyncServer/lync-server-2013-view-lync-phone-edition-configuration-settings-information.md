---
title: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition'
description: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62719b24920ee72a92b2f80498d5ea2a59288c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576432"
---
# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="9cf5a-103">Visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cf5a-103">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cf5a-104">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9cf5a-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9cf5a-105">È possibile visualizzare le informazioni di configurazione relative ai dispositivi che eseguono Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-105">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="9cf5a-106">Le informazioni sono organizzate in raccolte.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-106">The information is organized into collections.</span></span> <span data-ttu-id="9cf5a-107">Quando si installa Lync Server, è possibile ottenere una raccolta di impostazioni di Lync Phone Edition che si applicano a tutti i dispositivi che eseguono Lync Phone Edition nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-107">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="9cf5a-108">È anche possibile creare nuove raccolte di impostazioni per uno specifico sito.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-108">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="9cf5a-109">Le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-109">Site settings take precedence over global settings.</span></span> <span data-ttu-id="9cf5a-110">In ogni raccolta di impostazioni sono disponibili nome, ambito (globale o sito), impostazione per la sicurezza SIP, livello di registrazione, livello di qualità vocale del servizio (QoS), impostazione per il blocco telefono e dettagli sul blocco telefono, ovvero la lunghezza minima del PIN di sblocco e l'intervallo di tempo prima che il telefono si blocchi.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-110">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="9cf5a-111">Per visualizzare le informazioni di configurazione sui dispositivi che eseguono Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9cf5a-111">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="9cf5a-112">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9cf5a-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9cf5a-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9cf5a-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9cf5a-115">Nella barra di spostamento sinistra fare clic su **Client**, quindi sul pulsante di spostamento **Configurazione dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-115">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="9cf5a-p103">Nella pagina **Configurazione dispositivo** fare clic sulla raccolta di impostazioni di cui si desidera visualizzare le informazioni. Il nome, l'ambito, l'impostazione di sicurezza SIP, il livello di qualità vocale e l'impostazione di blocco telefono sono elencate nella pagina principale. Per visualizzare il livello di registrazione e i dettagli del blocco telefono, fare clic sul menu **Modifica**, quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9cf5a-119">Visualizzazione delle informazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cf5a-119">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9cf5a-120">È possibile visualizzare le impostazioni di configurazione di Lync Phone Edition utilizzando Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9cf5a-120">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="9cf5a-121">È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-121">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9cf5a-122">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9cf5a-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="9cf5a-123">Per visualizzare le informazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="9cf5a-123">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="9cf5a-124">Per visualizzare informazioni su tutte le impostazioni di configurazione di Lync Phone Edition, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="9cf5a-124">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="9cf5a-125">Verranno restituite informazioni simili alle seguenti</span><span class="sxs-lookup"><span data-stu-id="9cf5a-125">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="9cf5a-126">Per informazioni dettagliate, vedere [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="9cf5a-126">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9cf5a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cf5a-127">See Also</span></span>


[<span data-ttu-id="9cf5a-128">Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cf5a-128">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="9cf5a-129">Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cf5a-129">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="9cf5a-130">Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cf5a-130">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="9cf5a-131">Applicare il blocco del telefono in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cf5a-131">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

