---
title: Creare o modificare una raccolta di impostazioni di configurazione delle riunioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6906331e8a0b2cf67c8d4c0404caf2816f441ea0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="586f0-102">Creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="586f0-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="586f0-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="586f0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="586f0-p101">È possibile utilizzare le impostazioni nella pagina Configurazione riunione per definire diverse caratteristiche di partecipazione alle riunioni. Per impostazione predefinita, le impostazioni globali definiscono la partecipazione alle riunioni. È inoltre possibile creare impostazioni di partecipazione alle riunioni a livello di sito e di pool. Se si creano impostazioni a livello di pool, tali impostazioni si applicheranno a tutte le riunioni ospitate da tale pool. Se invece non si creano impostazioni a livello di pool, si applicheranno le impostazioni a livello di sito, se esistenti. Se non si definiscono impostazioni a livello di sito, le impostazioni globali si applicheranno a tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="586f0-p101">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience. By default, the global settings define the join experience. You can also create site-level and pool-level meeting join settings. If you create pool-level settings, those settings apply to all meetings hosted by that pool. If you do not create pool-level settings, site-level settings apply, if they exist. If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="586f0-110">Per creare nuove impostazioni di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="586f0-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="586f0-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="586f0-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="586f0-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="586f0-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="586f0-113">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="586f0-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="586f0-114">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="586f0-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="586f0-115">Nella pagina **Configurazione riunione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586f0-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="586f0-p103">Per creare un criterio a livello di sito, fare clic su **Configurazione sito**. Nel campo di ricerca **Seleziona un sito** digitare il nome del sito per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic sul sito desiderato nell'elenco dei siti e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="586f0-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="586f0-p104">Per creare un criterio a livello di pool, fare clic su **Configurazione pool**. Nel campo di ricerca **Seleziona un servizio** digitare il nome del pool per cui si desidera definire le impostazioni di partecipazione alle riunioni, per intero o in parte. Fare clic su un pool desiderato nell'elenco di servizi e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="586f0-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="586f0-p105">Per instradare i partecipanti che accedono dalla rete PSTN (Public Switched Telephone Network ) attraverso la sala di attesa, deselezionare la casella di controllo **I chiamanti PSTN ignorano la sala di attesa**. Per impostazione predefinita, i partecipanti che accedono dalla rete PSTN passano direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="586f0-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="586f0-124">Per configurare l'utente che svolge la funzione di relatore nella riunione, in **Designa come relatore** effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="586f0-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="586f0-125">Per non consentire a persone diverse dall'organizzatore di svolgere la funzione di relatore, fare clic su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="586f0-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="586f0-p106">Per consentire solo ai partecipanti membri dell'organizzazione di svolgere la funzione di relatore, fare clic su **Società**. Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="586f0-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="586f0-128">Per consentire a qualsiasi partecipante di fungere da relatore, fare clic su **Tutti**.</span><span class="sxs-lookup"><span data-stu-id="586f0-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="586f0-p107">Per fare in modo che l'organizzatore selezioni il tipo di conferenza quando pianifica una riunione, deselezionare la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita**. Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="586f0-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="586f0-p108">Per impedire che gli utenti anonimi (non autenticati) vengano ammessi automaticamente, deselezionare la casella di controllo **Consenti utenti anonimi per impostazione predefinita**. Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="586f0-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="586f0-133">Per personalizzare l'invito alla riunione che viene inviato ai partecipanti, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="586f0-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="586f0-134">Si noti che la dimensione massima degli URL e del testo del piè di pagina personalizzato è di 1 KB.</span><span class="sxs-lookup"><span data-stu-id="586f0-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="586f0-135">Se non si specifica un valore per le personalizzazioni, queste non verranno incluse nella riunione, ad eccezione di **URL Guida**.</span><span class="sxs-lookup"><span data-stu-id="586f0-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="586f0-136">Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Lync verrà visualizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="586f0-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="586f0-137">Per personalizzare il logo che viene visualizzato nell'invito alla riunione, immettere il percorso del logo in **URL logo**.</span><span class="sxs-lookup"><span data-stu-id="586f0-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="586f0-138">Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 per 30 pixel.</span><span class="sxs-lookup"><span data-stu-id="586f0-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="586f0-139">Per personalizzare il testo della Guida che viene visualizzato nell'invito alla riunione, immettere il percorso del testo della Guida in **URL Guida**.</span><span class="sxs-lookup"><span data-stu-id="586f0-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="586f0-140">Per personalizzare il testo legale che viene visualizzato nell'invito alla riunione, immettere il percorso del testo legale in **URL testo legale**.</span><span class="sxs-lookup"><span data-stu-id="586f0-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="586f0-141">Per personalizzare il testo del piè di pagina che viene visualizzato nell'invito alla riunione, immettere il testo in **Testo piè di pagina personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="586f0-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="586f0-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="586f0-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="586f0-143">Per modificare una raccolta esistente di configurazioni di riunioni</span><span class="sxs-lookup"><span data-stu-id="586f0-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="586f0-144">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="586f0-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="586f0-145">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="586f0-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="586f0-146">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="586f0-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="586f0-147">Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="586f0-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="586f0-148">Nell'elenco delle configurazioni delle riunioni, fare clic sulla configurazione che si desidera modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="586f0-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="586f0-149">In **Modifica configurazione riunione** modificare qualsiasi impostazione di configurazione, tranne il nome della configurazione, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="586f0-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="586f0-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="586f0-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="586f0-151">Creazione di nuove impostazioni di configurazione delle riunioni tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="586f0-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="586f0-152">È possibile creare le impostazioni di configurazione delle riunioni (solo nell'ambito del sito) utilizzando Windows PowerShell e il cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="586f0-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="586f0-153">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="586f0-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="586f0-154">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="586f0-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="586f0-155">Per creare le impostazioni di configurazione delle riunioni che utilizzano i valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="586f0-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="586f0-156">Il comando seguente crea un nuovo insieme di impostazioni di configurazione di riunione per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="586f0-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="586f0-157">Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, le nuove impostazioni di configurazione di riunione utilizzeranno i valori predefiniti per le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="586f0-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="586f0-158">Per modificare un valore di proprietà durante la creazione delle impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="586f0-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="586f0-p112">Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di riunione che per impostazione predefinita ammettono chiunque come relatore di una riunione, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="586f0-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="586f0-161">Per modificare più valori di proprietà durante la creazione di impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="586f0-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="586f0-p113">È possibile modificare più valori di proprietà includendo più parametri. Il comando seguente ad esempio ammette chiunque come relatore di una riunione e forza inoltre il passaggio degli utenti PSTN in una sala di attesa finché non vengono ammessi formalmente alla riunione:</span><span class="sxs-lookup"><span data-stu-id="586f0-p113">Multiple property values can be modified by including multiple parameters. For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="586f0-164">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="586f0-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

