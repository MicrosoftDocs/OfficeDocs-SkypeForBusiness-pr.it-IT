---
title: Uso di Start per il servizio di registrazione centralizzato per acquisire i registri
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75090036b7120c8af7cda132c26d5b4fb02d3dab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Uso di Start per il servizio di registrazione centralizzato per acquisire i registri in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Per acquisire i registri di traccia usando il servizio di registrazione centralizzato, viene emesso un comando per iniziare la registrazione in uno o più computer e pool. È inoltre possibile emettere parametri che definiscono i computer o i pool, quali scenari eseguire, ad esempio AlwaysOn, un altro scenario predefinito o uno scenario creato, quali componenti di Lync Server (ad esempio, S4, SipStack) devono essere rintracciati.

Per acquisire le informazioni appropriate, è necessario assicurarsi di usare lo scenario giusto per raccogliere informazioni rilevanti per il problema. Nel servizio di registrazione centralizzato, uno scenario è il concetto di attivazione della registrazione basato su una raccolta di componenti server, livelli di registrazione e contrassegni, che è molto più efficiente e utile che definire questi elementi in base al server. Puoi definire e specificare uno scenario da eseguire e lo scenario viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.

Lo scenario predefinito è denominato **AlwaysOn**. Lo scopo previsto per AlwaysOn è l'esecuzione costante dello scenario, come implica il nome dello scenario. Lo scenario AlwaysOn raccoglie informazioni a livello di informazioni (si noti che il livello di registrazione info include fatale, Error e Warning oltre ai messaggi info) per molti dei componenti server più comuni. AlwaysOn raccoglie le informazioni prima, durante e dopo che si verifica un problema. Ciò si differenzia in modo significativo dal comportamento tipico degli strumenti di registrazione precedenti, ad esempio OCSLogger. Hai eseguito OCSLogger dopo che il problema era già avvenuto, rendendo più difficile la risoluzione dei problemi perché i dati che hai sono reattivi e non proattivi. Se AlwaysOn non contiene le informazioni che si stanno cercando per fare riferimento al componente problema e indicare una linea di azione per risolverlo (che non è probabilmente dato l'ampiezza e la profondità dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole conferma per determinare altre informazioni utili, ad esempio la creazione di un nuovo scenario, la raccolta di altri dati, l'esecuzione di una ricerca diversa per raccogliere dettagli più mirati e così via.

Il servizio di registrazione centralizzato offre due modi per emettere comandi. Un certo numero di argomenti sono stati concentrati sull'uso di Windows PowerShell tramite Lync Server Management Shell. La possibilità di usare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'uso del servizio di registrazione centralizzato. Dato che Windows PowerShell tramite Lync Server Management Shell è quasi onnipresente per tutte le funzioni di Lync Server, vengono discussi solo i comandi di Windows PowerShell.

<div>


> [!NOTE]
> Se si decide di usare il set di comandi limitato disponibile dalla riga di comando, è possibile ottenere assistenza con CLSController. exe digitando <CODE>ClsController.exe</CODE>. Per impostazione predefinita, <STRONG>ClsController. exe</STRONG> viene installato nella directory C:\Programmi\Microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell usando i comandi di base

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Ad esempio, per avviare lo scenario **AlwaysOn** , digitare:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Lo scenario AlwaysOn non ha durata predefinita. Questo scenario verrà eseguito fino a quando non lo Interrompi esplicitamente con il cmdlet <STRONG>Stop-CsClsLogging</STRONG> . Per informazioni dettagliate, vedere <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Per tutti gli altri scenari, la durata predefinita è di 4 ore.

    
    </div>

3.  Premere INVIO per eseguire il comando.
    
    <div>
    

    > [!NOTE]
    > Potrebbe essere necessario un breve lasso di tempo (da 30 a 60 secondi) per i comandi da eseguire e per ricevere lo stato di nuovo dai computer della distribuzione.

    
    </div>
    
    ![Esecuzione di Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")

4.  Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire come indicato di seguito, ad esempio l' **autenticazione**dello scenario:
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > È possibile avere un totale di due scenari in esecuzione in qualsiasi computer specifico in qualsiasi momento. Se il comando è globale nell'ambito, tutti i computer della distribuzione eseguiranno lo scenario o gli scenari. Per avviare un terzo scenario, è necessario interrompere la registrazione nel computer, nel pool, nel sito o nell'ambito globale in cui si vuole eseguire il nuovo scenario. Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o entrambi gli scenari in uno o più computer e pool. Per informazioni dettagliate sulla gestione degli scenari in uso, vedere <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilizzo di stop per il servizio di registrazione centralizzato in Lync Server 2013</A> e <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell tramite comandi avanzati

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Sono disponibili parametri aggiuntivi per gestire i comandi di registrazione. È possibile usare la durata per regolare il periodo di tempo per l'esecuzione dello scenario. È anche possibile definire-computer, un elenco di nomi di dominio completi di computer (FQDN) separati da una virgola o da-pools, un elenco delimitato da virgole di FQDN per i pool di cui si vuole eseguire l'accesso.
    
    Si avvia una sessione di registrazione per lo scenario *UserReplicator* nel pool "pool01.contoso.NET". Puoi anche definire la durata della sessione di registrazione a 8 ore. A tale scopo, digitare:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    L'esecuzione corretta di questo scenario restituisce un risultato simile al seguente:
    
    ![Esecuzione di Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")
    
    Tieni presente che in questo esempio viene eseguito lo scenario AlwaysOn e lo scenario UserReplicator è in corso.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del servizio di registrazione centralizzato in Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

