---
title: 'Lync Server 2013: visualizzazione dei criteri PIN inforrmation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5dad362c4291f83c6feb261247a0b90ba47e16
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Visualizzazione dei criteri PIN inforrmation in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile utilizzare la scheda **criteri PIN** per visualizzare l'autenticazione PIN (Personal Identification Number) degli utenti che si connettono a Lync 2013 con telefoni IP. Per utilizzare l'autenticazione tramite PIN, verificare che sia selezionata l'opzione **Abilita autenticazione PIN** nelle impostazioni relative ai servizi Web. Per ulteriori informazioni, vedere [modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Effettuare la procedura seguente per modificare i criteri PIN a livello di utente o a livello di sito.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Per visualizzare le informazioni su un criterio PIN nel pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a un computer nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Sicurezza** e quindi su **Criteri PIN**.

4.  Nella pagina **Criteri PIN** scegliere i criteri, fare clic su **Modifica** e quindi su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Visualizzazione dei criteri PIN tramite i cmdlet di Windows PowerShell

È inoltre possibile visualizzare i criteri PIN utilizzando Windows PowerShell e il cmdlet Get-CsPinPolicy. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-pin-policies"></a>Per visualizzare i criteri PIN

  - Per visualizzare informazioni su tutti i criteri PIN, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsPinPolicy
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modificare le impostazioni di configurazione del servizio Web esistenti in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Creare un nuovo criterio PIN in Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

