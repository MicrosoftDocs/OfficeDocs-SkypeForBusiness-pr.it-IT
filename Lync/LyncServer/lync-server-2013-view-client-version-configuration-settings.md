---
title: 'Lync Server 2013: visualizzare le impostazioni di configurazione della versione client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e376525d2e00a6b2c98674855ccb314984364a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="edd5b-102">Visualizzare le impostazioni di configurazione della versione client in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="edd5b-102">View client version configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edd5b-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="edd5b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="edd5b-104">Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client.</span><span class="sxs-lookup"><span data-stu-id="edd5b-104">Client version configuration settings are used to turn client version control on or off.</span></span> <span data-ttu-id="edd5b-105">La configurazione globale della versione client viene installata con Lync Server 2013 e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server.</span><span class="sxs-lookup"><span data-stu-id="edd5b-105">The global client version configuration installs with Lync Server 2013 and is used to enable or disable client version control for the entire server deployment.</span></span> <span data-ttu-id="edd5b-106">Quando la configurazione globale è abilitata, tutti i criteri di versione client sul posto avranno effetto quando gli utenti tentano di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="edd5b-106">When the Global configuration is enabled, any client version policies you have in place will take effect when users attempt to log on.</span></span> <span data-ttu-id="edd5b-107">È possibile visualizzare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="edd5b-107">You can view client version configuration settings from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edd5b-108">Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.</span><span class="sxs-lookup"><span data-stu-id="edd5b-108">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="edd5b-109">Per visualizzare le impostazioni di configurazione della versione client utilizzando il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="edd5b-109">To view client version configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="edd5b-110">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="edd5b-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="edd5b-111">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="edd5b-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="edd5b-112">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="edd5b-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="edd5b-113">Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .</span><span class="sxs-lookup"><span data-stu-id="edd5b-113">In the left navigation bar, click **Clients**, and then click the **Client Version Configuration** navigation button.</span></span>

4.  <span data-ttu-id="edd5b-114">Fare doppio clic sul nome della configurazione della versione client che si desidera visualizzare.</span><span class="sxs-lookup"><span data-stu-id="edd5b-114">Double-click the name of the client version configuration you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="edd5b-115">Visualizzazione delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="edd5b-115">Viewing Client Version Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="edd5b-116">È possibile visualizzare le impostazioni di configurazione della versione client utilizzando il cmdlet **Get-CsClientVersionConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="edd5b-116">You can view client version configuration settings by using the **Get-CsClientVersionConfiguration** cmdlet.</span></span> <span data-ttu-id="edd5b-117">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="edd5b-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="edd5b-118">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="edd5b-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-configuration-information"></a><span data-ttu-id="edd5b-119">Per visualizzare le informazioni di configurazione della versione client</span><span class="sxs-lookup"><span data-stu-id="edd5b-119">To view client version configuration information</span></span>

  - <span data-ttu-id="edd5b-120">Per visualizzare informazioni su tutte le impostazioni di configurazione della versione client, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="edd5b-120">To view information about all your client version configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionConfiguration
    
    <span data-ttu-id="edd5b-121">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="edd5b-121">That will return information similar to this:</span></span>
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

<span data-ttu-id="edd5b-122">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="edd5b-122">For details, see the Help topic for the [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

