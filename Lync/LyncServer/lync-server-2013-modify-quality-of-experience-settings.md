---
title: "Lync Server 2013: modificare la qualità delle impostazioni dell'esperienza"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify Quality of Experience settings
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182563(v=OCS.15)
ms:contentKeyID: 48184996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2cf4745f76fa4667d14c9da5ca2b4e5309767b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="bfb11-102">Modificare le impostazioni di qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb11-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfb11-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bfb11-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bfb11-104">Per impostazione predefinita, i dati di qualità dell'esperienza (QoE) vengono eliminati dopo 60 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb11-104">By default, Quality of Experience (QoE) data is purged after 60 days.</span></span> <span data-ttu-id="bfb11-105">Per mantenere i dati per un periodo di tempo più lungo o più breve, è possibile usare le impostazioni nella pagina di **dati qualità della prova** .</span><span class="sxs-lookup"><span data-stu-id="bfb11-105">You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time.</span></span> <span data-ttu-id="bfb11-106">Se si disattiva QoE, anche i dati acquisiti prima dell'abilitazione di QoE saranno soggetti all'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="bfb11-106">If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfb11-107">Devi configurare la registrazione dei dettagli delle chiamate (CDR) e QoE per mantenere i dati per lo stesso numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb11-107">You should configure call detail recording (CDR) and QoE to retain data for the same number of days.</span></span> <span data-ttu-id="bfb11-108">Ogni chiamata nei report dettagli chiamata (CDRs), disponibile nella Home page dei report di monitoraggio, include informazioni CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="bfb11-108">Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information.</span></span> <span data-ttu-id="bfb11-109">Se la durata di eliminazione per CDR e QoE è diversa, alcune chiamate possono includere solo dati CDR, mentre altre possono includere solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="bfb11-109">If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="bfb11-110">La procedura seguente descrive come configurare le impostazioni di eliminazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="bfb11-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="bfb11-111">Per specificare la conservazione dei dati QoE tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="bfb11-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bfb11-112">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bfb11-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bfb11-113">Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bfb11-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bfb11-114">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bfb11-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfb11-115">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bfb11-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfb11-116">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="bfb11-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="bfb11-117">Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="bfb11-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="bfb11-118">Per attivare l'eliminazione, selezionare **Abilita l'eliminazione di QoE**.</span><span class="sxs-lookup"><span data-stu-id="bfb11-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="bfb11-119">In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="bfb11-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="bfb11-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="bfb11-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bfb11-121">Specifica della conservazione QoE usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfb11-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bfb11-122">È possibile creare impostazioni di conservazione QoE usando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bfb11-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="bfb11-123">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfb11-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bfb11-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="bfb11-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="bfb11-125">Per specificare la conservazione QoE per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="bfb11-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="bfb11-126">Questo comando consente l'eliminazione dei dati QoE per il sito Redmond e configura il sito per la gestione dei dati QoE per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="bfb11-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="bfb11-127">Per specificare la conservazione QoE per più posizioni</span><span class="sxs-lookup"><span data-stu-id="bfb11-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="bfb11-128">Questo comando configura la conservazione QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bfb11-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="bfb11-129">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="bfb11-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bfb11-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfb11-130">See Also</span></span>


[<span data-ttu-id="bfb11-131">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfb11-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

