---
title: 'Lync Server 2013: visualizzazione delle informazioni sulle impostazioni di notifica push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c74bbc90b0b7ef27da6b38b626fc91bc04383685
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="4306b-102">Visualizzazione delle informazioni sulle impostazioni di notifica push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4306b-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4306b-103">_**Ultimo argomento modificato:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4306b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4306b-104">Le notifiche Push, sotto forma di riquadri, icone o avvisi, possono essere inviate a un dispositivo mobile anche se l'applicazione per dispositivi mobili è inattiva.</span><span class="sxs-lookup"><span data-stu-id="4306b-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="4306b-105">Le notifiche Push avvisano gli utenti in caso di eventi quali inviti a sessioni di messaggistica istantanea nuovi o senza risposta e di messaggi in segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="4306b-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="4306b-106">È possibile visualizzare le impostazioni delle notifiche push di informazioni per i dispositivi mobili utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4306b-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="4306b-107">Per visualizzare le informazioni di notifica push dal pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="4306b-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4306b-108">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4306b-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4306b-109">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4306b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4306b-110">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4306b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4306b-111">Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.</span><span class="sxs-lookup"><span data-stu-id="4306b-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4306b-112">Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera visualizzare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4306b-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4306b-113">Visualizzazione delle informazioni di notifica push tramite i cmdlet di Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4306b-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4306b-114">È possibile visualizzare le impostazioni di configurazione di notifica push utilizzando Windows PowerShell e il cmdlet **Get-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4306b-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="4306b-115">È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4306b-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4306b-116">Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.</span><span class="sxs-lookup"><span data-stu-id="4306b-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="4306b-117">Per visualizzare le informazioni di configurazione delle notifiche Push</span><span class="sxs-lookup"><span data-stu-id="4306b-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="4306b-118">Per visualizzare informazioni su tutte le impostazioni di configurazione delle notifiche push, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="4306b-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="4306b-119">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="4306b-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="4306b-120">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4306b-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4306b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4306b-121">See Also</span></span>


[<span data-ttu-id="4306b-122">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4306b-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

