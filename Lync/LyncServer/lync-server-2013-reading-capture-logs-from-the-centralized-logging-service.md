---
title: 'Lync Server 2013: lettura dei registri di acquisizione dal servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5abf7b2f6962dbf38f90f52ff82c54b035d9aa0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-12-28_

Si rende conto del vantaggio reale del servizio di registrazione centralizzato dopo aver eseguito la ricerca e si dispone di un file che è possibile utilizzare per individuare un problema segnalato. È possibile leggere il file in diversi modi. Il file di output è in formato testo standard ed è possibile utilizzare Notepad. exe o qualsiasi altro programma che consenta di aprire e leggere un file di testo. Per i file più grandi e i problemi più complessi, è possibile utilizzare uno strumento come Snooper. exe che è stato creato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato. Snooper è incluso negli strumenti di debug di Lync Server 2013 disponibili come download separato. È possibile scaricare gli strumenti di debug di Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)qui:. Quando si installano gli strumenti di debug di Lync Server 2013, non vengono creati scorciatoie e voci di menu. Dopo aver installato gli strumenti di debug di Lync Server 2013, aprire Esplora risorse, una finestra della riga di comando o Lync Server Management Shell e passare alla directory (percorso predefinito) C\\: Program\\Files Microsoft Lync Server\\2013 Debugging Tools. Fare doppio clic su Snooper. exe o digitare Snooper. exe e quindi premere INVIO se si utilizza la riga di comando o Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Lo scopo di questo argomento non è quello di illustrare le tecniche di risoluzione dei problemi. La risoluzione dei problemi e i processi attorno a esso sono un argomento complesso. Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere Microsoft <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>Lync Server 2010 Resource Kit book at. I processi e le procedure si applicano ancora a Lync Server 2013.



</div>

Lync Server 2013 introduce una versione aggiornata di Snooper che include alcune nuove funzionalità. Nella schermata seguente viene visualizzata la versione di Snooper di Office Communications Server 2007.

![Versione di Snooper di Office Communications 2007.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Versione di Snooper di Office Communications 2007.")

Nella schermata seguente viene illustrata la nuova versione di Snooper inclusa negli strumenti di debug di Lync Server 2013.

![Versione di Snooper di Lync Server 2013.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versione di Snooper di Lync Server 2013.")

Nella schermata seguente viene visualizzata la barra degli strumenti con funzioni di uso frequente.

![Barra degli strumenti Snooper 2013.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra degli strumenti Snooper 2013.")

E, la caratteristica più recente che aggiunge valore è la visualizzazione diagramma flusso (flusso di chiamata). È possibile selezionare un flusso di messaggi nella scheda **messaggio** e fare clic sul pulsante **flusso di chiamata** . Quando si procede attraverso i messaggi, il diagramma del flusso di chiamata viene aggiornato con i nuovi dati.

![Diagramma del flusso di chiamata di Snooper 2013.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagramma del flusso di chiamata di Snooper 2013.")

È possibile posizionare il puntatore del mouse sulla visualizzazione diagramma e ottenere informazioni dettagliate sui messaggi e sul contenuto dei flussi e dei messaggi, nonché sugli elementi del server. Fare clic su qualsiasi freccia del flusso di chiamata per passare al messaggio nella visualizzazione messaggi.

![Dettagli del messaggio del diagramma di flusso delle chiamate.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Dettagli del messaggio del diagramma di flusso delle chiamate.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Per aprire un file di registro in Snooper

1.  Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro. Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.

2.  Dopo l'installazione degli strumenti di debug di Lync Server (LyncDebugTools. msi), passare alla directory del percorso di Snooper. exe utilizzando Esplora risorse o dalla riga di comando. Per impostazione predefinita, gli strumenti di debug sono disponibili in\\C:\\Program Files Microsoft Lync\\Server 2013 Debugging Tools. Fare doppio clic su o eseguire Snooper. exe.

3.  Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di registro, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.

4.  I messaggi di **traccia** dei file di registro vengono visualizzati nella scheda **traccia** . fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Per visualizzare un diagramma del flusso di chiamata

1.  Per utilizzare Snooper e aprire i file di registro, è necessario l'accesso in lettura ai file di registro. Per utilizzare Snooper e accedere ai file di registro, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC), oppure un ruolo RBAC personalizzato che contenga uno dei due gruppi.

2.  Aprire un file di registro e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi oppure selezionare un componente di traccia nella scheda **traccia** .

3.  Fare clic su **flusso di chiamata**.
    
    <div>
    

    > [!NOTE]  
    > Se si fa clic su un messaggio o su una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow". Scegliere un altro messaggio o traccia e il flusso di chiamata verrà visualizzato se il messaggio o la traccia è parte di un flusso di chiamata.

    
    </div>

4.  Spostarsi tra i messaggi o le righe di traccia e osservare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.

5.  Posizionare il puntatore del mouse sugli elementi per ottenere informazioni sui messaggi di chiamata, gli endpoint e altri componenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

