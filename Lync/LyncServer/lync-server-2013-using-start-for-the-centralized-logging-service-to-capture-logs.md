---
title: Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log
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
ms.openlocfilehash: f43a2c86dcbd88f8e9af4ae54f302b4abc943fc0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529973"
---
# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Utilizzo di Start per il servizio di registrazione centralizzato per l'acquisizione dei log in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Per acquisire i log di traccia utilizzando il servizio di registrazione centralizzato, è possibile eseguire un comando per iniziare la registrazione su uno o più computer e pool. È inoltre possibile emettere parametri che definiscono i computer o i pool, quali scenari eseguire (ad esempio, AlwaysOn, un altro scenario predefinito o uno scenario creato), quali componenti di Lync Server (ad esempio, S4, SipStack) devono essere rintracciati.

Per acquisire le informazioni giuste è necessario assicurarsi di usare lo scenario corretto per la raccolta di informazioni pertinenti al problema. Nel servizio di registrazione centralizzato, uno scenario è il concetto di attivazione della registrazione in base a un insieme di componenti server, livelli di registrazione e flag, che è molto più efficiente e utile rispetto alla necessità di definire tali elementi in base ai singoli server. Si definisce e specifica uno scenario da eseguire, e questo viene eseguito in modo coerente in tutti i server e i pool nell'ambito dell'infrastruttura.

Lo scenario predefinito è denominato **AlwaysOn**. Lo scopo di AlwaysOn, come indicato dal nome, è l'esecuzione costante dello scenario. Lo scenario AlwaysOn raccoglie informazioni a livello Info su molti dei più comuni componenti server. Tenere presente che questo livello di registrazione include, in aggiunta ai messaggi di informazioni, i messaggi di tipo Fatal, Error e Warning, ovvero relativi ad avvisi, errori ed errori irreversibili. AlwaysOn raccoglie informazioni prima, durante e dopo il verificarsi di un problema. Questo comportamento è radicalmente diverso rispetto a quello degli strumenti di registrazione precedenti, ad esempio OCSLogger. L'esecuzione di OCSLogger avveniva quando il problema si era già verificato, rendendone più difficoltosa la risoluzione poiché i dati raccolti erano di tipo reattivo e non proattivo. Se AlwaysOn non contiene le informazioni cercate per individuare il componente che causa il problema e indicare le azioni per la risoluzione (evento improbabile, data l'estensione e il livello di dettaglio dei provider in AlwaysOn), indicherà un livello di informazioni ragionevole per determinare le altre operazioni da eseguire, ad esempio creare un nuovo scenario, raccogliere altre informazioni, eseguire una ricerca diversa per raccogliere dettagli più specifici e così via.

Il servizio di registrazione centralizzato offre due modalità di esecuzione dei comandi. Un certo numero di argomenti sono stati concentrati sull'utilizzo di Windows PowerShell tramite Lync Server Management Shell. La possibilità di utilizzare una serie di configurazioni e comandi complessi favorisce Windows PowerShell per l'utilizzo del servizio di registrazione centralizzato. Poiché Windows PowerShell tramite Lync Server Management Shell è quasi onnipresente per tutte le funzioni di Lync Server, vengono descritti solo i comandi di Windows PowerShell.

<div>


> [!NOTE]
> Se si decide di utilizzare il set di comandi limitato disponibile dalla riga di comando, è possibile ottenere assistenza con CLSController.exe digitando <CODE>ClsController.exe</CODE> . Per impostazione predefinita, <STRONG>ClsController.exe</STRONG> viene installato nella directory C:\Programmi\Microsoft Lync Server 2013 \ ClsAgent.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell mediante comandi di base

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Avviare uno scenario di registrazione con il servizio di registrazione centralizzato digitando quanto segue:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Ad esempio, per avviare lo scenario **AlwaysOn** digitare:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > Lo scenario AlwaysOn non ha una durata predefinita. Verrà eseguito finché non lo si interrompe esplicitamente con il cmdlet <STRONG>Stop-CsClsLogging</STRONG>. Per informazioni dettagliate, vedere <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Per tutti gli altri scenari, la durata predefinita è 4 ore.

    
    </div>

3.  Premere INVIO per eseguire il comando.
    
    <div>
    

    > [!NOTE]
    > Per l'esecuzione dei comandi e la comunicazione dello stato dai computer della distribuzione possono essere necessari da 30 a 60 secondi.

    
    </div>
    
    ![Esecuzione di Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")

4.  Per avviare un altro scenario, usare il cmdlet **Start-CsClsLogging** con il nome dello scenario aggiuntivo da eseguire (ad esempio lo scenario **Authentication**) come segue:
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > È possibile eseguire un totale di due scenari su qualsiasi computer in qualsiasi momento. Se l'ambito del comando è globale, lo o gli scenari verranno eseguiti da tutti i computer della distribuzione. Per avviare un terzo scenario è necessario interrompere la registrazione nel computer, pool, sito o ambito globale in cui si vuole eseguire il nuovo scenario. Se è stato avviato un ambito globale, è possibile interrompere la registrazione per uno o per entrambi gli scenari in uno o più computer e pool. Per informazioni dettagliate sulla gestione degli scenari in esecuzione, vedere <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using stop for the accentrated Logging Service in Lync Server 2013</A> e <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Per eseguire Start-CsClsLogging con Windows PowerShell tramite comandi avanzati

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Sono disponibili ulteriori parametri per la gestione dei comandi di registrazione. –Duration consente di regolare la durata di esecuzione dello scenario. È anche possibile definire –Computers, un elenco di nomi di dominio completi (FQDN) di computer separati da una virgola, oppure –Pools, un elenco di FQDN separati da una virgola dei pool nei quali si vuole eseguire la registrazione.
    
    È possibile avviare una sessione di registrazione per lo scenario di *UserReplicator* nel pool "pool01.contoso.NET". La durata della sessione di registrazione deve essere di 8 ore. A questo scopo, digitare:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    L'esecuzione corretta dello scenario restituisce un risultato simile al seguente:
    
    ![Esecuzione di Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Esecuzione di Start-CsClsLogging.")
    
    Si noti che in questo esempio gli scenari AlwaysOn e UserReplicator sono entrambi in esecuzione.

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

