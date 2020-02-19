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
ms.openlocfilehash: 73345feedda10a5cd7979b7683b5a700de578085
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Visualizzazione delle informazioni sulle impostazioni di notifica push in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Le notifiche Push, sotto forma di riquadri, icone o avvisi, possono essere inviate a un dispositivo mobile anche se l'applicazione per dispositivi mobili è inattiva. Le notifiche Push avvisano gli utenti in caso di eventi quali inviti a sessioni di messaggistica istantanea nuovi o senza risposta e di messaggi in segreteria telefonica. È possibile visualizzare le impostazioni delle notifiche push di informazioni per i dispositivi mobili utilizzando il pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Per visualizzare le informazioni di notifica push dal pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione sinistra fare clic su **Client** e quindi fare clic sul pulsante **Configurazione notifiche Push**.

4.  Nella pagina **Configurazione notifiche push** fare clic sul sito che si desidera visualizzare, fare clic sul menu **modifica** e quindi su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni di notifica push tramite i cmdlet di Windows PowerShell

È possibile visualizzare le impostazioni di configurazione di notifica push utilizzando Windows PowerShell e il cmdlet **Get-CsPushNotificationConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-push-notification-configuration-information"></a>Per visualizzare le informazioni di configurazione delle notifiche Push

  - Per visualizzare informazioni su tutte le impostazioni di configurazione delle notifiche push, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsPushNotificationConfiguration
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).

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

