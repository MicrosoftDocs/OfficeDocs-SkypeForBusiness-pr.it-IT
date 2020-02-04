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

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configurazione delle notifiche push in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-12_

Le notifiche push, in forma di badge, icone o avvisi, possono essere inviate a un dispositivo mobile anche quando l'applicazione per dispositivi mobili è inattiva. Le notifiche push notificano a un utente gli eventi, ad esempio un invito ISTANTANEo o un messaggio di posta elettronica nuovo o perso. Il servizio di mobilità di Lync Server 2013 invia le notifiche al servizio di notifica push di Lync Server basato su cloud, che invia le notifiche al servizio di notifica push di Apple (APN) (per un dispositivo Apple che esegue il client mobile Lync 2010) o al Servizio di notifica push Microsoft (MPNS) (per un dispositivo Windows Phone che gestisce Lync 2010 mobile o Lync 2013 Mobile Client).

<div>


> [!IMPORTANT]  
> Se si usa Windows Phone con Lync 2010 mobile o Lync 2013 mobile client, la notifica push è una considerazione importante.<BR>Se si usa Lync 2010 Mobile su dispositivi Apple, la notifica push è una considerazione importante.<BR>Se si usa Lync 2013 Mobile su dispositivi Apple, non è più necessario notifica push.



</div>

Configurare la topologia per supportare le notifiche push eseguendo le operazioni seguenti:

  - Se l'ambiente in cui è installato Lync Server 2010 o Lync Server 2013 Edge Server, è necessario aggiungere un nuovo provider di hosting, Microsoft Lync Online e quindi configurare la Federazione del provider di hosting tra l'organizzazione e Lync Online.

  - Se l'ambiente ha un server perimetrale di Office Communications Server 2007 R2, è necessario configurare la federazione SIP diretta con push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com è un dominio di Microsoft Office 365 per il servizio di notifica push.

    
    </div>

  - Per abilitare le notifiche push, è necessario eseguire il cmdlet **Set-CsPushNotificationConfiguration** . Per impostazione predefinita, le notifiche push sono disattivate.

  - Verificare la configurazione della Federazione e le notifiche push.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Per configurare le notifiche push con Lync Server 2013 o Lync Server 2010 Edge Server

1.  Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del gruppo RtcUniversalServerAdmins.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Aggiungere un provider di hosting di Lync Server online. Nella riga di comando digitare:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Ad esempio:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Non è possibile avere più relazioni tra le federazioni con un singolo provider di hosting. Se invece hai già configurato un provider di hosting che ha una relazione di federazione con sipfed.online.lync.com, non aggiungere un altro provider di hosting, anche se l'identità del provider di hosting è diversa da LyncOnline.

    
    </div>

4.  Configurare la Federazione del provider di hosting tra l'organizzazione e il servizio di notifica push su Lync Online. Nella riga di comando digitare:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Per configurare le notifiche push con Office Communications Server 2007 R2 Edge Server

1.  Accedere all'Edge Server come membro del gruppo RtcUniversalServerAdmins.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **strumenti di amministrazione**e quindi su **Gestione computer**.

3.  Nell'albero della console espandere **Servizi e applicazioni**, fare clic con il pulsante destro del mouse su **Microsoft Office Communications Server 2007 R2**e quindi scegliere **proprietà**.

4.  Nella scheda **Consenti** fare clic su **Aggiungi**.

5.  Nella finestra di dialogo **Aggiungi partner federativo** eseguire le operazioni seguenti:
    
      - In **nome di dominio federativo partner**Digitare **push.Lync.com**.
    
      - Nel **server di Access Edge partner federati**Digitare **sipfed.online.Lync.com**.
    
      - Fare clic su **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Per abilitare le notifiche push

1.  Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Abilitare le notifiche push. Nella riga di comando digitare:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Abilita federazione. Nella riga di comando digitare:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Per testare la Federazione e le notifiche push

1.  Accedere a un computer in cui sono installati Lync Server Management Shell e OCSCore come membro del ruolo CsAdministrator.

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Verificare la configurazione della Federazione. Nella riga di comando digitare:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Ad esempio:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Verificare le notifiche push. Nella riga di comando digitare:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Ad esempio:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

