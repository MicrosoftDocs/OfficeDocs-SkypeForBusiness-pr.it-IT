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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="74f15-102">Creare o modificare una raccolta di impostazioni di configurazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f15-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74f15-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="74f15-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="74f15-104">È possibile usare le impostazioni nella pagina Configurazione riunione per definire le varie caratteristiche dell'esperienza di partecipazione alla riunione.</span><span class="sxs-lookup"><span data-stu-id="74f15-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="74f15-105">Per impostazione predefinita, le impostazioni globali definiscono l'esperienza di partecipazione.</span><span class="sxs-lookup"><span data-stu-id="74f15-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="74f15-106">È anche possibile creare impostazioni di riunione a livello di sito e a livello di pool.</span><span class="sxs-lookup"><span data-stu-id="74f15-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="74f15-107">Se crei impostazioni a livello di pool, queste impostazioni si applicano a tutte le riunioni ospitate da tale pool.</span><span class="sxs-lookup"><span data-stu-id="74f15-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="74f15-108">Se non si creano impostazioni a livello di pool, le impostazioni a livello di sito si applicano, se esistenti.</span><span class="sxs-lookup"><span data-stu-id="74f15-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="74f15-109">Se non si definiscono le impostazioni a livello di sito, le impostazioni globali si applicano a tutte le riunioni.</span><span class="sxs-lookup"><span data-stu-id="74f15-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="74f15-110">Per creare nuove impostazioni di partecipazione alle riunioni</span><span class="sxs-lookup"><span data-stu-id="74f15-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="74f15-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="74f15-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74f15-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74f15-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74f15-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74f15-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74f15-114">Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="74f15-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="74f15-115">Nella pagina **Configurazione riunione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74f15-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="74f15-116">Per creare un criterio a livello di sito, fare clic su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="74f15-116">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="74f15-117">Nel campo **Seleziona ricerca sito** digitare tutto o parte del nome del sito per il quale si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="74f15-117">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="74f15-118">Nell'elenco dei siti risultante fare clic sul sito desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74f15-118">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="74f15-119">Per creare criteri a livello di pool, fare clic su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="74f15-119">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="74f15-120">Nel campo **selezionare un servizio** di ricerca digitare tutto o parte del nome del servizio pool per cui si desidera definire le impostazioni di partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="74f15-120">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="74f15-121">Nell'elenco dei servizi risultante fare clic sul pool desiderato e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="74f15-121">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="74f15-122">Per instradare i partecipanti che effettuano la chiamata tramite la rete PSTN (Public Switched Telephone Network) nella sala di attesa, deselezionare la casella di controllo **Ignora chiamate PSTN** .</span><span class="sxs-lookup"><span data-stu-id="74f15-122">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box.</span></span> <span data-ttu-id="74f15-123">Per impostazione predefinita, i partecipanti che effettuano la chiamata dalla rete PSTN accedono direttamente alla riunione.</span><span class="sxs-lookup"><span data-stu-id="74f15-123">By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="74f15-124">Per configurare chi può essere un relatore nella riunione, in **designa come relatore**eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74f15-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="74f15-125">Per non consentire a utenti diversi dall'organizzatore di essere relatori, fare clic su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="74f15-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="74f15-126">Per consentire solo ai partecipanti membri dell'organizzazione di essere relatori, fare clic su **società**.</span><span class="sxs-lookup"><span data-stu-id="74f15-126">To allow only participants who are members of your organization to be a presenter, click **Company**.</span></span> <span data-ttu-id="74f15-127">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="74f15-127">This is the default setting.</span></span>
    
      - <span data-ttu-id="74f15-128">Per consentire a tutti i partecipanti di essere un relatore, fare clic su **tutti**.</span><span class="sxs-lookup"><span data-stu-id="74f15-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="74f15-129">Per fare in modo che l'organizzatore selezioni un tipo di conferenza durante la programmazione di una riunione, deselezionare la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="74f15-129">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box.</span></span> <span data-ttu-id="74f15-130">Per impostazione predefinita, il tipo di conferenza viene assegnato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="74f15-130">By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="74f15-131">Per impedire l'ammissione automatica degli utenti anonimi (non autenticati), deselezionare la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** .</span><span class="sxs-lookup"><span data-stu-id="74f15-131">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box.</span></span> <span data-ttu-id="74f15-132">Per impostazione predefinita, gli utenti anonimi vengono ammessi automaticamente alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="74f15-132">By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="74f15-133">Per personalizzare l'invito alla riunione inviato ai partecipanti, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="74f15-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="74f15-134">Tieni presente che la lunghezza massima per gli URL e il testo del piè di pagina personalizzato è 1KB.</span><span class="sxs-lookup"><span data-stu-id="74f15-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="74f15-135">Ad eccezione dell' **URL della Guida**, se non si specifica un valore per le personalizzazioni, questi non verranno inclusi nella riunione.</span><span class="sxs-lookup"><span data-stu-id="74f15-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="74f15-136">Se non si include un URL della Guida personalizzato, l'URL della Guida predefinito per Lync verrà visualizzato nell'invito.</span><span class="sxs-lookup"><span data-stu-id="74f15-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="74f15-137">Per personalizzare il logo visualizzato nell'invito alla riunione, in **URL logo**immettere la posizione del logo.</span><span class="sxs-lookup"><span data-stu-id="74f15-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="74f15-138">Il logo deve essere un'immagine GIF o JPG con una dimensione di 188 di 30 pixel.</span><span class="sxs-lookup"><span data-stu-id="74f15-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="74f15-139">Per personalizzare il testo della Guida visualizzato nell'invito alla riunione, in **URL della Guida**immettere la posizione del testo della guida.</span><span class="sxs-lookup"><span data-stu-id="74f15-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="74f15-140">Per personalizzare il testo legale visualizzato nell'invito alla riunione, in **URL di testo legale**immettere la posizione del testo legale.</span><span class="sxs-lookup"><span data-stu-id="74f15-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="74f15-141">Per personalizzare il testo del piè di pagina visualizzato nell'invito alla riunione, nel **testo del piè**di pagina personalizzato immettere il testo.</span><span class="sxs-lookup"><span data-stu-id="74f15-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="74f15-142">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="74f15-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="74f15-143">Per modificare una raccolta esistente di configurazioni di riunione</span><span class="sxs-lookup"><span data-stu-id="74f15-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="74f15-144">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="74f15-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="74f15-145">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74f15-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74f15-146">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74f15-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74f15-147">Sulla barra di spostamento sinistra fare clic su **conferenza** e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="74f15-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="74f15-148">Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="74f15-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="74f15-149">In **modifica configurazione riunione**modificare le impostazioni di configurazione, ad eccezione del nome della configurazione, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="74f15-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="74f15-150">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="74f15-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="74f15-151">Creazione di nuove impostazioni di configurazione delle riunioni con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="74f15-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="74f15-152">Le impostazioni di configurazione della riunione possono essere create (solo nell'ambito del sito) tramite Windows PowerShell e il cmdlet New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="74f15-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="74f15-153">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="74f15-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="74f15-154">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="74f15-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="74f15-155">Per creare impostazioni di configurazione delle riunioni che usano i valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="74f15-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="74f15-156">Questo comando crea un nuovo set di impostazioni di configurazione delle riunioni per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="74f15-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="74f15-157">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, le nuove impostazioni di configurazione della riunione utilizzeranno i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="74f15-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="74f15-158">Per modificare un valore di proprietà durante la creazione delle impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="74f15-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="74f15-159">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="74f15-159">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="74f15-160">Ad esempio, per creare una raccolta di impostazioni di configurazione della riunione che, per impostazione predefinita, ammettono tutti a una riunione come relatore usare un comando come questo:</span><span class="sxs-lookup"><span data-stu-id="74f15-160">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="74f15-161">Per modificare più valori di proprietà durante la creazione delle impostazioni di configurazione delle riunioni</span><span class="sxs-lookup"><span data-stu-id="74f15-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="74f15-162">Più valori di proprietà possono essere modificati includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="74f15-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="74f15-163">Ad esempio, questo comando ammette tutti i partecipanti a una riunione come relatore e costringe anche gli utenti PSTN ad attendere nella sala di attesa finché non vengono formalmente ammessi alla riunione:</span><span class="sxs-lookup"><span data-stu-id="74f15-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="74f15-164">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="74f15-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

