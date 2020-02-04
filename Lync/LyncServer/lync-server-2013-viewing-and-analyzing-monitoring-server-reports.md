---
title: 'Lync Server 2013: visualizzazione e analisi dei report del server di monitoraggio'
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
ms.openlocfilehash: 9e4fce6cf17601d2a68a07a3b832e6b50c10b759
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="7f447-102">Visualizzazione e analisi dei report del server di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f447-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f447-103">_**Argomento Ultima modifica:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="7f447-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="7f447-104">Monitoring Server Reports offre diverse misure di qualità vocale per monitorare gli QoE che vengono recapitati agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="7f447-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="7f447-105">Il server di monitoraggio include inoltre diversi report predefiniti che l'organizzazione può usare per guardare l'uso e le tendenze della qualità multimediale nella rete dell'organizzazione e risolvere i problemi di qualità dei contenuti multimediali che si verificano.</span><span class="sxs-lookup"><span data-stu-id="7f447-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="7f447-106">Una parte principale della gestione dei report del server di monitoraggio che interessano le operazioni quotidiane e settimanali è la visualizzazione e l'analisi dei report sulla qualità multimediale, in particolare:</span><span class="sxs-lookup"><span data-stu-id="7f447-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="7f447-107">Riepilogo QoE/report di tendenza</span><span class="sxs-lookup"><span data-stu-id="7f447-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="7f447-108">Report prestazioni QoE</span><span class="sxs-lookup"><span data-stu-id="7f447-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="7f447-109">Visualizzare i report dal server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="7f447-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="7f447-110">In un Web browser individuare i server che ospitano SQL Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="7f447-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="7f447-111">Visualizzare i report necessari dalla schermata del browser.</span><span class="sxs-lookup"><span data-stu-id="7f447-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="7f447-112">Opzionale Esportare un report selezionando l'opzione Esporta e il formato di output richiesto.</span><span class="sxs-lookup"><span data-stu-id="7f447-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="7f447-113">Configurare la registrazione dettagli chiamata (CDR)</span><span class="sxs-lookup"><span data-stu-id="7f447-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="7f447-114">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con autorizzazioni equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7f447-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7f447-115">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f447-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7f447-116">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.</span><span class="sxs-lookup"><span data-stu-id="7f447-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="7f447-117">Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7f447-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7f447-118">Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="7f447-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7f447-119">In **Mantieni registrazioni dei dettagli delle chiamate per la durata massima (giorni):** selezionare il numero massimo di giorni in cui le registrazioni dei dettagli delle chiamate devono essere mantenute.</span><span class="sxs-lookup"><span data-stu-id="7f447-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="7f447-120">In **Mantieni i dati del report sugli errori per la durata massima (giorni):** selezionare il numero massimo di giorni in cui devono essere mantenuti i report degli errori.</span><span class="sxs-lookup"><span data-stu-id="7f447-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="7f447-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7f447-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="7f447-122">Configurare QoE</span><span class="sxs-lookup"><span data-stu-id="7f447-122">Configure QoE</span></span>

1.  <span data-ttu-id="7f447-123">Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7f447-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="7f447-124">Per informazioni dettagliate, vedere delegare le autorizzazioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7f447-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="7f447-125">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f447-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7f447-126">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.</span><span class="sxs-lookup"><span data-stu-id="7f447-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="7f447-127">Nella pagina **qualità di dati esperienza** fare clic sul sito appropriato nella tabella, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7f447-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="7f447-128">Per attivare l'eliminazione, selezionare **Abilita eliminazione per i server di monitoraggio**.</span><span class="sxs-lookup"><span data-stu-id="7f447-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="7f447-129">In **Mantieni registrazioni dei dettagli delle chiamate per la durata massima (giorni):** selezionare il numero massimo di giorni di conservazione dei dati QoE.</span><span class="sxs-lookup"><span data-stu-id="7f447-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="7f447-130">Fare clic su Commit.</span><span class="sxs-lookup"><span data-stu-id="7f447-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="7f447-131">Modificare i criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="7f447-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="7f447-132">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7f447-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f447-133">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f447-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7f447-134">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="7f447-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="7f447-135">Fare clic su **Globale** nell'elenco dei criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7f447-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7f447-136">In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7f447-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="7f447-137">Per abilitare o disabilitare l'archiviazione interna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="7f447-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="7f447-138">Per abilitare o disabilitare l'archiviazione esterna per la distribuzione, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="7f447-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="7f447-139">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7f447-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="7f447-140">Applicare un criterio di archiviazione a un utente</span><span class="sxs-lookup"><span data-stu-id="7f447-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="7f447-141">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7f447-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7f447-142">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7f447-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="7f447-143">Nella barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente da configurare.</span><span class="sxs-lookup"><span data-stu-id="7f447-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7f447-144">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="7f447-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7f447-145">In **modifica utenti di Lync Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="7f447-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="7f447-146">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7f447-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7f447-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f447-147">See Also</span></span>


[<span data-ttu-id="7f447-148">Uso di report di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f447-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="7f447-149">Report prestazioni server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f447-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="7f447-150">Report di confronto qualità multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f447-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

