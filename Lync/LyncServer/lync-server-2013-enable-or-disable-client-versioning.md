---
title: 'Lync Server 2013: abilitare o disabilitare il controllo delle versioni dei client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a0f6e5306e30baca3c2a8178a0d979f82d55481
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a><span data-ttu-id="37bae-102">Abilitare o disabilitare il controllo delle versioni client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37bae-102">Enable or disable client versioning in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37bae-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="37bae-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="37bae-104">Le impostazioni di configurazione della versione client vengono usate per attivare o disattivare il controllo della versione client, sia a livello globale che per siti particolari.</span><span class="sxs-lookup"><span data-stu-id="37bae-104">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span> <span data-ttu-id="37bae-105">La configurazione della versione client globale viene installata con Lync Server 2013 e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="37bae-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="37bae-106">Quando la configurazione globale è abilitata, i criteri di versione client in vigore saranno effettivi quando gli utenti tenteranno di accedere.</span><span class="sxs-lookup"><span data-stu-id="37bae-106">When the global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="37bae-107">È possibile disabilitare la configurazione della versione client globale se non si vuole che venga eseguito alcun controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="37bae-107">You can disable the global client version configuration if you do not want any client version control to occur.</span></span> <span data-ttu-id="37bae-108">È possibile abilitare o disabilitare il controllo delle versioni del client da Lync Server 2013 Control Panel o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="37bae-108">You can enable or disable client versioning from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37bae-109">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="37bae-109">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a><span data-ttu-id="37bae-110">Per abilitare o disabilitare il controllo delle versioni del client tramite il pannello di controlli di Lync Server</span><span class="sxs-lookup"><span data-stu-id="37bae-110">To enable or disable client versioning by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="37bae-111">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="37bae-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="37bae-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37bae-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="37bae-113">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="37bae-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="37bae-114">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della versione client** .</span><span class="sxs-lookup"><span data-stu-id="37bae-114">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="37bae-115">Effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="37bae-115">Do the following:</span></span>
    
      - <span data-ttu-id="37bae-116">Per abilitare o disabilitare globalmente il controllo delle versioni dei client, fare doppio clic sulla configurazione **globale** e quindi modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="37bae-116">To globally enable or disable client versioning, double-click the **Global** configuration, and then modify the settings.</span></span>
    
      - <span data-ttu-id="37bae-117">Per abilitare o disabilitare il controllo delle versioni dei client per un determinato sito, fare clic su **nuovo**, selezionare il sito, fare clic su **OK**e quindi modificare le impostazioni per il sito.</span><span class="sxs-lookup"><span data-stu-id="37bae-117">To enable or disable client versioning for a particular site, click **New**, select the site, click **OK**, and then modify the settings for the site.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37bae-118">Abilitazione o disabilitazione del controllo delle versioni client con i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37bae-118">Enabling or Disabling Client Versioning by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="37bae-119">Puoi abilitare o disabilitare il controllo delle versioni del client usando il cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="37bae-119">You can enable or disable client versioning by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="37bae-120">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37bae-120">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="37bae-121">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="37bae-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-client-versioning"></a><span data-ttu-id="37bae-122">Per abilitare il controllo delle versioni del client</span><span class="sxs-lookup"><span data-stu-id="37bae-122">To enable client versioning</span></span>

  - <span data-ttu-id="37bae-123">Puoi abilitare il controllo delle versioni del client impostando la proprietà **Enabled** su True ($true).</span><span class="sxs-lookup"><span data-stu-id="37bae-123">You can enable client versioning by setting the **Enabled** property to True ($True).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a><span data-ttu-id="37bae-124">Per disabilitare il controllo delle versioni del client</span><span class="sxs-lookup"><span data-stu-id="37bae-124">To disable client versioning</span></span>

  - <span data-ttu-id="37bae-125">Puoi disabilitare il controllo delle versioni dei client impostando la proprietà **Enabled** su False ($false).</span><span class="sxs-lookup"><span data-stu-id="37bae-125">You can disable client versioning by setting the **Enabled** property to False ($False).</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<span data-ttu-id="37bae-126">Per informazioni dettagliate, vedere l'argomento della Guida relativo al cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="37bae-126">For details, see the Help topic for the [Set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

