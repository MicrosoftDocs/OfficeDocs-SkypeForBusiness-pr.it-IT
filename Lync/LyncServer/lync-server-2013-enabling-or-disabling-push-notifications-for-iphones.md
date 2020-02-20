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

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>Abilitazione o disabilitazione delle notifiche push per i iPhones in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Le notifiche push, sotto forma di badge, icone o avvisi, possono essere inviate a un iPhone anche quando l'applicazione per dispositivi mobili è inattiva. Le notifiche push consentono di notificare a un utente eventi quali inviti di messaggistica immediata nuovi o senza risposta e i messaggi vocali. È possibile abilitare o disabilitare le notifiche push per iPhone utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Per abilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.

4.  Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera modificare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.

5.  Selezionare la casella di controllo **Abilita notifiche push di Apple**.

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>Per disabilitare le notifiche push per iPhone tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.

4.  Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera modificare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.

5.  Deselezionare la casella di controllo **Abilita notifiche push di Apple**.

6.  Fare clic su  **Commit **.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione delle notifiche push per iPhone tramite i cmdlet di Windows PowerShell

Le notifiche push su Apple iPhone possono essere abilitate o disabilitate utilizzando il cmdlet **Set-CsPushNotificationConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>Per abilitare le notifiche push per iPhone

  - Per abilitare le notifiche push per iPhone impostare il valore della proprietà EnableApplePushNotificationService su true ($True). Ad esempio:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>Per disabilitare le notifiche push per iPhone

  - Per disabilitare le notifiche push per iPhone, impostare il valore della proprietà EnableApplePushNotificationService su false ($False). Ad esempio:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).

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

