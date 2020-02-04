---
title: 'Lync Server 2013: Configurazione delle notifiche push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="bce2a-102">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bce2a-102">Configuring for push notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bce2a-103">_**Argomento Ultima modifica:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="bce2a-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="bce2a-104">Le notifiche push, in forma di badge, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="bce2a-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="bce2a-105">Le notifiche push notificano a un utente gli eventi, ad esempio un invito ISTANTANEo o un messaggio di posta elettronica nuovo o perso.</span><span class="sxs-lookup"><span data-stu-id="bce2a-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="bce2a-106">Il servizio di mobilità di Lync Server 2013 invia le notifiche al servizio di notifica push di Lync Server basato su cloud, che invia le notifiche al servizio di notifica push di Apple (APN) (per un dispositivo Apple che esegue il client mobile Lync 2010) o al Servizio di notifica push Microsoft (MPNS) (per un dispositivo Windows Phone che gestisce Lync 2010 mobile o Lync 2013 Mobile Client).</span><span class="sxs-lookup"><span data-stu-id="bce2a-106">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bce2a-107">Se si usa Windows Phone con Lync 2010 mobile o Lync 2013 mobile client, la notifica push è una considerazione importante.</span><span class="sxs-lookup"><span data-stu-id="bce2a-107">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="bce2a-108">Se si usa Lync 2010 Mobile su dispositivi Apple, la notifica push è una considerazione importante.</span><span class="sxs-lookup"><span data-stu-id="bce2a-108">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="bce2a-109">Se si usa Lync 2013 Mobile su dispositivi Apple, non è più necessario notifica push.</span><span class="sxs-lookup"><span data-stu-id="bce2a-109">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="bce2a-110">Configurare la topologia per supportare le notifiche push eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bce2a-110">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="bce2a-111">Se l'ambiente in cui è installato Lync Server 2010 o Lync Server 2013 Edge Server, è necessario aggiungere un nuovo provider di hosting, Microsoft Lync Online e quindi configurare la Federazione del provider di hosting tra l'organizzazione e Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bce2a-111">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="bce2a-112">Se l'ambiente ha un server perimetrale di Office Communications Server 2007 R2, è necessario configurare la federazione SIP diretta con push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bce2a-112">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bce2a-113">Push.lync.com è un dominio di Microsoft Office 365 per il servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="bce2a-113">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="bce2a-114">Per abilitare le notifiche push, è necessario eseguire il cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="bce2a-114">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="bce2a-115">Per impostazione predefinita, le notifiche push sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="bce2a-115">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="bce2a-116">Verificare la configurazione della Federazione e le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="bce2a-116">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="bce2a-117">Per configurare le notifiche push con Lync Server 2013 o Lync Server 2010 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bce2a-117">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="bce2a-118">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del gruppo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bce2a-118">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="bce2a-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bce2a-120">Aggiungere un provider di hosting di Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="bce2a-120">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="bce2a-121">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-121">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="bce2a-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bce2a-122">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bce2a-123">Non è possibile avere più relazioni tra le federazioni con un singolo provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="bce2a-123">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="bce2a-124">Se invece hai già configurato un provider di hosting che ha una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="bce2a-124">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="bce2a-125">Configurare la Federazione del provider di hosting tra l'organizzazione e il servizio di notifica push su Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bce2a-125">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="bce2a-126">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-126">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="bce2a-127">Per configurare le notifiche push con Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="bce2a-127">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="bce2a-128">Accedere all'Edge Server come membro del gruppo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bce2a-128">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="bce2a-129">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **strumenti di amministrazione**e quindi su **Gestione computer**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-129">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="bce2a-130">Nell'albero della console espandere **Servizi e applicazioni**, fare clic con il pulsante destro del mouse su **Microsoft Office Communications Server 2007 R2**e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-130">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="bce2a-131">Nella scheda **Consenti** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-131">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="bce2a-132">Nella finestra di dialogo **Aggiungi partner federativo** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bce2a-132">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="bce2a-133">In **nome di dominio federativo partner**Digitare **push.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-133">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="bce2a-134">Nel **server di Access Edge partner federati**Digitare **sipfed.online.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-134">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="bce2a-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-135">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="bce2a-136">Per abilitare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="bce2a-136">To enable push notifications</span></span>

1.  <span data-ttu-id="bce2a-137">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bce2a-137">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="bce2a-138">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bce2a-139">Abilitare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="bce2a-139">Enable push notifications.</span></span> <span data-ttu-id="bce2a-140">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-140">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="bce2a-141">Abilita federazione.</span><span class="sxs-lookup"><span data-stu-id="bce2a-141">Enable federation.</span></span> <span data-ttu-id="bce2a-142">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-142">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="bce2a-143">Per testare la Federazione e le notifiche push</span><span class="sxs-lookup"><span data-stu-id="bce2a-143">To test federation and push notifications</span></span>

1.  <span data-ttu-id="bce2a-144">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="bce2a-144">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="bce2a-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="bce2a-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bce2a-146">Verificare la configurazione della Federazione.</span><span class="sxs-lookup"><span data-stu-id="bce2a-146">Test the federation configuration.</span></span> <span data-ttu-id="bce2a-147">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-147">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="bce2a-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bce2a-148">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="bce2a-149">Verificare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="bce2a-149">Test push notifications.</span></span> <span data-ttu-id="bce2a-150">Nella riga di comando digitare:</span><span class="sxs-lookup"><span data-stu-id="bce2a-150">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="bce2a-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bce2a-151">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bce2a-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bce2a-152">See Also</span></span>


[<span data-ttu-id="bce2a-153">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="bce2a-153">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="bce2a-154">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="bce2a-154">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

