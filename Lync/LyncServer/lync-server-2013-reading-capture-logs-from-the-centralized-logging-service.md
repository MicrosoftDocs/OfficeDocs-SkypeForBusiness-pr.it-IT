---
title: 'Lync Server 2013: leggere i registri di acquisizione dal servizio di registrazione centralizzato'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a>Lettura dei registri di acquisizione dal servizio di registrazione centralizzato in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-12-28_

Dopo aver eseguito la ricerca, è possibile realizzare il vero vantaggio del servizio di registrazione centralizzato e si ha un file che può essere usato per rintracciare un problema segnalato. È possibile leggere il file in diversi modi. Il file di output è in formato testo standard ed è possibile usare Notepad. exe o qualsiasi altra applicazione che consentirà di aprire e leggere un file di testo. Per i file più grandi e i problemi più complessi, puoi usare uno strumento come Snooper. exe progettato per leggere e analizzare l'output di registrazione dal servizio di registrazione centralizzato. Snooper è incluso negli strumenti di debug di Lync Server 2013 disponibili come download separato. È possibile scaricare gli strumenti di debug di Lync Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)qui:. Quando si installano gli strumenti di debug di Lync Server 2013, non vengono creati scorciatoie e voci di menu. Dopo aver installato gli strumenti di debug di Lync Server 2013, aprire Esplora risorse, una finestra della riga di comando o Lync Server Management Shell e accedere alla directory (posizione predefinita) C\\: programmi\\Microsoft Lync Server 2013\\strumenti di debug. Fare doppio clic su Snooper. exe o digitare Snooper. exe, quindi premere INVIO se si usa la riga di comando o Lync Server Management Shell.

<div>


> [!IMPORTANT]  
> Lo scopo di questo argomento non è dettagliare e discutere le tecniche di risoluzione dei problemi. La risoluzione dei problemi e i processi che la circondano sono un argomento complesso. Per informazioni dettagliate sulla risoluzione dei problemi di base e sulla risoluzione dei problemi relativi ai carichi di lavoro specifici, vedere il <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>manuale del Resource Kit di Microsoft Lync Server 2010. I processi e le procedure si applicano ancora a Lync Server 2013.



</div>

Lync Server 2013 introduce una versione aggiornata di Snooper che include alcune nuove caratteristiche. Lo screenshot seguente mostra la versione di Snooper da Office Communications Server 2007.

![Office Communications 2007 versione di Snooper.] (images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 versione di Snooper.")

Lo screenshot seguente mostra la nuova versione di Snooper inclusa negli strumenti di debug di Lync Server 2013.

![Versione di Snooper di Lync Server 2013.] (images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Versione di Snooper di Lync Server 2013.")

La schermata seguente mostra la barra degli strumenti con le funzioni usate di frequente.

![Barra degli strumenti di snooper 2013.] (images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Barra degli strumenti di snooper 2013.")

La caratteristica più recente che aggiunge valore è la visualizzazione diagramma flusso (flusso delle chiamate). Si seleziona un flusso di messaggi nella scheda **messaggio** e si fa clic sul pulsante **flusso di chiamata** . Quando si procede attraverso i messaggi, il diagramma di flusso delle chiamate viene aggiornato con i nuovi dati.

![Diagramma di flusso delle chiamate di snooper 2013.] (images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Diagramma di flusso delle chiamate di snooper 2013.")

È possibile posizionare il puntatore del mouse sulla visualizzazione diagramma e ottenere informazioni dettagliate sui messaggi e il contenuto dei flussi e dei messaggi, nonché sugli elementi del server. Fare clic su una freccia del flusso di chiamata per passare al messaggio nella visualizzazione messaggi.

![Dettagli del messaggio del diagramma di flusso delle chiamate.] (images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Dettagli del messaggio del diagramma di flusso delle chiamate.")

<div>

## <a name="to-open-a-log-file-in-snooper"></a>Per aprire un file di log in Snooper

1.  Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log. Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.

2.  Dopo l'installazione degli strumenti di debug di Lync Server (LyncDebugTools. msi), cambiare directory nella posizione di Snooper. exe usando Esplora risorse o dalla riga di comando. Per impostazione predefinita, gli strumenti di debug si trovano in\\C:\\Program Files Microsoft Lync\\Server 2013 strumenti di debug. Fare doppio clic su o eseguire Snooper. exe.

3.  Dopo aver aperto Snooper, fare clic con il pulsante destro del mouse su **file**, scegliere **OpenFile**, individuare i file di log, selezionare un file nella finestra di dialogo **Apri** e quindi fare clic su **Apri**.

4.  I messaggi di **traccia** del file di log vengono visualizzati nella scheda **traccia** . fare clic sulla scheda **messaggi** per visualizzare il contenuto del messaggio delle tracce raccolte.

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a>Per visualizzare un diagramma di flusso delle chiamate

1.  Per usare Snooper e aprire i file di log, è necessario l'accesso in lettura ai file di log. Per usare Snooper e accedere ai file di log, è necessario essere membri dei gruppi di sicurezza CsAdministrator o CsServerAdministrator (RBAC) o di un ruolo RBAC personalizzato che contenga uno di questi due gruppi.

2.  Aprire un file di log e fare clic sulla scheda **messaggi** , selezionare una conversazione nella visualizzazione messaggi o selezionare un componente di traccia nella scheda **traccia** .

3.  Fare clic su **flusso di chiamata**.
    
    <div>
    

    > [!NOTE]  
    > Se si fa clic su un messaggio o una traccia che non fa parte di un flusso di chiamata, il diagramma non verrà visualizzato e viene visualizzato un messaggio di stato nella parte inferiore di Snooper che indica che "questo messaggio non è idoneo per callfow". Scegliere un altro messaggio o traccia e il flusso di chiamata viene visualizzato se il messaggio o la traccia fa parte di un flusso di chiamata.

    
    </div>

4.  Spostarsi tra i messaggi o le linee di traccia e notare se il diagramma di flusso delle chiamate viene aggiornato o modificato per visualizzare un nuovo diagramma.

5.  Posizionare il puntatore del mouse sugli elementi per ottenere informazioni su messaggi di chiamata, endpoint e altri componenti.

</div>

</div>

<span> </span>

</div>

</div>

</div>

