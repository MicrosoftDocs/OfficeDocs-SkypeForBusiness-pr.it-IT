---
title: 'Lync Server 2013: visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition'
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
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="1623a-102">Visualizzare le informazioni sulle impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1623a-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1623a-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1623a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1623a-104">È possibile visualizzare le informazioni di configurazione sui dispositivi in cui è in uso Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1623a-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="1623a-105">Le informazioni sono organizzate in raccolte.</span><span class="sxs-lookup"><span data-stu-id="1623a-105">The information is organized into collections.</span></span> <span data-ttu-id="1623a-106">Quando si installa Lync Server, si ottiene una raccolta di impostazioni di Lync Phone Edition che si applicano a tutti i dispositivi in cui è in uso Lync Phone Edition nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1623a-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="1623a-107">È anche possibile creare nuove raccolte di impostazioni per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="1623a-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="1623a-108">Le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="1623a-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="1623a-109">Ogni raccolta di impostazioni è costituita da un nome, l'ambito (globale o del sito), l'impostazione di sicurezza SIP, il livello di registrazione, il livello di qualità del servizio (QoS) vocale, l'impostazione di blocco telefonico e i dettagli del blocco telefonico, ovvero la lunghezza minima dell'identificazione personale di sblocco numero (PIN) e ora prima che il telefono si blocchi.</span><span class="sxs-lookup"><span data-stu-id="1623a-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="1623a-110">Per visualizzare le informazioni di configurazione sui dispositivi in cui è in uso Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1623a-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="1623a-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1623a-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1623a-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1623a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1623a-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1623a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1623a-114">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="1623a-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1623a-115">Nella pagina **Configurazione dispositivo** fare clic sulla raccolta di impostazioni di cui si vogliono visualizzare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="1623a-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="1623a-116">Nella pagina principale sono elencati il nome, l'ambito, l'impostazione di sicurezza SIP, il livello di qualità vocale e l'impostazione di blocco telefonico.</span><span class="sxs-lookup"><span data-stu-id="1623a-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="1623a-117">Per visualizzare i dettagli del livello di registrazione e del blocco telefonico, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="1623a-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1623a-118">Visualizzazione delle informazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1623a-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1623a-119">Per visualizzare le impostazioni di configurazione di Lync Phone Edition, è possibile usare Lync Server Management Shell e il cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1623a-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="1623a-120">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1623a-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1623a-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="1623a-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="1623a-122">Per visualizzare le informazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1623a-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="1623a-123">Per visualizzare informazioni su tutte le impostazioni di configurazione di Lync Phone Edition, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="1623a-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="1623a-124">Il comando restituisce informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="1623a-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="1623a-125">Per informazioni dettagliate, vedere [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1623a-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1623a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1623a-126">See Also</span></span>


[<span data-ttu-id="1623a-127">Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1623a-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="1623a-128">Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1623a-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="1623a-129">Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1623a-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="1623a-130">Applicare il blocco telefonico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1623a-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

