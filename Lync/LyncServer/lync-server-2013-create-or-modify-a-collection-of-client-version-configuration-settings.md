---
title: Creare o modificare una raccolta di impostazioni di configurazione della versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84df13c7abbc98cbb90c5b59a6b0717deb855e28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="abcb0-102">Creare o modificare una raccolta di impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abcb0-102">Create or modify a collection of client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abcb0-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="abcb0-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="abcb0-104">Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="abcb0-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="abcb0-105">La configurazione della versione client globale viene installata con Lync Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="abcb0-105">The global client version configuration installs with Lync Server and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="abcb0-106">È anche possibile configurare le impostazioni di configurazione della versione client per singoli siti.</span><span class="sxs-lookup"><span data-stu-id="abcb0-106">You can also configure client version configuration settings for individual sites.</span></span> <span data-ttu-id="abcb0-107">È possibile creare o modificare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="abcb0-107">You can create or modify client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="abcb0-108">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="abcb0-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="abcb0-109">Per creare o modificare le impostazioni di configurazione della versione client tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="abcb0-109">To create or modify client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="abcb0-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="abcb0-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="abcb0-111">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="abcb0-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="abcb0-112">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="abcb0-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="abcb0-113">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della versione client** .</span><span class="sxs-lookup"><span data-stu-id="abcb0-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="abcb0-114">Nella pagina **Configurazione versione client** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="abcb0-114">On the **Client Version Configuration** page, do the following:</span></span>
    
      - <span data-ttu-id="abcb0-115">Per creare una nuova configurazione, fare clic su **nuovo**, selezionare un sito, fare clic su nome **OK** e aggiornare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="abcb0-115">To create a new configuration, click **New**, select a site, click **OK** name, and update the settings.</span></span>
    
      - <span data-ttu-id="abcb0-116">Per modificare una configurazione, selezionare la configurazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e apportare modifiche alle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="abcb0-116">To modify a configuration, select the configuration, click **Edit**, click **Show details**, and make changes to the settings.</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="abcb0-117">Creazione o modifica delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abcb0-117">Creating or Modifying Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="abcb0-118">Puoi creare le impostazioni di configurazione della versione client usando il cmdlet **New-CsClientVersionConfiguration** e modificarle usando il cmdlet **set-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="abcb0-118">You can create client version configuration settings by using the **New-CsClientVersionConfiguration** cmdlet, and modify them by using the **Set-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="abcb0-119">Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="abcb0-119">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="abcb0-120">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="abcb0-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a><span data-ttu-id="abcb0-121">Per creare una nuova raccolta di impostazioni di configurazione della versione client</span><span class="sxs-lookup"><span data-stu-id="abcb0-121">To create a new collection of client version configuration settings</span></span>

  - <span data-ttu-id="abcb0-122">Il comando seguente crea una nuova raccolta di impostazioni di configurazione della versione client applicata al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="abcb0-122">The following command creates a new collection of client version configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="abcb0-123">In questo esempio, il controllo delle versioni dei client è disabilitato per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="abcb0-123">In this example, client versioning is disabled for the Redmond site.</span></span>
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a><span data-ttu-id="abcb0-124">Per abilitare il controllo delle versioni del client per un sito</span><span class="sxs-lookup"><span data-stu-id="abcb0-124">To enable client versioning for a site</span></span>

  - <span data-ttu-id="abcb0-125">Questo comando consente di abilitare il controllo delle versioni del client per il sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="abcb0-125">This command enables client versioning for the Redmond site.</span></span>
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a><span data-ttu-id="abcb0-126">Per disabilitare il controllo delle versioni del client in tutta l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="abcb0-126">To disable client versioning throughout the organization</span></span>

  - <span data-ttu-id="abcb0-127">In questo esempio, il controllo delle versioni dei client è disabilitato per tutte le impostazioni di configurazione della versione client in uso nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abcb0-127">In this example, client versioning is disabled for all the client version configuration settings in use in the organization.</span></span>
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

<span data-ttu-id="abcb0-128">Per informazioni dettagliate, vedere l'argomento della Guida per i cmdlet [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="abcb0-128">For details, see the Help topic for the [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) and [Set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) cmdlets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

