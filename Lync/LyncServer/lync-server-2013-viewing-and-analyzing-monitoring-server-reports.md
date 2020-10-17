---
title: 'Lync Server 2013: visualizzazione e analisi dei report di Monitoring Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7416b54e7b1ddb5bfc41c07502802c7c120a93ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523573"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="604b9-102">Visualizzazione e analisi dei report di Monitoring Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604b9-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="604b9-103">_**Ultimo argomento modificato:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="604b9-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="604b9-104">Monitoring Server Reports offre diverse misure di qualità vocale per monitorare gli QoE che vengono recapitati agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="604b9-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="604b9-105">Monitoring Server include inoltre numerosi report incorporati che l'organizzazione può utilizzare per visualizzare le tendenze relative all'utilizzo e alla qualità dei contenuti multimediali sulla rete dell'organizzazione e risolvere i problemi relativi alla qualità multimediale che si verificano.</span><span class="sxs-lookup"><span data-stu-id="604b9-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="604b9-106">Una parte principale del mantenimento dei rapporti di Monitoring Server che interessano le operazioni quotidiane e settimanali è la visualizzazione e l'analisi dei rapporti sulla qualità multimediale, in particolare:</span><span class="sxs-lookup"><span data-stu-id="604b9-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="604b9-107">Riepilogo QoE/rapporti di tendenza</span><span class="sxs-lookup"><span data-stu-id="604b9-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="604b9-108">Rapporti sulle prestazioni QoE</span><span class="sxs-lookup"><span data-stu-id="604b9-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="604b9-109">Visualizzare i report dal Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="604b9-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="604b9-110">Da un Web browser, individuare i server che ospitano SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="604b9-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="604b9-111">Visualizzare i report necessari dalla schermata del browser.</span><span class="sxs-lookup"><span data-stu-id="604b9-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="604b9-112">Optional Esportare un report selezionando l'opzione Esporta e il formato di output necessario.</span><span class="sxs-lookup"><span data-stu-id="604b9-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="604b9-113">Configurare la registrazione dettagli chiamata (CDR)</span><span class="sxs-lookup"><span data-stu-id="604b9-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="604b9-114">Da un account utente membro del gruppo RTCUniversalServerAdmins o con autorizzazioni equivalenti oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, eseguire l'accesso a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="604b9-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="604b9-115">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="604b9-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="604b9-116">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="604b9-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="604b9-117">Nella pagina **Registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="604b9-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="604b9-118">Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="604b9-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="604b9-119">In **Mantieni registrazioni dettagli chiamata per durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere conservate le registrazioni dettagli chiamata.</span><span class="sxs-lookup"><span data-stu-id="604b9-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="604b9-120">In **Mantieni dati delle segnalazioni errori per durata massima (giorni)** selezionare il numero massimo di giorni per cui mantenere le segnalazioni degli errori.</span><span class="sxs-lookup"><span data-stu-id="604b9-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="604b9-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="604b9-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="604b9-122">Configurare QoE</span><span class="sxs-lookup"><span data-stu-id="604b9-122">Configure QoE</span></span>

1.  <span data-ttu-id="604b9-123">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="604b9-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="604b9-124">Per informazioni dettagliate, vedere Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="604b9-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="604b9-125">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="604b9-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="604b9-126">Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.</span><span class="sxs-lookup"><span data-stu-id="604b9-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="604b9-127">Nella pagina **Dati QoE** fare clic sul sito appropriato nella tabella, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="604b9-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="604b9-128">Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="604b9-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="604b9-129">In **Mantieni registrazioni dettagli chiamata per durata massima (giorni):** selezionare il numero massimo di giorni in cui i dati QoE devono essere conservati.</span><span class="sxs-lookup"><span data-stu-id="604b9-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="604b9-130">Fare clic su Commit.</span><span class="sxs-lookup"><span data-stu-id="604b9-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="604b9-131">Modificare i criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="604b9-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="604b9-132">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="604b9-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="604b9-133">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="604b9-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="604b9-134">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="604b9-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="604b9-135">Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="604b9-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="604b9-136">In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="604b9-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="604b9-137">Per abilitare o disabilitare l'archiviazione interna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="604b9-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="604b9-138">Per abilitare o disabilitare l'archiviazione esterna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="604b9-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="604b9-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="604b9-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="604b9-140">Applicazione di un criterio di archiviazione a un utente</span><span class="sxs-lookup"><span data-stu-id="604b9-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="604b9-141">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="604b9-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="604b9-142">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="604b9-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="604b9-143">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="604b9-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="604b9-144">Nella tabella in cui sono elencati i risultati di ricerca, fare clic sull'account utente, scegliere **Modifica** e quindi **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="604b9-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="604b9-145">In **modifica utente di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="604b9-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="604b9-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="604b9-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="604b9-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="604b9-147">See Also</span></span>


[<span data-ttu-id="604b9-148">Utilizzo di report di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604b9-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="604b9-149">Report sulle prestazioni del server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604b9-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="604b9-150">Rapporto di confronto qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="604b9-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

