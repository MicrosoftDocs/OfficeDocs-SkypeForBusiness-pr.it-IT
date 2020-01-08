---
title: 'Lync Server 2013: abilitare la registrazione dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12359e331e9abd2767285a5ef8c32d56433731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a>Abilitare la registrazione dettagli chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Registrazione dettagli chiamata (CDR) registra l'uso e le informazioni di diagnostica sulle attività peer-to-peer, tra cui messaggistica istanza, chiamate VoIP (Voice over Internet Protocol), condivisione di applicazioni, trasferimento di file e riunioni. I dati sull'utilizzo possono essere usati per calcolare il ritorno sugli investimenti (ROI) e i dati di diagnostica possono essere usati per risolvere le attività e le riunioni peer-to-peer.

Usare la procedura seguente per abilitare CDR per l'intera organizzazione o per ogni sito dell'organizzazione.

<div>


> [!NOTE]  
> Per abilitare CDR è necessario configurare il monitoraggio e un database di monitoraggio. Per informazioni dettagliate, vedere <A href="lync-server-2013-deploying-monitoring.md">distribuzione del monitoraggio in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a>Per abilitare CDR con il pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) o assegnato al ruolo CsServerAdministrator o CsAdministrator, accedere a qualsiasi computer presente nella rete in cui è stato distribuito Lync Server 2013.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **registrazione dettagli chiamata**.

4.  Nella pagina **registrazione dettagli chiamata** fare clic sul sito appropriato nella tabella, fare clic su **azione**e quindi su **Abilita CDR**.
    
    <div>
    

    > [!NOTE]  
    > CDR è abilitato per impostazione predefinita.

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Attivazione di CDR tramite i cmdlet di Windows PowerShell

È possibile abilitare CDR usando Windows PowerShell e il cmdlet **Set-CsCdrConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-cdr-for-a-single-location"></a>Per abilitare CDR per una singola posizione

  - Per disabilitare CDR, imposta il parametro EnableCDR su true ($True).
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a>Per disabilitare CDR per una singola posizione

  - Per disabilitare CDR, imposta il parametro EnableCDR su false ($False). La disattivazione di CDR non disinstalla il monitoraggio. Sospende la raccolta e lo spazio di archiviazione dei dati CDR.
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>Per usare un singolo comando per abilitare CDR in più posizioni

  - Questo comando consente a CDR di usare tutte le impostazioni di configurazione CDR attualmente in uso nell'organizzazione.
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione del monitoraggio in Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Distribuzione del monitoraggio in Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

