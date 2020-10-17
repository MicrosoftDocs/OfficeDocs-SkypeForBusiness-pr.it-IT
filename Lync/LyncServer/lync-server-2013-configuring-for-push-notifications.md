---
title: 'Lync Server 2013: configurazione delle notifiche push'
description: 'Lync Server 2013: configurazione delle notifiche push.'
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
ms.openlocfilehash: 24c22ff42f666add9eac4966134c88b9bf680046
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548332"
---
# <a name="configuring-for-push-notifications-in-lync-server-2013"></a><span data-ttu-id="dffaf-103">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dffaf-103">Configuring for push notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dffaf-104">_**Ultimo argomento modificato:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="dffaf-104">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="dffaf-105">Le notifiche Push, sotto forma di riquadri, icone o avvisi, possono essere inviate a un dispositivo mobile anche se l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="dffaf-105">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="dffaf-106">Le notifiche Push avvisano gli utenti in caso di eventi quali inviti a sessioni di messaggistica istantanea nuovi o senza risposta e di messaggi in segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="dffaf-106">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="dffaf-107">Il servizio per dispositivi mobili di Lync Server 2013 invia le notifiche al servizio di notifica push di Lync Server basato sul cloud, che invia le notifiche al servizio di notifica push di Apple (APNS) (per un dispositivo Apple che esegue il client per dispositivi mobili Lync 2010) o Microsoft Push Notification Service (MPNS) (per un dispositivo Windows Phone che esegue Lync 2010 mobile o il client mobile Lync 2013)</span><span class="sxs-lookup"><span data-stu-id="dffaf-107">The Lync Server 2013 Mobility Service sends the notifications to the cloud-based Lync Server Push Notification Service, which then sends the notifications to the Apple Push Notification Service (APNS) (for an Apple device running the Lync 2010 Mobile client) or the Microsoft Push Notification Service (MPNS) (for a Windows Phone device running the Lync 2010 Mobile or the Lync 2013 Mobile client).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dffaf-108">Se si utilizza Windows Phone con Lync 2010 mobile o Lync 2013 mobile client, è importante tenere conto della notifica push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-108">If you use Windows Phone with Lync 2010 Mobile or Lync 2013 Mobile client, push notification is an important consideration.</span></span><BR><span data-ttu-id="dffaf-109">Se si utilizza Lync 2010 mobile nei dispositivi Apple, è importante considerare la notifica push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-109">If you use Lync 2010 Mobile on Apple devices, push notification is an important consideration.</span></span><BR><span data-ttu-id="dffaf-110">Se si utilizza Lync 2013 mobile nei dispositivi Apple, non è più necessario inviare una notifica push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-110">If you use Lync 2013 Mobile on Apple devices, you no longer need push notification.</span></span>



</div>

<span data-ttu-id="dffaf-111">Configurare la topologia per supportare le notifiche push eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffaf-111">Configure your topology to support push notifications by doing the following:</span></span>

  - <span data-ttu-id="dffaf-112">Se nell'ambiente è presente un server perimetrale di Lync Server 2010 o Lync Server 2013, è necessario aggiungere un nuovo provider di hosting, Microsoft Lync Online e quindi configurare la Federazione dei provider di hosting tra l'organizzazione e Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dffaf-112">If your environment has a Lync Server 2010 or Lync Server 2013 Edge Server, you need to add a new hosting provider, Microsoft Lync Online, and then set up hosting provider federation between your organization and Lync Online.</span></span>

  - <span data-ttu-id="dffaf-113">Se nell'ambiente è presente un server perimetrale di Office Communications Server 2007 R2, è necessario configurare la federazione SIP diretta con push.lync.com.</span><span class="sxs-lookup"><span data-stu-id="dffaf-113">If your environment has a Office Communications Server 2007 R2 Edge Server, you need to set up direct SIP federation with push.lync.com.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dffaf-114">Push.lync.com è un dominio di Microsoft Office 365 per il servizio di notifica push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-114">Push.lync.com is a Microsoft Office 365 domain for Push Notification Service.</span></span>

    
    </div>

  - <span data-ttu-id="dffaf-115">Per abilitare le notifiche push, è necessario eseguire il cmdlet **Set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="dffaf-115">To enable push notifications, you need to run the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="dffaf-116">Per impostazione predefinita, le notifiche push sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="dffaf-116">By default, push notifications are turned off.</span></span>

  - <span data-ttu-id="dffaf-117">Testare la configurazione della Federazione e le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-117">Test the federation configuration and push notifications.</span></span>

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a><span data-ttu-id="dffaf-118">Per configurare le notifiche push con Lync Server 2013 o Lync Server 2010 Edge Server</span><span class="sxs-lookup"><span data-stu-id="dffaf-118">To configure for push notifications with Lync Server 2013 or Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="dffaf-119">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membri del gruppo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dffaf-119">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dffaf-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dffaf-121">Aggiungere un provider di hosting Lync Server online.</span><span class="sxs-lookup"><span data-stu-id="dffaf-121">Add a Lync Server online hosting provider.</span></span> <span data-ttu-id="dffaf-122">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-122">At the command line, type:</span></span>
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="dffaf-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dffaf-123">For example:</span></span>
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dffaf-124">Non è possibile avere più di una relazione di federazione con un singolo provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="dffaf-124">You cannot have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="dffaf-125">Se è già stato configurato un provider di hosting con una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da LyncOnline.</span><span class="sxs-lookup"><span data-stu-id="dffaf-125">That is, if you have already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, do not add another hosting provider for it, even if the identity of the hosting provider is something other than LyncOnline.</span></span>

    
    </div>

4.  <span data-ttu-id="dffaf-126">Configurare la Federazione dei provider di hosting tra l'organizzazione e il servizio di notifica push in Lync Online.</span><span class="sxs-lookup"><span data-stu-id="dffaf-126">Set up hosting provider federation between your organization and the Push Notification Service at Lync Online.</span></span> <span data-ttu-id="dffaf-127">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-127">At the command line, type:</span></span>
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a><span data-ttu-id="dffaf-128">Per configurare le notifiche push con il server perimetrale di Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="dffaf-128">To configure for push notifications with Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="dffaf-129">Accedere al server perimetrale come membro del gruppo RtcUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="dffaf-129">Log on to the Edge Server as a member of the RtcUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="dffaf-130">Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **strumenti di amministrazione**e quindi **Gestione computer**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-130">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Computer Management**.</span></span>

3.  <span data-ttu-id="dffaf-131">Nell'albero della console espandere **Servizi e applicazioni**, fare clic con il pulsante destro del mouse su **Microsoft Office Communications Server 2007 R2**e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-131">In the console tree, expand **Services and Applications**, right-click **Microsoft Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="dffaf-132">Nella scheda **Consenti** fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-132">On the **Allow** tab, click **Add**.</span></span>

5.  <span data-ttu-id="dffaf-133">Nella finestra di dialogo **Aggiungi partner federato** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="dffaf-133">In the **Add Federated Partner** dialog box, do the following:</span></span>
    
      - <span data-ttu-id="dffaf-134">In **nome di dominio del partner federato**Digitare **push.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-134">In **Federated partner domain name**, type **push.lync.com**.</span></span>
    
      - <span data-ttu-id="dffaf-135">Nel **server perimetrale di accesso partner federato**, digitare **sipfed.online.Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-135">In **Federated partner Access Edge Server**, type **sipfed.online.lync.com**.</span></span>
    
      - <span data-ttu-id="dffaf-136">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-136">Click **OK**.</span></span>

</div>

<div>

## <a name="to-enable-push-notifications"></a><span data-ttu-id="dffaf-137">Per abilitare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="dffaf-137">To enable push notifications</span></span>

1.  <span data-ttu-id="dffaf-138">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dffaf-138">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="dffaf-139">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dffaf-140">Abilitare le notifiche push.</span><span class="sxs-lookup"><span data-stu-id="dffaf-140">Enable push notifications.</span></span> <span data-ttu-id="dffaf-141">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-141">At the command line, type:</span></span>
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  <span data-ttu-id="dffaf-142">Abilitare la Federazione.</span><span class="sxs-lookup"><span data-stu-id="dffaf-142">Enable federation.</span></span> <span data-ttu-id="dffaf-143">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-143">At the command line, type:</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a><span data-ttu-id="dffaf-144">Per testare la Federazione e le notifiche push</span><span class="sxs-lookup"><span data-stu-id="dffaf-144">To test federation and push notifications</span></span>

1.  <span data-ttu-id="dffaf-145">Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membri del ruolo CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="dffaf-145">Log on to a computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="dffaf-146">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dffaf-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dffaf-147">Testare la configurazione della Federazione.</span><span class="sxs-lookup"><span data-stu-id="dffaf-147">Test the federation configuration.</span></span> <span data-ttu-id="dffaf-148">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-148">At the command line, type:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    <span data-ttu-id="dffaf-149">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dffaf-149">For example:</span></span>
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  <span data-ttu-id="dffaf-150">Testare le notifiche push</span><span class="sxs-lookup"><span data-stu-id="dffaf-150">Test push notifications.</span></span> <span data-ttu-id="dffaf-151">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dffaf-151">At the command line, type:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    <span data-ttu-id="dffaf-152">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="dffaf-152">For example:</span></span>
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dffaf-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dffaf-153">See Also</span></span>


[<span data-ttu-id="dffaf-154">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="dffaf-154">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[<span data-ttu-id="dffaf-155">Test-CsMcxPushNotification</span><span class="sxs-lookup"><span data-stu-id="dffaf-155">Test-CsMcxPushNotification</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

