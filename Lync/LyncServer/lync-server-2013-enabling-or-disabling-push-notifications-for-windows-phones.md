---
title: 'Lync Server 2013: abilitare o disabilitare le notifiche push per i telefoni Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b25594948f1d88caaca3dd07ca035b20f9f00079
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Abilitazione o disabilitazione delle notifiche push per i telefoni Windows in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le notifiche push, in forma di badge, icone o avvisi, possono essere inviate a un Windows Phone anche quando l'applicazione per dispositivi mobili è inattiva. Le notifiche push notificano a un utente gli eventi, ad esempio un invito ISTANTANEo o un messaggio di posta elettronica nuovo o perso. È possibile abilitare o disabilitare le notifiche push per i dispositivi Windows Phone usando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Per abilitare le notifiche push per Windows Phone tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della notifica push** .

4.  Nella pagina di **configurazione della notifica push** fare clic sul sito che si vuole modificare, fare clic sul menu **modifica** e quindi fare clic su **Mostra dettagli**.

5.  Fare clic sulla casella di controllo **Attiva notifiche push Microsoft** .

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Per disabilitare le notifiche push per Windows Phone tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della notifica push** .

4.  Nella pagina di **configurazione della notifica push** fare clic sul sito che si vuole modificare, fare clic sul menu **modifica** e quindi fare clic su **Mostra dettagli**.

5.  Deselezionare la casella di controllo **Abilita notifiche push Microsoft** .

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione delle notifiche push per Windows Phone tramite i cmdlet di Windows PowerShell

Puoi abilitare o disabilitare le notifiche push per Windows Phone usando il cmdlet **Set-CsPushNotificationConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Per abilitare le notifiche push per Windows Phone

  - Per abilitare le notifiche push per Windows Phone, imposta il valore della proprietà EnableMicrosoftPushNotificationService su true ($True). Ad esempio:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Per disabilitare le notifiche push per Windows Phone

  - Per disabilitare le notifiche push per Windows Phone, imposta il valore della proprietà EnableMicrosoftPushNotificationService su false ($False). Ad esempio:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione delle notifiche push in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

