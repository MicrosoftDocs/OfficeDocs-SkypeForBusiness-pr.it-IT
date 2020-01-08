---
title: 'Lync Server 2013: specificare la conservazione dei dati CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae725c58f3b93c7e3b267eec105571f8bbf882ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a><span data-ttu-id="61d03-102">Specifica della conservazione dei dati CDR in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61d03-102">Specifying retention of CDR data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61d03-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="61d03-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="61d03-104">Per impostazione predefinita, i dati della registrazione dei dettagli delle chiamate (CDR) vengono eliminati dopo 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="61d03-104">By default, call detail recording (CDR) data is purged after 60 days.</span></span> <span data-ttu-id="61d03-105">È possibile usare le impostazioni nella pagina **registrazione dettagli chiamata** per mantenere i dati per un periodo di tempo più lungo o più breve.</span><span class="sxs-lookup"><span data-stu-id="61d03-105">You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="61d03-106">Se si disattiva CDR, anche i dati acquisiti prima dell'abilitazione di CDR saranno soggetti all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="61d03-106">If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61d03-107">È necessario configurare CDR e la qualità dell'esperienza (QoE) per mantenere i dati per lo stesso numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="61d03-107">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days.</span></span> <span data-ttu-id="61d03-108">Ogni chiamata nei report dettagli chiamata (CDRs), disponibile dalla pagina Web monitoraggio report server, include informazioni CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="61d03-108">Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information.</span></span> <span data-ttu-id="61d03-109">Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate potrebbero includere solo dati CDR, mentre altre possono includere solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="61d03-109">If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="61d03-110">Usare le procedure seguenti per configurare le impostazioni di eliminazione dei dati CDR.</span><span class="sxs-lookup"><span data-stu-id="61d03-110">Use the following procedures to configure purge settings for CDR data.</span></span>

<div>

## <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="61d03-111">Per specificare la conservazione dei dati CDR</span><span class="sxs-lookup"><span data-stu-id="61d03-111">To specify retention of CDR data</span></span>

1.  <span data-ttu-id="61d03-112">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61d03-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="61d03-113">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="61d03-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="61d03-114">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="61d03-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="61d03-115">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="61d03-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="61d03-116">Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="61d03-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="61d03-117">Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di CDRS**.</span><span class="sxs-lookup"><span data-stu-id="61d03-117">To turn on purging, select **Enable purging of CDRs**.</span></span>

6.  <span data-ttu-id="61d03-118">In **Mantieni CDRS per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.</span><span class="sxs-lookup"><span data-stu-id="61d03-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="61d03-119">In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="61d03-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="61d03-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="61d03-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="61d03-121">Specifica della conservazione CDR con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="61d03-121">Specifying CDR Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="61d03-122">È possibile creare impostazioni di conservazione CDR tramite Windows PowerShell e il cmdlet Set-CsCdrConfiguration.</span><span class="sxs-lookup"><span data-stu-id="61d03-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="61d03-123">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61d03-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="61d03-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="61d03-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="61d03-125">Per specificare la conservazione CDR per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="61d03-125">To specify CDR retention for a specific location</span></span>

  - <span data-ttu-id="61d03-126">Questo comando consente l'eliminazione dei dati CDR per il sito Redmond e configura il sito per la gestione dei dati CDR e dei rapporti di errore per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="61d03-126">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="61d03-127">Per specificare la conservazione CDR per più posizioni</span><span class="sxs-lookup"><span data-stu-id="61d03-127">To specify CDR retention for multiple locations</span></span>

  - <span data-ttu-id="61d03-128">Questo comando configura la conservazione CDR per tutte le impostazioni di configurazione CDR in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61d03-128">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<span data-ttu-id="61d03-129">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="61d03-129">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61d03-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61d03-130">See Also</span></span>


[<span data-ttu-id="61d03-131">Registrazione dettagli chiamata (CDR) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61d03-131">Call detail recording (CDR) in Lync Server 2013</span></span>](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

