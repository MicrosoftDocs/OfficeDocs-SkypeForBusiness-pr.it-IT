---
title: 'Lync Server 2013: attivazione o disattivazione delle notifiche push per i iPhones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9af351e2d5710d3263faf0afeb6ab8aa36d5e568
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="e039a-102">Abilitazione o disabilitazione delle notifiche push per i iPhones in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e039a-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e039a-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e039a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e039a-104">Le notifiche push, sotto forma di badge, icone o avvisi, possono essere inviate a un iPhone anche quando l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="e039a-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="e039a-105">Le notifiche push consentono di notificare a un utente eventi quali inviti di messaggistica immediata nuovi o senza risposta e i messaggi vocali.</span><span class="sxs-lookup"><span data-stu-id="e039a-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="e039a-106">È possibile abilitare o disabilitare le notifiche push per iPhone utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e039a-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="e039a-107">Per abilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e039a-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e039a-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e039a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e039a-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e039a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e039a-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e039a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e039a-111">Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.</span><span class="sxs-lookup"><span data-stu-id="e039a-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e039a-112">Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera modificare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e039a-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e039a-113">Selezionare la casella di controllo **Abilita notifiche push di Apple**.</span><span class="sxs-lookup"><span data-stu-id="e039a-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="e039a-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e039a-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="e039a-115">Per disabilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="e039a-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e039a-116">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e039a-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e039a-117">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e039a-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e039a-118">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e039a-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e039a-119">Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.</span><span class="sxs-lookup"><span data-stu-id="e039a-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="e039a-120">Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera modificare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e039a-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e039a-121">Deselezionare la casella di controllo **Abilita notifiche push di Apple**.</span><span class="sxs-lookup"><span data-stu-id="e039a-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="e039a-122">Fare clic su  \*\*Commit \*\*.</span><span class="sxs-lookup"><span data-stu-id="e039a-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e039a-123">Abilitazione o disabilitazione delle notifiche push per iPhone tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e039a-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e039a-124">Le notifiche push su Apple iPhone possono essere abilitate o disabilitate utilizzando il cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e039a-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="e039a-125">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e039a-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e039a-126">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="e039a-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="e039a-127">Per abilitare le notifiche push per iPhone</span><span class="sxs-lookup"><span data-stu-id="e039a-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="e039a-128">Per abilitare le notifiche push per iPhone impostare il valore della proprietà EnableApplePushNotificationService su true ($True).</span><span class="sxs-lookup"><span data-stu-id="e039a-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="e039a-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e039a-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="e039a-130">Per disabilitare le notifiche push per iPhone</span><span class="sxs-lookup"><span data-stu-id="e039a-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="e039a-131">Per disabilitare le notifiche push per iPhone, impostare il valore della proprietà EnableApplePushNotificationService su false ($False).</span><span class="sxs-lookup"><span data-stu-id="e039a-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="e039a-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e039a-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="e039a-133">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="e039a-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e039a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e039a-134">See Also</span></span>


[<span data-ttu-id="e039a-135">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e039a-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

