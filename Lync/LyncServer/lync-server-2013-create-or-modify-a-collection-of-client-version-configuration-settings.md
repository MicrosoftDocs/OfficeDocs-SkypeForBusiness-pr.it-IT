---
title: Creare o modificare una raccolta di impostazioni di configurazione della versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56061b4d6c801263c30e471acef70e68c10bfea1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521743"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="7cd89-102">Creare o modificare una raccolta di impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7cd89-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7cd89-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7cd89-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7cd89-104">Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="7cd89-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="7cd89-105">La configurazione globale della versione client viene installata con Lync Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="7cd89-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="7cd89-106">È inoltre possibile configurare le impostazioni di configurazione della versione client per i singoli siti.</span><span class="sxs-lookup"><span data-stu-id="7cd89-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="7cd89-107">È possibile creare o modificare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7cd89-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7cd89-108">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="7cd89-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="7cd89-109">Per creare o modificare le impostazioni di configurazione della versione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7cd89-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7cd89-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7cd89-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7cd89-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7cd89-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7cd89-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7cd89-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7cd89-113">Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .</span><span class="sxs-lookup"><span data-stu-id="7cd89-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="7cd89-114">Nella pagina **Configurazione versione client** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7cd89-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="7cd89-115">Per creare una nuova configurazione, fare clic su **nuovo**, selezionare un sito, fare clic su **OK** e aggiornare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7cd89-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="7cd89-116">Per modificare una configurazione, selezionare la configurazione, fare clic su **modifica**, su **Mostra dettagli**e apportare modifiche alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="7cd89-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7cd89-117">Creazione o modifica delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7cd89-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7cd89-118">Per creare le impostazioni di configurazione della versione client, è possibile utilizzare il cmdlet **New-CsClientVersionConfiguration** e modificarle utilizzando il cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7cd89-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="7cd89-119">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7cd89-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7cd89-120">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="7cd89-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="7cd89-121">Per creare una nuova raccolta di impostazioni di configurazione della versione client</span><span class="sxs-lookup"><span data-stu-id="7cd89-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="7cd89-122">Il comando seguente consente di creare una nuova raccolta di impostazioni di configurazione della versione client applicate al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="7cd89-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="7cd89-123">In questo esempio, il controllo delle versioni client è disabilitato per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="7cd89-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="7cd89-124">Per abilitare il controllo delle versioni dei client per un sito</span><span class="sxs-lookup"><span data-stu-id="7cd89-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="7cd89-125">Questo comando consente di abilitare il controllo delle versioni client per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="7cd89-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="7cd89-126">Per disabilitare il controllo delle versioni client all'interno dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="7cd89-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="7cd89-127">In questo esempio, il controllo delle versioni client è disabilitato per tutte le impostazioni di configurazione della versione client in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7cd89-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="7cd89-128">Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="7cd89-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

