---
title: Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1bc6f-102">Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc6f-102">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bc6f-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1bc6f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1bc6f-104">Quando si installa Lync Server, si ottiene una raccolta globale delle impostazioni di Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-104">When you install Lync Server, you get a global collection of Lync Phone Edition settings.</span></span> <span data-ttu-id="1bc6f-105">Queste impostazioni si applicano a tutti i dispositivi in cui è in uso Lync Phone Edition nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-105">These settings apply to all devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="1bc6f-106">È possibile modificare queste impostazioni in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-106">You can change these settings at any time.</span></span> <span data-ttu-id="1bc6f-107">È anche possibile configurare una nuova raccolta di impostazioni che si applicano ai dispositivi di un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-107">You can also set up a new collection of settings that apply to the devices in a specific site.</span></span> <span data-ttu-id="1bc6f-108">Le impostazioni del sito hanno la precedenza sulle impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-108">Site settings take precedence over global settings.</span></span>

<span data-ttu-id="1bc6f-109">Le impostazioni di configurazione includono il nome della raccolta, l'ambito (globale o il sito), l'impostazione di sicurezza SIP, il livello di registrazione, il livello di qualità vocale del servizio (QoS), l'impostazione di blocco telefonico e i dettagli del blocco telefonico, ovvero la durata della a) per sbloccare il numero di identificazione personale ( PIN) deve essere e b) il telefono rimane inattivo prima di bloccarsi.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-109">Configuration settings consist of the collection name, scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, how long the a) unlock personal identification number (PIN) must be and b) phone stays idle before locking itself.</span></span>

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a><span data-ttu-id="1bc6f-110">Per creare una raccolta di impostazioni di configurazione di Lync Phone Edition o modificare le impostazioni per una raccolta esistente</span><span class="sxs-lookup"><span data-stu-id="1bc6f-110">To create a collection of Lync Phone Edition configuration settings or edit settings for an existing collection</span></span>

1.  <span data-ttu-id="1bc6f-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1bc6f-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1bc6f-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1bc6f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1bc6f-114">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="1bc6f-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1bc6f-115">Nella pagina **Configurazione dispositivo** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-115">On the **Device Configuration** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1bc6f-116">Per creare una nuova raccolta di impostazioni di configurazione di Lync Phone Edition, fare clic su **nuovo**, selezionare un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si vuole, apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-116">To create a new collection of Lync Phone Edition configuration settings, click **New**, select a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
      - <span data-ttu-id="1bc6f-117">Per modificare le impostazioni di una raccolta esistente, fare clic sulla raccolta, fare clic sul menu **modifica** , fare clic su **Mostra dettagli**e quindi apportare le modifiche desiderate.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-117">To edit any of the settings in an existing collection, click the collection, click the **Edit** menu, click **Show details**, and then make your changes.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="1bc6f-118">Per tornare all'uso delle impostazioni predefinite per la raccolta globale, fare clic sulla raccolta globale, fare clic sul menu <STRONG>modifica</STRONG> , scegliere <STRONG>Elimina</STRONG>e quindi fare clic su <STRONG>OK</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-118">To go back to using the default settings for the global collection, click the global collection, click the <STRONG>Edit</STRONG> menu, click <STRONG>Delete</STRONG>, and then click <STRONG>OK</STRONG>.</span></span> <span data-ttu-id="1bc6f-119">In questo modo non verrà eliminata la raccolta globale; Ripristina solo le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-119">This will not delete the global collection; it just resets the settings to the defaults.</span></span>

        
        </div>

5.  <span data-ttu-id="1bc6f-120">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1bc6f-121">Creazione di nuove impostazioni di configurazione di Lync Phone Edition con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bc6f-121">Creating New Lync Phone Edition Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1bc6f-122">È possibile creare le impostazioni di configurazione di Lync Phone Edition (solo nell'ambito del sito) tramite Windows PowerShell e il cmdlet **New-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1bc6f-122">You can create Lync Phone Edition configuration settings can (at the site scope only) by using Windows PowerShell and the **New-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="1bc6f-123">Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-123">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1bc6f-124">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="1bc6f-125">Per creare nuove impostazioni di configurazione di Lync Phone Edition che usano i valori predefiniti</span><span class="sxs-lookup"><span data-stu-id="1bc6f-125">To create new Lync Phone Edition configuration settings that use the default values</span></span>

  - <span data-ttu-id="1bc6f-126">Questo comando crea un nuovo set di impostazioni di configurazione del telefono UC per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-126">This command creates a new set of UC phone configuration settings for the Redmond site:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="1bc6f-127">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1bc6f-128">Per modificare un valore di proprietà Single durante la creazione di nuove impostazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1bc6f-128">To change a single property value when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="1bc6f-129">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-129">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="1bc6f-130">Ad esempio, per creare una raccolta di impostazioni di configurazione del telefono UC che, per impostazione predefinita, richiedono il blocco del telefono, usa un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-130">For example, to create a collection of UC phone configuration settings that, by default, require phone locking, use a command like this:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a><span data-ttu-id="1bc6f-131">Per modificare più valori di proprietà quando si creano nuove impostazioni di configurazione di Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1bc6f-131">To change multiple property values when creating new Lync Phone Edition configuration settings</span></span>

  - <span data-ttu-id="1bc6f-132">Più valori di proprietà possono essere modificati includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-132">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="1bc6f-133">Ad esempio, questo comando impone il blocco del telefono e imposta anche la lunghezza minima del PIN su 8 cifre:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-133">For example, this command enforces phone locking and also sets the minimum PIN length to 8 digits:</span></span>
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

<span data-ttu-id="1bc6f-134">Per informazioni dettagliate, vedere [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span><span class="sxs-lookup"><span data-stu-id="1bc6f-134">For details, see [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bc6f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bc6f-135">See Also</span></span>


[<span data-ttu-id="1bc6f-136">Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc6f-136">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="1bc6f-137">Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc6f-137">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="1bc6f-138">Applicare il blocco telefonico in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bc6f-138">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

