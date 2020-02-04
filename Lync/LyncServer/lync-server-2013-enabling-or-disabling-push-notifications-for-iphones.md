---
title: 'Lync Server 2013: abilitare o disabilitare le notifiche push per iPhone'
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
ms.openlocfilehash: a73d0f32da5063f98da662e85ec531de6801a428
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735646"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="3338c-102">Abilitazione o disabilitazione delle notifiche push per iPhones in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3338c-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3338c-103">_**Argomento Ultima modifica:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3338c-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3338c-104">Le notifiche push, in forma di badge, icone o avvisi, possono essere inviate a un iPhone anche quando l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="3338c-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="3338c-105">Le notifiche push notificano a un utente gli eventi, ad esempio un invito ISTANTANEo o un messaggio di posta elettronica nuovo o perso.</span><span class="sxs-lookup"><span data-stu-id="3338c-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="3338c-106">È possibile abilitare o disabilitare le notifiche push per iPhone usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3338c-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="3338c-107">Per abilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3338c-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3338c-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3338c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3338c-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3338c-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3338c-110">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3338c-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3338c-111">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della notifica push** .</span><span class="sxs-lookup"><span data-stu-id="3338c-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="3338c-112">Nella pagina di **configurazione della notifica push** fare clic sul sito che si vuole modificare, fare clic sul menu **modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3338c-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3338c-113">Fare clic sulla casella di controllo **Abilita notifiche push Apple** .</span><span class="sxs-lookup"><span data-stu-id="3338c-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="3338c-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3338c-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="3338c-115">Per disabilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="3338c-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3338c-116">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3338c-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3338c-117">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3338c-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3338c-118">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3338c-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3338c-119">Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della notifica push** .</span><span class="sxs-lookup"><span data-stu-id="3338c-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="3338c-120">Nella pagina di **configurazione della notifica push** fare clic sul sito che si vuole modificare, fare clic sul menu **modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="3338c-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3338c-121">Deselezionare la casella di controllo **Abilita notifiche push Apple** .</span><span class="sxs-lookup"><span data-stu-id="3338c-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="3338c-122">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3338c-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3338c-123">Abilitare o disabilitare le notifiche push per iPhone usando i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3338c-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3338c-124">Le notifiche push a Apple iPhone possono essere abilitate o disabilitate usando il cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="3338c-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="3338c-125">Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3338c-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3338c-126">Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="3338c-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="3338c-127">Per abilitare le notifiche push per iPhone</span><span class="sxs-lookup"><span data-stu-id="3338c-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="3338c-128">Per abilitare le notifiche push per iPhone, imposta il valore della proprietà EnableApplePushNotificationService su true ($True).</span><span class="sxs-lookup"><span data-stu-id="3338c-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="3338c-129">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3338c-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="3338c-130">Per disabilitare le notifiche push per iPhone</span><span class="sxs-lookup"><span data-stu-id="3338c-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="3338c-131">Per disabilitare le notifiche push per iPhone, imposta il valore della proprietà EnableApplePushNotificationService su false ($False).</span><span class="sxs-lookup"><span data-stu-id="3338c-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="3338c-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3338c-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="3338c-133">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3338c-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3338c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3338c-134">See Also</span></span>


[<span data-ttu-id="3338c-135">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3338c-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

