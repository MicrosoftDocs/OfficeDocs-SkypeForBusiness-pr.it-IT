---
title: 'Lync Server 2013: modificare le impostazioni di qualità delle esperienze'
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
ms.openlocfilehash: 0e5af1f53cc35bd22fcc09058a0aecb1b499897f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="b76cb-102">Modificare le impostazioni di qualità delle esperienze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b76cb-102">Modify Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b76cb-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b76cb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b76cb-p101">Per impostazione predefinita, i dati relativi alla QoE (Quality of Experience) vengono eliminati dopo 60 giorni. È possibile utilizzare le impostazioni nella pagina **Dati QoE** per conservare i dati per un periodo superiore o inferiore. Se si disabilita la funzionalità QoE, verranno eliminati anche i dati acquisiti prima dell'abilitazione di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b76cb-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b76cb-p102">È consigliabile configurare la registrazione dettagli chiamata (CDR, Call Detail Recording) e QoE in modo che mantengano i dati per lo stesso numero di giorni. Ogni chiamata inclusa nei rapporti Dettagli chiamata, disponibili dalla home page dei rapporti di monitoraggio, include informazioni di registrazione dettagli chiamata e QoE. Se il periodo che precede l'eliminazione è diverso, alcune chiamate potrebbero includere solo dati di registrazione dettagli chiamata e altre solo dati QoE.</span><span class="sxs-lookup"><span data-stu-id="b76cb-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>



</div>

<span data-ttu-id="b76cb-110">Nella procedura seguente viene descritto come configurare le impostazioni per l'eliminazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="b76cb-110">The following procedure describes how to configure purge settings for QoE data.</span></span>

<div>

## <a name="to-specify-retention-of-qoe-data-by-using-lync-server-control-panel"></a><span data-ttu-id="b76cb-111">Per specificare il mantenimento dei dati QoE utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="b76cb-111">To specify retention of QoE data by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="b76cb-112">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b76cb-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b76cb-113">Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b76cb-113">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b76cb-114">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b76cb-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b76cb-115">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b76cb-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b76cb-116">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="b76cb-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="b76cb-117">Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="b76cb-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="b76cb-118">Per abilitare l'eliminazione, selezionare **Abilita eliminazione dei dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="b76cb-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6.  <span data-ttu-id="b76cb-119">In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere i dati QoE.</span><span class="sxs-lookup"><span data-stu-id="b76cb-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="b76cb-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b76cb-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b76cb-121">Impostazione della conservazione QoE tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b76cb-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b76cb-122">È possibile creare impostazioni di conservazione QoE utilizzando Windows PowerShell e il cmdlet **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b76cb-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="b76cb-123">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b76cb-123">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b76cb-124">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="b76cb-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="b76cb-125">Per specificare il mantenimento dei dati QoE per una posizione specifica</span><span class="sxs-lookup"><span data-stu-id="b76cb-125">To specify QoE retention for a specific location</span></span>

  - <span data-ttu-id="b76cb-126">Questo comando consente di abilitare l'eliminazione dei dati QoE per il sito Redmond e di configurare il sito per mantenere i dati QoE per 20 giorni.</span><span class="sxs-lookup"><span data-stu-id="b76cb-126">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

</div>

<div>

## <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="b76cb-127">Per specificare il mantenimento dei dati QoE per più posizioni</span><span class="sxs-lookup"><span data-stu-id="b76cb-127">To specify QoE retention for multiple locations</span></span>

  - <span data-ttu-id="b76cb-128">Questo comando consente di configurare il mantenimento dei dati QoE per tutte le impostazioni di configurazione QoE in uso in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b76cb-128">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

</div>

<span data-ttu-id="b76cb-129">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="b76cb-129">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b76cb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b76cb-130">See Also</span></span>


[<span data-ttu-id="b76cb-131">Distribuzione del monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b76cb-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

