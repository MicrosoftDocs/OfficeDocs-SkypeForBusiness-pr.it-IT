---
title: 'Lync Server 2013: specifica della conservazione dei dati di registrazione dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05ab963084935f67a68ccd2701995a4f04b78543
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="81cdd-102">Specifica della conservazione dei dati di registrazione dettagli chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81cdd-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81cdd-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="81cdd-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="81cdd-p101">Per impostazione predefinita, i dati di registrazione dettagli chiamata vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Registrazione dettagli chiamata** per mantenere i dati per un periodo maggiore o inferiore. Se si disabilita registrazione dettagli chiamata, verranno eliminati anche i dati acquisiti prima dell'abilitazione di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="81cdd-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81cdd-p102">È consigliabile configurare registrazione dettagli chiamata e QoE (Quality of Experience) in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla pagina Web dei rapporti di Monitoring Server, include informazioni di registrazione dettagli chiamata e QoE. Se la durata prima dell'eliminazione è diversa, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="81cdd-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="81cdd-110">Nelle procedure seguenti viene descritto come configurare le impostazioni per l'eliminazione dei dati di registrazione dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="81cdd-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="81cdd-111">Per specificare il periodo di mantenimento dei dati di registrazione dettagli chiamata</span><span class="sxs-lookup"><span data-stu-id="81cdd-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="81cdd-112">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="81cdd-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="81cdd-113">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="81cdd-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81cdd-114">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="81cdd-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="81cdd-115">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="81cdd-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="81cdd-116">Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="81cdd-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="81cdd-117">Per attivare l'eliminazione, selezionare **Abilita eliminazione registrazioni dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="81cdd-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="81cdd-118">In **Mantieni registrazioni dettagli chiamata per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le registrazioni dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="81cdd-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="81cdd-119">In **Mantieni dati delle segnalazioni errori per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le segnalazioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="81cdd-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="81cdd-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="81cdd-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="81cdd-121">Impostazione della conservazione CDR tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="81cdd-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="81cdd-122">È possibile creare le impostazioni di mantenimento delle registrazioni dettagli chiamata utilizzando Windows PowerShell e il cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="81cdd-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="81cdd-123">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81cdd-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="81cdd-124">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="81cdd-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="81cdd-125">Per specificare il mantenimento delle registrazioni dettagli chiamata per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="81cdd-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="81cdd-126">Questo comando consente di abilitare l'eliminazione dei dati delle registrazioni dettagli chiamata per il sito Redmond e di configurare il sito per mantenere sia tali dati che le segnalazioni di errore per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="81cdd-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="81cdd-127">Per specificare il mantenimento delle registrazioni dettagli chiamata per più posizioni</span><span class="sxs-lookup"><span data-stu-id="81cdd-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="81cdd-128">Questo comando consente di configurare il mantenimento delle registrazioni dettagli chiamata per tutte le impostazioni di configurazione di tali registrazioni in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="81cdd-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="81cdd-129">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="81cdd-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81cdd-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81cdd-130">See Also</span></span>


[<span data-ttu-id="81cdd-131">Registrazione dettagli chiamata (CDR) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81cdd-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

