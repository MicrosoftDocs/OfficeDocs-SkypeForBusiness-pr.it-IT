---
title: Documentazione sugli strumenti di Lync Server 2013 Resource Kit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Resource Kit Tools Documentation
ms:assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945604(v=OCS.15)
ms:contentKeyID: 51541429
ms.date: 02/02/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 046e29fcec697a1ac073833e6b73c7bfe15fb8ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-resource-kit-tools-documentation"></a>Documentazione sugli strumenti di Lync Server 2013 Resource Kit

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-01-09_

In questo argomento vengono descritti gli strumenti che fanno parte del Resource Kit di Lync Server 2013, tra cui lo scopo di ogni strumento e gli esempi di utilizzo. Gli strumenti di Lync Server 2013, Resource Kit consentono di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Lync Server 2013. Ad esempio, è possibile utilizzare lo strumento di **dati di Web conf** per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento **SEFAUtil** può essere utilizzato per configurare l'inoltro delle chiamate Delegate e la risposta per gli utenti. Si consiglia agli amministratori IT di utilizzare questi strumenti per gestire in modo più efficace Lync Server 2013.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installazione degli strumenti del Resource Kit

Per installare Lync Server 2013, strumenti del Resource Kit, scaricare **OCSReskit. msi**. È possibile scaricare il programma di installazione degli strumenti del Resource Kit dall' [https://go.microsoft.com/fwlink/p/?LinkID=330429](https://go.microsoft.com/fwlink/p/?linkid=330429)area download all'indirizzo.

Eseguire **OCSResKit. msi** per eseguire un'installazione semplice. Il file con estensione msi installa tutti gli strumenti nel percorso seguente: **% Program Files\\% Microsoft Lync Server\\2013 reskit**. Gli strumenti che sono eseguibili indipendenti sono presenti in questa cartella. Gli strumenti che dispongono anche di file si trovano nelle rispettive sottocartelle.

</div>

<div>

## <a name="supported-environments"></a>Ambienti supportati

Per ottenere prestazioni ottimali, è consigliabile installare gli strumenti di Lync Server 2013, Resource Kit nello stesso ambiente e con le stesse specifiche richieste per Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Panoramica degli strumenti del Resource Kit

Nell'elenco seguente vengono descritti gli strumenti forniti in Lync Server 2013 Resource Kit. Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nella sezione seguente.

  - ABSConfig

  - Monitoraggio del servizio criteri di larghezza di banda

  - Analizzatore dell'utilizzo della larghezza di banda

  - Chiamata Parkometer

  - CleanupStorageServiceData

  - DBAnalyze

  - ImportStorageServiceData

  - LCSSync

  - LookupUserConsole

  - MsTurnPing

  - Visualizzatore di configurazione di rete

  - Agente di Response Group Live

  - SEFAUtil

  - SYSPrep. ps1

  - Migrazione degli annunci di numeri non assegnati

  - Dati Web conf

</div>

<div>

## <a name="absconfig"></a>ABSConfig

Lo strumento di configurazione del servizio di gestione della Rubrica (ABSConfig) è uno strumento di amministrazione che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Lync Server 2013. Questo strumento consente inoltre agli amministratori di Lync Server 2013 di ripristinare le impostazioni predefinite del servizio Rubrica.

<div>

## <a name="description"></a>Descrizione

ABSConfig è un'applicazione per l'interfaccia utente grafica che consente agli amministratori di configurare gli attributi di servizi di dominio Active Directory correlati al servizio Rubrica.

Gli scenari principali per lo strumento sono gli elementi seguenti:

  - Per consentire agli amministratori di eseguire il mapping degli attributi in servizi di dominio Active Directory agli attributi di Lync Server 2013.

  - Per consentire agli amministratori di specificare l'attributo servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.

  - Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.

È possibile avviare lo strumento ABSConfig utilizzando il file absConfig. exe. Lo strumento verrà aperto alla scheda **Configure Attributes** . In questa tabella sono disponibili opzioni per il mapping degli attributi dei servizi di dominio Active Directory ai campi degli attributi per Lync Server 2013 e per specificare quali utenti includere o escludere nei file del servizio Rubrica basati su filtri di attributi specifici. Sono inoltre disponibili opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica. L'opzione **Ripristina valori predefiniti** consente agli amministratori di ripristinare le impostazioni del servizio Rubrica in valore predefinito.

</div>

<div>

## <a name="changes-from-lync-server-2010"></a>Modifiche apportate da Lync Server 2010

Nello strumento di configurazione di Lync Server 2013 ABS, gli attributi (righe) possono essere rimossi deselezionando la casella di controllo "attiva" per l'attributo. Questo ha lo stesso effetto dell'eliminazione della riga in Lync Server 2010.

<div>


> [!NOTE]  
> La casella di controllo Abilita si trova nella colonna estrema destra. potrebbe essere necessario scorrere verso destra per visualizzare la colonna



</div>

</div>

<div>

## <a name="output"></a>Output

ABSConfig archivia la configurazione del servizio Rubrica nel database.

    Path: %ProgramFiles%\Microsoft Lync Server 2013\Reskit

</div>

<div>

## <a name="purpose"></a>Scopo

ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Lync Server 2013.

</div>

<div>

## <a name="requirements"></a>Requisiti

<div>

## <a name="computer"></a>Computer

ABSConfig può essere eseguito solo da un computer aggiunto al dominio in cui è installato Lync Server 2013. Nel caso di Lync Server 2013, Enterprise Edition, questo strumento può essere eseguito in tutti i front end server in cui il servizio Rubrica è abilitato durante l'installazione.

</div>

<div>

## <a name="network"></a>Rete

Il computer deve essere in grado di connettersi al pool Front end e al database back-end.

</div>

<div>

## <a name="software"></a>Software

Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:

  - Microsoft Lync Server 2013

</div>

<div>

## <a name="users"></a>Utenti

Amministratori che dispongono delle autorizzazioni necessarie per aggiornare la distribuzione di Lync Server 2013.

</div>

</div>

<div>

## <a name="examples"></a>Esempi

ABSConfig può essere avviato digitando **ABSConfig. exe** al prompt dei comandi. Di seguito è riportata l'interfaccia utente dello strumento ABSConfig.

![Lo strumento ABSConfig. exe.](images/JJ945604.6fb63a70-7b63-4b8b-b7d1-82fe9aa2028f(OCS.15).jpg "Lo strumento ABSConfig. exe.")

</div>

<div>

## <a name="summary"></a>Riepilogo

Lo strumento ABSConfig offre agli amministratori uno strumento rapido e semplice da utilizzare per personalizzare il servizio Rubrica di Lync Server 2013.

</div>

</div>

<div>

## <a name="bandwidth-policy-service-monitor"></a>Monitoraggio del servizio criteri di larghezza di banda

Lo strumento di monitoraggio dei criteri di larghezza di banda è progettato per consentire agli amministratori di visualizzare un elenco di quanto segue:

1.  Tutti i servizi di criteri di larghezza di banda di Lync Server 2013 configurati (autenticazione e Core) nella topologia

2.  Le connessioni che ogni servizio apporta ad altri servizi di criteri di larghezza di banda e ai server perimetrali

3.  Tutti i collegamenti configurati nel documento di configurazione di rete e nell'utilizzo della larghezza di banda in tempo reale riportati da ciascuno dei servizi di criteri di larghezza di banda

<div>

## <a name="description"></a>Descrizione

Lo strumento di monitoraggio dei criteri di larghezza di banda è implementato come applicazione basata su GUI. Gli amministratori avviano lo strumento mediante l'esecuzione di PDPMonUI. exe.

Quando lo strumento viene avviato, cerca di individuare l'elenco dei servizi per i criteri di larghezza di banda nella topologia. Dopo aver eseguito l'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati per i cluster a cui appartengono.

Quando gli amministratori selezionano un particolare servizio per i criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni relative a quel particolare servizio. Nel riquadro sono inoltre disponibili due schede principali che consentono di visualizzare le informazioni.

<div>

## <a name="machine-info-tab"></a>Scheda informazioni sul computer

Nella scheda **informazioni sul computer** vengono visualizzati i dettagli del servizio dei criteri di larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.

</div>

<div>

## <a name="topology-info-tab"></a>Scheda informazioni sulla topologia

Nella scheda **informazioni sulla topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione di rete. Per ogni collegamento viene visualizzata la capacità di larghezza di banda audio e video. Inoltre, viene visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità. Lo strumento utilizza la codifica a colori per evidenziare i collegamenti che dispongono di un utilizzo vicino alla capacità, consentendo agli amministratori di isolare rapidamente tali collegamenti.

<div>


> [!NOTE]  
> Se lo strumento Monitoraggio servizi di larghezza di banda verifica un errore durante la connessione a uno dei servizi di criteri di larghezza di banda configurati, le informazioni contenute nelle schede informazioni <STRONG>computer</STRONG> e <STRONG>topologia</STRONG> non verranno popolate. Tuttavia, è possibile che lo strumento possa connettersi inizialmente, ma in seguito perde la connessione al servizio. In questi casi, gli amministratori possono visualizzare le informazioni obsolete. È presente un timestamp dell' <STRONG>Ultimo aggiornamento</STRONG> su ognuna delle schede che consentono agli amministratori di visualizzare l'ultimo aggiornamento dei dati per un particolare servizio criteri di larghezza di banda.



</div>

</div>

</div>

<div>

## <a name="output"></a>Output

Non è disponibile alcun output della riga di comando. l'output del programma è contenuto all'interno dell'interfaccia utente grafica principale (GUI).

</div>

<div>

## <a name="purpose"></a>Scopo

Lo strumento di monitoraggio dei criteri di larghezza di banda consente agli amministratori di visualizzare lo stato di ogni servizio dei criteri di larghezza di banda definito nella topologia. Gli amministratori possono inoltre visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento di configurazione della rete.

</div>

<div>

## <a name="requirements"></a>Requisiti

È necessario eseguire lo strumento di monitoraggio dei criteri di larghezza di banda su un computer che fa parte della topologia di Lync Server.

</div>

<div>

## <a name="summary"></a>Riepilogo

Lo strumento di monitoraggio dei criteri di larghezza di banda può essere una risorsa importante per gli amministratori in modo che possano ispezionare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, soprattutto, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti che sono definito nelle impostazioni di configurazione di rete.

</div>

</div>

<div>

## <a name="bandwidth-utilization-analyzer"></a>Analizzatore dell'utilizzo della larghezza di banda

L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che consente di creare report su diverse visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC tra i collegamenti WAN nella rete aziendale. Questi report possono essere utilizzati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità della larghezza di banda.

<div>

## <a name="description"></a>Descrizione

L'analizzatore dell'utilizzo della larghezza di banda viene implementato come applicazione basata su GUI. Questo strumento genera report in modo specifico per l'utilizzo dell'audio in rete e contribuisce alla pianificazione della capacità. Inoltre, viene eseguita una iterazione sulla capacità di larghezza di banda assegnata a vari collegamenti.

</div>

<div>

## <a name="output"></a>Output

L'analizzatore dell'utilizzo della larghezza di banda fornisce grafici al grafico della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.

</div>

<div>

## <a name="purpose"></a>Scopo

In qualsiasi distribuzione di voce e video, è importante monitorare e comprendere l'andamento dell'utilizzo della larghezza di banda del traffico multimediale in tutta la rete aziendale. Lo strumento Analizzatore utilizzo larghezza di banda consente a un amministratore di raggiungere questo obiettivo. Questo strumento esegue le operazioni seguenti:

  - Genera relazioni specifiche per l'utilizzo dell'audio in rete

  - Consente di eseguire una pianificazione e un'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a vari collegamenti

L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche dei rapporti di utilizzo e capacità della larghezza di banda. sono i seguenti:

  - Tutti i collegamenti WAN nella rete aziendale

  - Filtrato da collegamenti WAN selezionati che sono stati scelti

  - Filtrato tramite collegamenti WAN che hanno superato la capacità dei collegamenti

  - Filtrato mediante collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning

  - Filtrare mediante collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda superiore al 90% della capacità di larghezza di banda del collegamento WAN)

  - Filtro in base al tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito

  - Filtrato in base all'area di rete

<div>

## <a name="applications"></a>Applicazioni

Analizzatore dell'utilizzo della larghezza di banda contiene le due applicazioni seguenti (strumenti):

  - **WanLinkLogCollector. exe**   questo strumento consente all'utente di immettere le informazioni necessarie.

  - **BandwidthUtilizationAnalyzer. xlsm**  un rapporto software del foglio di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector. exe. Questa applicazione consente all'utente di applicare filtri al rapporto come mostrato più avanti in questo articolo.

</div>

<div>

## <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fasi dell'utilizzo dell'analizzatore dell'utilizzo della larghezza di banda

Quando si utilizza l'analizzatore dell'utilizzo della larghezza di banda sono presenti due fasi:

  - Raccogliere i registri, che vengono eseguiti utilizzando WanLinkLogCollector. exe

  - Personalizzare i report, che vengono eseguiti mediante BandwidthUtilizationAnalyzer. xlsm

<div>


> [!IMPORTANT]  
> È consigliabile che BandwidthUtilizationAnalyzer. xlsm non venga avviato manualmente dagli utenti finali.



</div>

</div>

<div>

## <a name="starting-bandwidth-utilization-analyzer"></a>Avvio dell'analizzatore dell'utilizzo della larghezza di banda

Avviare WanLinkLogCollector. exe dal prompt dei comandi o tramite Esplora risorse.

**Utilizzo di WanLinkLogCollector. exe**

Sono disponibili tre passaggi per l'utilizzo di WanLinkLogCollector. exe:

1.  **Log la sequenza temporale**   fornisce la sequenza temporale per la quale è necessario generare il report

2.  **Specificare le directory**   di file che forniscono informazioni sulla posizione dei file

3.  **Raccolta dei registri e avvio del Visualizzatore**  di report eseguire il comando per generare il report

<div>

## <a name="step-1---log-the-timeline"></a>Passaggio 1-registrare la sequenza temporale

La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue come illustrato nella figura seguente.

1.  **Data di inizio** Questa è la data di inizio della sequenza temporale per la quale deve essere generato il report. ad esempio, 2010 agosto 1.

2.  **Data di fine** Questa è la data di fine della sequenza temporale per la quale deve essere generato il report. ad esempio, settembre 30, 2010.
    
    ![Date di inizio e di fine nell'utilizzo della larghezza di banda A](images/JJ945604.2c597cfc-3372-4d41-816b-26202f607ad8(OCS.15).jpg "Date di inizio e di fine nell'utilizzo della larghezza di banda A")  

</div>

<div>

## <a name="step-2---specify-the-file-directories"></a>Passaggio 2: specificare le directory dei file

Le directory dei file seguenti possono essere specificate dall'utente come illustrato.

  - **Percorso dei file di registro del server** Percorso della cartella in cui sono archiviati i registri del server dei criteri di larghezza di banda. Si tratta in \<genere di\>\\\<una scelta Fileserver\>\\di\\Fe AppServerFiles PDP.

  - **Percorso di archiviazione file temporaneo** Percorso temporaneo del file in cui vengono archiviati i file intermedi durante la generazione del report.

![Directory dei file nell'utilizzo della larghezza di banda anale](images/JJ945604.d66daeac-1669-45e3-932d-3f6782840c2a(OCS.15).jpg "Directory dei file nell'utilizzo della larghezza di banda anale")

<div>


> [!NOTE]  
> Verificare che all'utente dello strumento sia disponibile un numero sufficiente di accessi ai registri del server e alla cartella temporanea dell'archivio file.



</div>

</div>

<div>

## <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Passaggio 3: raccolta dei registri e avvio del Visualizzatore di report

Per raccogliere i registri e avviare il Visualizzatore di report, fare clic su **Esegui** come illustrato di seguito. Questo passaggio consente di raccogliere i dati necessari.

![Raccolta di dati nell'utilizzo della larghezza di banda anale](images/JJ945604.0019cb2c-7c01-4dc9-ac90-ac47c47d1bfd(OCS.15).jpg "Raccolta di dati nell'utilizzo della larghezza di banda anale")

Quando la convalida dell'input ha esito positivo, viene visualizzato il messaggio mostrato di seguito.

![Registri di notifica raccolti nella larghezza di banda utili](images/JJ945604.eda91da8-3285-4eab-8ccb-c6d89c8cc221(OCS.15).jpg "Registri di notifica raccolti nella larghezza di banda utili")

Fare clic su **OK**. BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente. Seguire le istruzioni riportate nella finestra di messaggio. Per informazioni dettagliate, vedere **using BandwidthUtilizationAnalyzer. xlsm** nella sezione successiva.

</div>

<div>


**Utilizzo di BandwidthUtilizationAnalyzer. xlsm**

1.  Quando BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente, fare clic su **Aggiorna** come illustrato di seguito.
    
    ![BandwidthUtilizationAnalyzer. xlsm](images/JJ945604.c4e675b9-1671-400e-a712-6db82d731b39(OCS.15).jpg "BandwidthUtilizationAnalyzer. xlsm")

2.  Quando si apre una cartella di file, selezionare Consolidated. csv dal percorso specificato nella finestra di messaggio come illustrato di seguito. Viene inoltre visualizzato il percorso come **C:\\Temp**.
    
    ![Apertura di una cartella in BandwidthUtilizationAnalyzer.](images/JJ945604.601cc572-cee9-45fb-9ed1-c4b96a2fa21e(OCS.15).jpg "Apertura di una cartella in BandwidthUtilizationAnalyzer.")

3.  Fare clic su **Importa**.

4.  La trama grafica viene generata automaticamente. È disponibile quando il puntatore di lavoro in background scompare.
    
    ![Applicazione di filtri nella visualizzazione report.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applicazione di filtri nella visualizzazione report.")

</div>

<div>

## <a name="applying-filters-to-the-report-view"></a>Applicazione di filtri alla visualizzazione del report

I filtri che è possibile applicare alla visualizzazione del rapporto come illustrato di seguito sono descritti nel modo seguente:

![Applicazione di filtri nella visualizzazione report.](images/JJ945604.1416468e-e3ab-478e-b569-e42ba9c27a17(OCS.15).jpg "Applicazione di filtri nella visualizzazione report.")

1.  **Nome** Filtrare in base ai collegamenti WAN (il filtro è a destra del grafico). Il prefisso indica i tipi di collegamento seguenti. vedere la casella verticale (blu):
    
      - **Sito S** Collegamento WAN da un sito di rete a un'area di rete
    
      - **È tra siti** Collegamento WAN tra due siti di rete
    
      - **Inter-Region R** Collegamento WAN tra due aree di rete

2.  **Limite superato** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda è superiore alla capacità della larghezza di banda

3.  **Livelli critici** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto il 90% o superiore alla capacità della larghezza di banda

4.  **Sottoutilizzati** Filtra mediante collegamenti WAN il cui utilizzo della larghezza di banda è stato inferiore al 25% della capacità della larghezza di banda

5.  **Tipo di collegamento** Filtrare in base ai seguenti tipi di collegamenti WAN:
    
      - Tipo di **sito di rete**
    
      - Tipo **tra siti**
    
      - Tipo **di collegamento tra aree** geografiche

6.  **Area geografica** Filtrare in base all'area di rete

Nelle figure seguenti vengono illustrati i filtri descritti in precedenza.

Filtrare in base al **nome**. Selezionare l'elenco dei collegamenti che devono essere visualizzati nel grafico.

![Filtro in base al nome in BandwidthUtilizationAnalyzer.](images/JJ945604.002b7c8e-f0da-48ce-9e1a-5c34d2cab063(OCS.15).jpg "Filtro in base al nome in BandwidthUtilizationAnalyzer.")

Filtrare in base al **limite superato**. Selezionare **true** per applicare il filtro.

![Filtro in base al limite superato.](images/JJ945604.5946c95e-76ce-46ca-8f3e-a79be1e5c527(OCS.15).jpg "Filtro in base al limite superato.")

Filtrare in base ai **livelli critici**. Selezionare **true** per applicare il filtro.

![Filtro in base a livelli critici.](images/JJ945604.60771a52-d8ba-4cb9-a02d-d6c888cb5505(OCS.15).jpg "Filtro in base a livelli critici.")

Filtro in **base a utilizzato**. Selezionare **true** per applicare il filtro.

![Filtro in base a utilizzato.](images/JJ945604.95a2bf01-5aba-4927-af47-1ad3c459d791(OCS.15).jpg "Filtro in base a utilizzato.")

Filtro in base al **tipo di collegamento**. Selezionare il tipo o i tipi che devono essere visualizzati.

![Filtro in base al tipo di collegamento.](images/JJ945604.08757949-06bd-4cf3-809f-d81fd23a6639(OCS.15).jpg "Filtro in base al tipo di collegamento.")

Filtrare in base all' **area geografica**. Selezionare un elenco di aree di cui devono essere visualizzati i collegamenti.

![Filtro in base all'area geografica.](images/JJ945604.5de4cec4-6c09-48bb-98c7-b56f7bdb3d5a(OCS.15).jpg "Filtro in base all'area geografica.")

</div>

</div>

</div>

<div>

## <a name="requirements"></a>Requisiti

  - .NET Framework 3,5

  - Microsoft Excel 2010 o Excel 2007

</div>

<div>

## <a name="summary"></a>Riepilogo

L'analizzatore dell'utilizzo della larghezza di banda viene utilizzato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC sulla rete. Questo strumento può essere utilizzato per segnalare l'utilizzo della larghezza di banda video anche sulla rete.

</div>

</div>

<div>

## <a name="call-parkometer"></a>Chiamata Parkometer

Call Parkometer è un'applicazione della riga di comando che consente di accedere facilmente al database di orbit del parcheggio di chiamata.

<div>

## <a name="description"></a>Descrizione

Call Parkometer è uno strumento che consente di monitorare le chiamate attualmente parcheggiate. Raccoglie anche le statistiche sulle orbite e sull'utilizzo del server parcheggio di chiamata (CPS). Questo strumento da riga di comando fornisce sia la lettura che l'accesso in scrittura al database di SQL Server Orbit di CPS da un computer locale o connesso in remoto.

Tutte le opzioni sono mutualmente esclusive. La sintassi della riga di comando è la seguente:

  - **– o** parameter: elenca tutti gli intervalli di Orbit configurati per il pool.

  - **– n** parameter: elenca tutte le orbite attualmente utilizzate in questo pool. Di seguito sono riportate le informazioni visualizzate:
    
      - URI (Uniform Resource Identifier) SIP del parcheggiato e del Parker.
    
      - Nome host del CPS in cui è parcheggiata la chiamata.
    
      - Indicatore di data e ora di quando la chiamata è stata parcheggiata.

  - **– parametro f** : elenca il numero di orbite attualmente libere nel pool.

  - **– r \<n\> ** parameter: elenca le \<\> ultime chiamate parcheggiate. Di seguito sono riportate le informazioni visualizzate:
    
      - URI SIP del parcheggio.
    
      - URI SIP Parker.
    
      - Nome host del CPS in cui la chiamata è stata parcheggiata.
    
      - Indicatore di data e ora di quando la chiamata è stata recuperata o eliminata.

  - **-t\<n\> ** -test dei parametri che riservano un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.

</div>

<div>

## <a name="output"></a>Output

In base ai parametri di input specificati al prompt dei comandi, la chiamata a Parkometer Visualizza l'output seguente:

  - Tutti gli intervalli di Orbit configurati per il pool

  - Chiamate attualmente parcheggiate

  - Numero di orbite libere (disponibili)

  - Chiamate parcheggiate di recente

  - Orbite riservate per testare valori di Orbit uniformi e casuali

</div>

<div>

## <a name="purpose"></a>Scopo

Lo strumento CPS ha lo scopo di fornire l'accesso da riga di comando al database CPS. L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbite assegnate a un pool.

</div>

<div>

## <a name="requirements"></a>Requisiti

Se lo strumento viene eseguito nello stesso computer in cui è in esecuzione CPS, non è previsto alcun requisito. Se lo strumento viene eseguito in un computer remoto, il database di SQL Server utilizzato da Lync Server 2013 deve essere configurato per consentire l'accesso remoto. La chiamata Parkometer deve essere configurata con una stringa di connessione al database di SQL Server per la connessione al server SQL del pool. La stringa di connessione del database di SQL Server è definita nel file di configurazione **parkometer. exe. config**. Deve essere collocato nella stessa directory in cui si trova parkometer. exe. Il file XML seguente è un esempio di parkometer. exe. config. I parametri che devono essere configurati sono il nome utente (ad esempio\\, l'amministratore di dominio), la password (ad esempio, password) e il nome host, ad esempio myserver.

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
       <add key="SQL" value="server=myserver\RTC;
    database=cpsdyn;
    User Id=mydomain\Administrator;
    Password=mypassword.;
    Integrated Security=false;"/>
      </appSettings>
    </configuration>
```

</div>

<div>

## <a name="examples"></a>Esempi

Intervalli di Orbit distribuiti: il parametro – o elenca tutti gli intervalli di Orbit configurati per il pool come illustrato

![Intervalli di Orbit in Call Parkometer.](images/JJ945604.9ede64cb-29d9-4782-a34b-b76c42fbdcad(OCS.15).jpg "Intervalli di Orbit in Call Parkometer.")

Chiamate attualmente parcheggiate: il parametro – n elenca tutte le orbite attualmente utilizzate in questo pool come illustrato

![Chiamate al momento parcheggiate in Call Parkometer.](images/JJ945604.07a7eec4-7999-4c92-93f0-95525b244b4c(OCS.15).jpg "Chiamate al momento parcheggiate in Call Parkometer.")

Numero di orbite libere: il parametro – f elenca il numero di orbite attualmente libere nel pool come mostrato

![Orbite gratuite in Call Parkometer.](images/JJ945604.ecc1d621-0ca0-4ecf-a579-08b41c6f08ed(OCS.15).jpg "Orbite gratuite in Call Parkometer.")

Chiamate parcheggiate di recente: il parametro \<–\> r n elenca \<le\> chiamate n Last parcheggiate come mostrato

![Chiamate parcheggiate di recente in Call Parkometer.](images/JJ945604.1c5eb27d-faa1-491b-b4aa-b484255c3353(OCS.15).jpg "Chiamate parcheggiate di recente in Call Parkometer.")

Test Orbit Reservation: i test dei \<parametri\> – t n che riservano un'orbita nel database come illustrato

![Testare le prenotazioni in orbita in Call Parkometer.](images/JJ945604.84c9b69e-7af0-4224-8711-a43a28f08691(OCS.15).jpg "Testare le prenotazioni in orbita in Call Parkometer.")

</div>

<div>

## <a name="summary"></a>Riepilogo

Call Parkometer è uno strumento da riga di comando che fornisce informazioni dettagliate sul server parcheggio di chiamata.

</div>

</div>

<div>

## <a name="cleanupstorageservicedata"></a>CleanupStorageServiceData

Lo strumento CleanupStorageServiceData Resource Kit consente di eliminare i dati orfani dal database utilizzato dal servizio di archiviazione di Lync Server (LYSS). Una funzione del servizio di archiviazione è la comunicazione del buffer tra Lync Server e diversi endpoint di archiviazione dei dati back-end, ad esempio SQL Server e Exchange.

<div>

## <a name="description"></a>Descrizione

Per supportare la disponibilità elevata, LYSS accetta e salva temporaneamente le copie dei dati su più Front End Server nel pool e rimuove tali dati dopo che sono stati recapitati nel percorso di archiviazione finale a lungo termine. È possibile che si verifichino situazioni inusuali durante il normale funzionamento, quando un server potrebbe bloccarsi o riscontrare un problema di elaborazione e alcuni dati potrebbero non essere stati ripuliti correttamente. Questi dati sono innocui, ma non utilizzano risorse di elaborazione limitate. Gran parte della normale manutenzione dei dati necessari è automatizzata, ma questo strumento consente di identificare e rimuovere in modo sicuro i dati orfani quando non è possibile la rimozione automatica. L'utilizzo di questo strumento è indicato quando viene generato un avviso di System Center Operations Manager (SCOM) per il monitoraggio dell'integrità che richiede all'amministratore di rimuovere i dati non necessari dai database locali LYSS nel pool. Verrà generato un evento corrispondente nel registro eventi sul front-end che ha attivato l'avviso. I dettagli dell'evento conterranno informazioni sulla quantità di dati orfani contenuti nel front-end e vengono generati quando tali dati superano determinate soglie predeterminate.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti di Lync Server 2013, Resource Kit. Lo strumento viene eseguito nei computer aggiunti a un dominio in cui sono installati Lync Server e Lync Server 2013 Management Shell. Lo strumento utilizza un cmdlet dalla shell di gestione per identificare tutti i Front End Server nel pool. In secondo luogo, è necessario eseguire lo strumento da un computer del pool in cui è installato il database di **RtcLocal** . Questo database viene utilizzato dallo strumento CleanupStorageServiceData per ottenere i dettagli della connessione necessari per comunicare con il servizio di routing di Lync Server. Infine, l'account o la credenziale che richiama lo strumento devono disporre dell'autorizzazione di lettura/scrittura per la condivisione file a cui si desidera scrivere il log di output. Inoltre, questo strumento dipende dal pool che si trova in uno stato stabile. In sostanza, questo significa che ogni Front End Server dovrebbe essere attivo e in esecuzione, l'istanza di SQL Server LYNCLOCAL e il database LYSS devono essere in grado di connettersi e ciascun gruppo di routing deve disporre di un set completo di 1 front end server primari e 2 front-end secondari s ervers.

</div>

<div>

## <a name="examples"></a>Esempi

C:\\Program Files\\Microsoft Lync Server 2013\\reskit\\StorageService\> ImportStorageServiceData. exe

    Description:
    This tool will remove orphaned data from the Storage Service database
    for a pool. You are required to run this tool on a machine inside the
    pool which has the Lync Server Management Shell installed and has RtcLocal database installed.
    Usage: Default behavior is to clean up orphaned data from the all the 
           Storage Service databases in the current pool.
    Additional Options:
    -Verbose    : Turn verbose output on.
    -LogPath    : The UNC path to which to write the log.
    ------------------------------------------------------------------------------
    Please wait while we initialize...
    Found 4 front end servers
    Replica Instances for LYSS Service
    Address: server2.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server1.vdomain.com - Primaries: 7 Secondaries: 14
    Address: server3.vdomain.com - Primaries: 7 Secondaries: 14
    Primary Total Count = 28, Secondary Total Count = 56
    Finding and removing orphaned data for 28 routing groups
    Removing 1 stale groups from FE server.vdomain.com
    No stale routing groups detected on FE server2.vdomain.com
    No stale routing groups detected on FE server1.vdomain.com
    No stale routing groups detected on FE server3.vdomain.com
    Searching for stale queue items
    Removed 20 stale queue items for routing group 17D5435AE40259F7BBDF1866776386E4
    No stale queue items found for routing group 1975349662315F90B119DACB4F2AE3AD
    No stale queue items found for routing group 1A23E3D58BDB5A458A0B73F34AB7ACBE
    No stale queue items found for routing group 1AC91E3A1029535A80123121989CEADC
    No stale queue items found for routing group 3313935458E35B9B9759E08A15D251E6
    No stale queue items found for routing group 39BB0035B06B5427873FC6099720462A
    No stale queue items found for routing group 40721948E7B55CE893A53E911F76D185
    No stale queue items found for routing group 4501E04EAE4856059346949FF817C220
    No stale queue items found for routing group 4D833C98801F546F8E45E417EE028E2E
    No stale queue items found for routing group 5AD77443AD955A22A876749BE66D5317
    No stale queue items found for routing group 69844A271E6C5633A1F2B46A42287DD6
    No stale queue items found for routing group 69DA3BE407A95C7284EB4B1337718C93
    No stale queue items found for routing group 8437358AB34A5CC8967D5EF39494AB8D
    No stale queue items found for routing group 8ED455B1789655359816E1C5BF4C430F
    No stale queue items found for routing group 904F6C9B8AC951AE8B3C86684D3832E4
    No stale queue items found for routing group 90AAB3AE9A1950E0ADE7809A27021D63
    No stale queue items found for routing group 944F5724C65C5F93900DC1C8C898B102
    No stale queue items found for routing group 9E8A2630250C51769E39F63F0FB552BA
    No stale queue items found for routing group A11E27AE439A582288D4657EDA86B565
    No stale queue items found for routing group A9B10C76E764556FAEA3E47301EDF518
    No stale queue items found for routing group AEA2699E74ED59848ACEA7896699430D
    No stale queue items found for routing group B269961603E75065AFDA4F4F006DA5E4
    No stale queue items found for routing group BB873D9A3DA959DAB2FD743E5AA619F7
    No stale queue items found for routing group BCC6A48FBA2454B79B9EDB276657A404
    No stale queue items found for routing group C8EF4805722B5F6C876EBC0440B420FD
    No stale queue items found for routing group CA38EBDAC4845489ACE208C2240E4056
    No stale queue items found for routing group F5921887DB025C5F908CE42DB7F1AEE8
    No stale queue items found for routing group F9E606A825395422B3BF7A01ECBB7B1F
    Writing log: M:\Dev\Server\ResKit\StorageService\CleanupStorageServiceData.Log_20121009_151040
    Tool has finished execution.  Errors encountered: 0
    C:\Program Files\Microsoft Lync Server 2013\ResKit\StorageService>

</div>

</div>

<div>

## <a name="dbanalyze"></a>DBAnalyze

<div>

## <a name="description"></a>Descrizione

DBAnalyze è uno strumento da riga di comando che consente agli amministratori di raccogliere report di analisi sui database di Lync Server 2013. In DBAnalyze sono disponibili le seguenti modalità: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:

  - **La modalità**   diagnostica consente di creare un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati e dimensioni degli indici, dimensioni dei file di dati e di log, ultimo tempo di backup, distribuzione dei contatti tra i server che eseguono Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, abbonamenti, pubblicazioni, endpoint per utente, utenti non adeguatamente ospitati, utenti che non possono essere instradati, numero medio di conferenze organizzate per utente conferenze, conferenze attive e versione del database.
    
    <div>
    

    > [!NOTE]  
    > L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.

    
    </div>

  - **Modalità**  dati utente segnala contatti, contenitori, abbonamenti, pubblicazioni, autorizzazioni e dati del gruppo di contatti per un utente specificato o per gli utenti che dispongono di tale utente negli elenchi di contatti e autorizzazioni. Questa modalità segnala anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.

  - **In modalità**   conferenza vengono riportati i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli relativi alla programmazione per la conferenza, l'elenco degli invitati, l'elenco dei tipi di contenuto multimediale consentiti per la conferenza, i MCU attivi (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.

  - **Decode ID**  riunione consente di decodificare un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** ma non viene connesso al back-end per informazioni dettagliate.

  - **Resolve Conference**   consente di decodificare un ID riunione PSTN specificato dall'opzione **/pstnid** e di visualizzare le informazioni sulla conferenza indicate dall'ID.

  - **La modalità**  MCU segnala l'ID, il tipo di supporto, l'URL, lo stato del battito cardiaco, il carico delle conferenze e il carico dei partecipanti per ogni MCU del pool.

  - **La modalità**  di frammentazione del disco Visualizza lo stato di frammentazione di tutti i dischi.

Questo strumento può essere utilizzato per diagnosticare diversi problemi o per assistere gli amministratori nella pianificazione della capacità. Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie gli utenti ospitati nel server B come contatti, l'amministratore può spostare gli utenti nel server a nel server B per ridurre il traffico tra server.

</div>

<div>

## <a name="output"></a>Output

Questo strumento restituisce i report predefiniti relativi al database di Lync Server 2013. **Percorso:** % ProgramFiles%\\Microsoft Lync Server 2013\\reskit

</div>

<div>

## <a name="purpose"></a>Scopo

Per installare Dbanalyze. exe, copiarlo in una cartella locale e quindi eseguire lo strumento. Per utilizzare lo strumento, eseguire il comando riportato di seguito dalla riga di comando.`dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Di seguito sono riportate le descrizioni delle opzioni della riga di comando.

![Opzioni della riga di comando per Dbanalyze. exe.](images/JJ945604.22bf3432-af6d-495b-8f48-d94c5d259523(OCS.15).jpg "Opzioni della riga di comando per Dbanalyze. exe.")

</div>

<div>

## <a name="requirements"></a>Requisiti

**Computer** DBAnalyze può essere eseguito solo da un computer aggiunto al dominio in cui è installato Lync Server 2013.

**Rete** Il computer deve essere in grado di connettersi al database back-end.

**Software** I componenti software di Lync Server 2013 devono essere installati prima di eseguire DBAnalyze.

**Utenti** Nella tabella seguente sono riportati gli amministratori che dispongono delle autorizzazioni necessarie per accedere ai database di Lync Server 2013.

![Tabella delle autorizzazioni per Dbanalyze. exe.](images/JJ945604.b8931e9e-834e-4dec-8a84-2fc47d1613e9(OCS.15).jpg "Tabella delle autorizzazioni per Dbanalyze. exe.")

<div>


> [!NOTE]  
> Per <STRONG>/report: modalità disco</STRONG> è necessario un account di amministratore locale.



</div>

</div>

<div>

## <a name="examples"></a>Esempi

Di seguito sono riportati alcuni esempi di comandi di Dbanalyze. exe validi:

    dbanalyze.exe /report:diag
    dbanalyze.exe /report:user /user:usera@domainb.com
    dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
    dbanalyze.exe /report:resolve /pstnid:12345
    dbanalyze.exe /report:mcus
    dbanalyze.exe /report:disk

</div>

<div>

## <a name="summary"></a>Riepilogo

DBAnalyzer offre agli amministratori un semplice e veloce analisi dei database di Lync Server 2013.

</div>

</div>

<div>

## <a name="importstorageservicedata"></a>ImportStorageServiceData

Lo strumento ImportStorageServiceData Resource Kit consente di riimportare i dati di coda e di endpoint che sono stati scaricati dal servizio di archiviazione (LYSS) nuovamente nel servizio di archiviazione.

<div>

## <a name="description"></a>Descrizione

I dati scaricati dal servizio di archiviazione avrebbero potuto essere automatici (periodici) in base allo stato della coda o alle dimensioni del database. Potrebbe essere accaduto a causa della chiamata manuale del cmdlet di failover del pool oppure del cmdlet StorageServiceFullFlush (che richiama il cmdlet di failover del pool). Si noti che i dati non devono essere reimportati idealmente se una delle dimensioni del database del servizio di archiviazione (LYSS) ai front-end è superiore al livello normale, perché in questo modo è probabile che vengano esportati più dati da esportare. Inoltre, tutti i problemi che potrebbero aver contribuito a errori che hanno causato la crescita della coda del servizio di archiviazione devono essere prima risolti (ad esempio, errori di endpoint di Exchange, problemi di rete o altri problemi).

**Scenario 1:** durante il failover del pool, i file possono essere scaricati dal servizio di archiviazione per ogni front-end. Dopo aver completato il failover, è necessario eseguire lo strumento per importare di nuovo i dati.

**Scenario 2:** i dati vengono scaricati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera le soglie di determinate dimensioni, ad esempio 60%, 80%, 90% Full. I dati scaricati automaticamente devono essere reimportati di routine dall'amministratore. Nella situazione precedente, se il Monitoring SCOM Pack non è distribuito, esistono eventi per il servizio di archiviazione di Lync Server relativo ai dati scaricati dal servizio di archiviazione. ID evento di 32075 (operazione full Flush è stato avviato), 32076 (Full Flush è stato completato), 32082 (livello di manutenzione incasso iniziato), 32083 (livello di manutenzione incasso completo), 32089 (si è verificato un errore a causa del riempimento del database). Nota Questi ID di evento corrispondono alla versione RTM. Quando un amministratore Visualizza questi eventi, significa che sono presenti file che sono stati scaricati. Questi dati devono essere importati di nuovo usando questo strumento, ad esempio una volta alla settimana.

Per la versione del servizio online, se il monitoraggio dello stato SCOM Pack per Lync Server è distribuito, sono disponibili nuovi avvisi che possono essere generati dall'amministratore per reimportare nuovamente i dati scaricati nel servizio di archiviazione. Nel log eventi del front end server è presente un evento corrispondente che ha attivato l'avviso. L'evento fornirà una descrizione del percorso padre in cui si trovano i file di dati scaricati, nonché il numero di file che soddisfano i criteri di avviso. I criteri di avviso sono che sono presenti X o più file sotto il percorso padre specifico che hanno almeno Y giorni (dove X e Y sono preimpostati all'interno di StorageService ma possono essere ignorati cambiando il file APPCONFIG). Di seguito sono riportati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre. Una possibilità è in condivisione file del servizio Web, mentre l'altra possibilità è la directory dei dati dell'applicazione locale di ogni front-end. (ad esempio c:\\ProgramData\\Microsoft\\Lync Server\\StorageService). L'amministratore eseguirà quindi questo strumento reskit.

Questo strumento aumenterà il carico di CPU e IO sul front-end in cui è in esecuzione, oltre ad altri front-end, nella situazione in cui i dati non sono posseduti dal front-end in cui viene eseguito lo strumento. Si consiglia di Runng questo strumento quando i front-end non sono sotto carico elevato di CPU e IO, ad esempio al di fuori delle ore di punta. In secondo luogo, questo strumento può includere da 2 a 3 minuti per importare un file di dati. Tenere presente questo valore quando si stima la durata dell'esecuzione dello strumento. Il file di registro dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file. Eliminarlo se non sono stati segnalati errori, in quanto il file di registro può essere pari o superiore a 10 MB.

![Eventi del registro eventi del server di archiviazione di esempio.](images/JJ945604.3a903ef7-ea8a-4606-8229-a3e32f13af3a(OCS.15).jpg "Eventi del registro eventi del server di archiviazione di esempio.")

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti di Lync Server 2013, Resource Kit. Lo strumento viene eseguito nei computer aggiunti a un dominio in cui sono installati Lync Server e Lync Server Management Shell. Lo strumento utilizza un cmdlet dalla shell di gestione per identificare tutti i Front End Server nel pool. In secondo luogo, è necessario eseguire lo strumento da un computer del pool in cui è installato il database di **RtcLocal** . Questo database viene utilizzato dallo strumento per recuperare il percorso della condivisione file WEBSERVICE per il pool. Inoltre, prima di utilizzare lo strumento, ogni Front End Server deve innanzitutto abilitare la comunicazione remota di Windows PowerShell tramite **Enable-PSRemoting** in ogni Front End Server, nonché il computer da cui viene eseguito lo strumento. In caso contrario, i comandi remoti di Windows PowerShell da questo strumento avranno esito negativo. La comunicazione remota di Windows PowerShell può essere disattivata in tutti i Front End Server nel pool dopo che è stata completata. Infine, l'account o la credenziale che richiama lo strumento deve disporre dell'autorizzazione di lettura/scrittura per la condivisione file WebService per il pool in cui è in esecuzione lo strumento. In caso contrario, lo strumento avrà esito negativo con errori di autorizzazione di IO.

<div>


> [!NOTE]  
> In Windows Server 2012, la comunicazione remota di Windows PowerShell è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.



</div>

</div>

<div>

## <a name="examples"></a>Esempi

    >  C:\StorageService>ImportStorageServiceData.exe
    Description:
    This tool will re-import Storage Service (LYSS) flushed queue data back in.  For a pool: you are required to run this tool on a machine inside the pool which has the Lync Server Management Shell installed.  Additionally, all front end machines need to have Windows Powershell Remoting enabled before executing this tool by executing Enable-PSRemoting.  Also, please ensure that all Storage Service instance DB Size are at the 'Normal' level (verify this by viewing Eventlog events). Otherwise re-importing may cause data to be flushed out again if any Storage Service instance DB size level goes above 'Normal'.
    Usage: Default behavior is to Import data from web service file share as well as any files on all Front End machines in pool.
    Additional Options:
    -Verbose                    : Turn verbose output on.
    
    -StorageServiceHostName     : Host Name of Storage Service WCF endpoint.  ( Default=localhost netnamedpipe binding. )
                                        
    -FileSharePath              : Import only all data from just under the UNC path specified.
    
    ActivityID: cc3b62ff-bb66-4e61-a6e2-96cb3626315c. <-- Use this to correlate with StorageService trace logs if troubleshooting.
    Type Server name (TCP binding) or press <enter> for localhost (NamePipe binding):
    Using NetNamedPipeBinding...
    OnTopologyChanged Event received
    Web Service File Share: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService
    
    Front Ends:
    server.vdomain.com
    server2.vdomain.com
    server1.vdomain.com
    server3.vdomain.com
    Looking under directory: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService for exported data.
    # Files found: 8
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    Items deserialized: 20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER.vdomain.com\944f5724c65c5f93900dc1c8c898b102__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\17d5435ae40259f7bbdf1866776386e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server1.vdomain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d
    3832e4__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER1.vdomain.com\904f6c9b8ac951ae8b3c
    86684d3832e4__0.xml
    
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER1.vdomain.com\904f6c9b8ac951ae8b3c86684d3832e4__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server2.vdom
    ain.com, queueItems=20
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42
    287dd6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER2.vdomain.com\69844a271e6c5633a1f2
    b46a42287dd6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER2.vdomain.com\69844a271e6c5633a1f2b46a42287dd6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml
    
    Items deserialized: 20
    
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759e08a15
    d251e6__0.xml
    
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\3313935458e35b9b9759
    e08a15d251e6__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\3313935458e35b9b9759e08a15d251e6__0.xml: succeeded: 20, failed: 0
    
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=1
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346949ff8
    17c220__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\4501e04eae4856059346
    949ff817c220__0.xml
    
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\4501e04eae4856059346949ff817c220__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml
    
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876749be6
    6d5317__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\5ad77443ad955a22a876
    749be66d5317__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\5ad77443ad955a22a876749be66d5317__0.xml: succeeded: 20, failed: 0
    Starting Import for file:\\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\2
    0120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml
    Items deserialized: 20
    [cc3b62ff-bb66-4e61-a6e2-96cb3626315c] Send EnqueueMessages to redirected, targetServer=server3.vdom
    ain.com, queueItems=20
    All items in file were enqueued successfully, will try to delete file: \\dc.vdomain.com\OcsFileStore
    \co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4657eda
    86b565__0.xml
    All items in file failed to enqueue so file will not be deleted.  File path: \\dc.vdomain.com\OcsFil
    eStore\co1-WebServices-1\StorageService\DataExport\20120910\SERVER3.vdomain.com\a11e27ae439a582288d4
    657eda86b565__0.xml
    Summary for file \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\DataExport\20120910\
    SERVER3.vdomain.com\a11e27ae439a582288d4657eda86b565__0.xml: succeeded: 20, failed: 0
    All files have been imported into Storage Service for path: \\dc.vdomain.com\OcsFileStore\co1-WebSer
    vices-1\StorageService
    Importing files for: server.vdomain.com
    No files founds.
    Importing files for: server2.vdomain.com
    No files founds.
    Importing files for: server1.vdomain.com
    No files founds.
    Importing files for: server3.vdomain.com
    No files founds.
    Writing log: \\dc.vdomain.com\OcsFileStore\co1-WebServices-1\StorageService\ImportStorageServiceData
    Log20120910_1609SS
    Tool has finished execution.
    >  C:\StorageService>

</div>

</div>

<div>

## <a name="lcssync"></a>LCSSync

Lo strumento LCSSync consente di distribuire il software di comunicazione di Lync Server 2013 in un ambiente con più foreste. Questo strumento viene utilizzato per sincronizzare gli utenti e i gruppi provenienti da foreste di utenti diverse come un oggetto contatto di servizi di dominio Active Directory in una foresta centrale in cui è installato Lync Server 2013.

<div>

## <a name="description"></a>Descrizione

LCSSync utilizza gli oggetti contatto di servizi di dominio Active Directory sincronizzati nella foresta centrale per consentire agli utenti di Lync Server. Per fornire l'accesso Single Sign-in, è necessario eseguire il mapping dell'account utente primario all'oggetto contatto dei servizi di dominio Active Directory nella foresta centrale per Lync Server 2013. Questo strumento consente di eseguire tale mapping. Questo strumento fornisce modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.

</div>

<div>

## <a name="summary"></a>Riepilogo

Lo strumento LCSSync consente di distribuire Lync Server in un ambiente con più foreste.

</div>

</div>

<div>

## <a name="lookupuserconsole"></a>LookupUserConsole

Lo strumento LookupUserConsole consente di visualizzare le informazioni di routing interne di Lync Server relative a utenti specifici. Tali informazioni possono essere utili per il supporto tecnico di Microsoft nella diagnostica dei problemi di distribuzione e routing.

<div>

## <a name="description"></a>Descrizione

L'esecuzione di LookupUserConsole. exe aprirà un prompt dei comandi che accetta gli indirizzi SIP e tenta di visualizzare le informazioni di routing interne di Lync Server correlate. Digitare **Exit** per chiudere lo strumento LookupUserConsole.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti di Lync Server 2013, Resource Kit. Lo strumento viene eseguito nei computer aggiunti a un dominio in cui è installato Lync Server

</div>

<div>

## <a name="examples"></a>Esempi

C:\\Program Files\\Microsoft Lync Server 2013\\reskit\>LookupUserConsole. exe

    > sip:john.doe@vdomain.com
    
      Execution time (ms):                            171.094
      Exeuction result:                               Success
      SIP URI:                                        sip:john.doe@vdomain.com
      User info:
        SID:                                          S-1-5-21-2831376166-29632525...    Display name:                                     John Doe
        Grouping ID:                                  00000000-0000-0000-0000-...
        Line URI:                                     <null>
        Policy assignment:                            TenantId={00000000--0000-000....
        SIP enabled:                                  True
        UC enabled:                                   False
        Tenant ID:                                    00000000-0000-0000-0000-...  Cluster info:
        Active cluster:                               pool0.vdomain.com
        Backup registrar cluster:                     <null>
        Deployment location:                          <null>
        Home Front-End FQDN:                          SERVER.vdomain.com
        Primary Registrar cluster:                    pool0.vdomain.com
        Remote Director external SIP FQDN:            <null>
        Remote Director internal SIP FQDN:            <null>
        Remote Director Web FQDN:                     <null>
        Routing group ID:                             4501e04e-ae48-5605-9346...
        Service tag ID:                               1266953005
        User Front-End resolved:                      True
        User in local forest:                         True
        User in remote forest:                        False
        User in split domain:                         False
        User-Services cluster:                        pool0.vdomain.com
    
    > sip:nouser@vdomain.com
    
      Execution time (ms):                            948.7574
      Exeuction result:                               UserDoesNotExist
    
    > exit

</div>

</div>

<div>

## <a name="msturnping"></a>MsTurnPing

Lo strumento MSTurnPing consente a un amministratore del software Microsoft Lync Server 2013 Communications di controllare lo stato dei server che eseguono i servizi audio/video e di autenticazione audio/video, nonché i server che eseguono i servizi per i criteri di larghezza di banda nella topologia.

<div>

## <a name="description"></a>Descrizione

Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Lync Server 2013 di controllare lo stato dei server che eseguono i servizi di autenticazione audio/video e i server che eseguono i servizi per i criteri di larghezza di banda nella topologia.

Lo strumento consente all'amministratore di eseguire i test seguenti:

1.  Test a/V Edge Server: lo strumento esegue test su tutti i server a/V Edge nella topologia eseguendo le operazioni seguenti:
    
      - Verificare che il servizio di autenticazione audio/video di Lync Server sia stato avviato e che sia possibile emettere credenziali appropriate.
    
      - Verifica del corretto avvio del servizio di Edge audio/video di Lync Server ed è in grado di allocare correttamente le risorse sul perimetro esterno.

2.  Test del servizio criteri di larghezza di banda: lo strumento esegue test su tutti i server che eseguono i servizi dei criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:
    
      - Verifica che il servizio criteri di larghezza di banda di Lync Server (autenticazione) sia avviato e possa emettere credenziali appropriate.
    
      - Verifica dell'avvio del servizio criteri di larghezza di banda di Lync Server (Core) ed è in grado di eseguire correttamente il controllo della larghezza di banda.

Questo strumento deve essere eseguito da un computer che fa parte della topologia e l'archivio locale è installato.

</div>

<div>

## <a name="output"></a>Output

Lo strumento restituisce i risultati di ciascuna delle operazioni.

  - Se viene eseguito il test di **AudioVideoEdgeServer** , gli output dello strumento sono i seguenti:
    
      - I risultati del test dei computer che forniscono il servizio di autenticazione audio/video di Lync Server nella topologia
    
      - I risultati del test dei computer che forniscono il servizio Edge audio/video di Lync Server nella topologia

  - Se viene eseguito il test di **BandwidthPolicyServer** , gli output dello strumento sono i seguenti:
    
      - I risultati del test dei computer che forniscono il servizio criteri di larghezza di banda di Lync Server (autenticazione) nella topologia
    
      - I risultati del test dei computer che forniscono il servizio criteri di larghezza di banda di Lync Server nella topologia

</div>

<div>

## <a name="requirements"></a>Requisiti

  - Questo strumento deve essere eseguito da un computer presente nella topologia e con l'archivio locale.

  - Lo strumento deve essere eseguito come un amministratore che ha accesso all'archivio locale.

</div>

<div>

## <a name="examples"></a>Esempi

Di seguito è riportato un esempio di input dello strumento.

    MsTurnPing -ServerRole AudioVideoEdgeServer
    
    MsTurnPing -ServerRole BandwidthPolicyServer

</div>

<div>

## <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa importante per gli amministratori di Lync Server 2013 che desiderano controllare lo stato dei server che eseguono i servizi di criteri di larghezza di banda e audio/video.

</div>

</div>

<div>

## <a name="network-configuration-viewer"></a>Visualizzatore di configurazione di rete

Il Visualizzatore di configurazione di rete può essere utilizzato dagli amministratori del software Microsoft Lync Server 2013 Communications per visualizzare la topologia di rete di controllo di ammissione di chiamata per un'azienda di cui è stato effettuato il provisioning per consentire sessioni di comunicazione in tempo reale, quali Voice o chiamate video in base alla capacità di larghezza di banda specificata. Gli amministratori di Lync Server 2013 definiscono i criteri di controllo della larghezza di banda, che vengono applicati dai servizi di Bandwidth Policy installati con Lync Server 2013.

<div>

## <a name="description"></a>Descrizione

Network Configuration Viewer (NetworkConfigurationViewer. exe) consente agli amministratori di eseguire le attività seguenti:

  - Caricare e visualizzare la topologia di rete CAC da una distribuzione di Lync Server 2013 in formato grafico.

  - Caricare e visualizzare la topologia di rete CAC da un file di registro del server dei criteri di larghezza di banda in formato grafico.

  - Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.

  - Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.

  - Visualizzare i dati di configurazione della topologia di rete CAC.

  - Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero.

  - Definire i connettori personalizzati per i collegamenti alla topologia di rete CAC (ad esempio, da siti a area geografica, dall'area geografica e da sito a sito).

  - Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sulle aree geografiche e i criteri di larghezza di banda e collegamenti di rete.

</div>

<div>

## <a name="purpose"></a>Scopo

Visualizzare i collegamenti alla topologia di rete Enterprise CAC in un'interfaccia grafica.

</div>

<div>

## <a name="examples"></a>Esempi

**Caricare e visualizzare la topologia di rete CAC da una distribuzione di Lync Server 2013 in formato grafico:** Gli amministratori di Lync Server 2013 possono caricare e visualizzare la configurazione della topologia di rete di CAC su qualsiasi computer Lync Server 2013 utilizzando l'opzione **Download Network Configuration** come mostrato nella figura seguente. Lo strumento non riesce a scaricare o visualizzare una configurazione di questo tipo quando viene distribuita in un computer che non dispone di connettività per l'archivio di configurazione di Lync.

![Download della configurazione di rete.](images/JJ945604.8d126d3f-2545-4f13-a244-974f09614982(OCS.15).jpg "Download della configurazione di rete.")

**Caricare e visualizzare la topologia di rete CAC da un file di registro del server dei criteri di larghezza di banda in formato grafico:** I server dei criteri di larghezza di banda di Lync Server 2013 salvano la topologia di rete CAC come parte del meccanismo di registrazione nel percorso di condivisione file di Lync Server 2013. Gli amministratori di Lync Server possono visualizzare un file di questo tipo in formato grafico utilizzando l'opzione di **configurazione della rete aperta** come illustrato di seguito.

![Apertura di un file di registro del server del criterio larghezza di banda.](images/JJ945604.3e503e92-aacb-4921-a8d2-23f860fe2df6(OCS.15).jpg "Apertura di un file di registro del server del criterio larghezza di banda.")

Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: gli amministratori di Lync Server 2013 possono salvare il file di configurazione della topologia di rete CAC in formato XML utilizzando l'opzione **Salva una copia di configurazione di rete** , come illustrato di seguito. Il file di configurazione salvato può quindi essere utilizzato offline per scopi di visualizzazione grafica.

![Salvataggio della configurazione di rete come file XML.](images/JJ945604.6eeef3b0-78b5-4ee6-8d94-1a4ddf3d8676(OCS.15).jpg "Salvataggio della configurazione di rete come file XML.")

Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP: gli amministratori di Lync Server 2013 possono salvare la configurazione della topologia di rete CAC in formato grafico (formati di file JPG e BMP) utilizzando l'opzione **Salva diagramma configurazione di rete come** illustrato di seguito.

![Salvataggio della configurazione di rete come immagine.](images/JJ945604.145a6fb9-58b1-46b1-bbd5-a661ceba07b4(OCS.15).jpg "Salvataggio della configurazione di rete come immagine.")

**Visualizzare i dati di configurazione della topologia di rete CAC:** Lync Server 2013 gli amministratori possono visualizzare i dati relativi alla configurazione della rete, ad esempio le aree di rete, i siti di rete, i profili larghezza di banda e gli indirizzi IP della subnet del sito in un formato testuale utilizzando l'opzione Visualizza dati di configurazione della rete come illustrato di seguito.

![Visualizzazione dei dati di configurazione di rete.](images/JJ945604.b72a4c21-a042-4d91-bf96-fcb396af0679(OCS.15).jpg "Visualizzazione dei dati di configurazione di rete.")

**Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero:** Gli amministratori di Lync Server 2013 possono visualizzare i dati relativi alla configurazione di rete in uno stile grafico tramite il pannello di controllo a sinistra della finestra degli strumenti, come illustrato di seguito.

![Visualizzazione dei dati di configurazione di rete in una visualizzazione struttura ad albero.](images/JJ945604.4d924ac9-fd96-430f-b211-ee35b7ef9a23(OCS.15).jpg "Visualizzazione dei dati di configurazione di rete in una visualizzazione struttura ad albero.")

**Definire i connettori personalizzati per i collegamenti alla topologia di rete CAC (quali collegamenti da sito a area** geografica e da sito a sito): Gli amministratori di Lync Server 2013 possono definire connettori grafici personalizzati per i collegamenti WAN di configurazione di rete di CAC utilizzando l'opzione impostazioni come illustrato di seguito. In questo modo è possibile distinguere tra vari tipi di collegamenti di rete di cui è stato effettuato il provisioning nella configurazione di rete.

![Definire i connettori personalizzati per la topologia di rete CAC](images/JJ945604.b20bea67-c8e1-453e-b1dd-e2aa17b62566(OCS.15).jpg "Definire i connettori personalizzati per la topologia di rete CAC")

**Visualizzare le informazioni sul sito della topologia di rete CAC, informazioni sulle aree e criteri di larghezza di banda provisioning:** Lync Server 2013 gli amministratori possono visualizzare le informazioni relative all'area di rete CAC, le informazioni sul sito e le informazioni sul provisioning della larghezza di banda di CAC tramite le opzioni illustrate di seguito Ad esempio, fare clic su **info** in un'area di rete o in un oggetto sito di rete.

![Definizione dei connettori personalizzati per la rete.](images/JJ945604.26262c75-4342-41c3-bc98-1793aa6a7713(OCS.15).jpg "Definizione dei connettori personalizzati per la rete.")

</div>

<div>

## <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa importante per gli amministratori di Lync Server 2013 che desiderano visualizzare la topologia di rete CAC per la distribuzione in formato grafico.

</div>

</div>

<div>

## <a name="response-group-agent-live"></a>Agente di Response Group Live

L'applicazione Response Group fornisce agli agenti la possibilità di accedere alle informazioni in tempo reale utili utilizzando il servizio Web incorporato. Purtroppo, nessuna visualizzazione grafica di questi dati è disponibile all'esterno dell'applicazione. Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo una modalità semplice e grafica per accedere a queste informazioni, migliorate con le informazioni sul software di comunicazione Microsoft Lync 2013 in tempo reale, come la presenza di altri agenti.

<div>

## <a name="description"></a>Descrizione

Response Group Agent Live è un'applicazione di Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale, ad esempio l'appartenenza a un gruppo e il numero corrente di chiamate, agli agenti di Response Group. È destinata a essere una versione avanzata della pagina gruppi di agenti (accessibile da Lync 2013.

</div>

<div>

## <a name="purpose"></a>Scopo

L'applicazione Response Group Accoda le chiamate in arrivo e quindi le instrada ai gruppi di agenti. Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere alle informazioni in tempo reale sui gruppi di agenti, ad esempio gli altri agenti disponibili e il numero di chiamate in attesa in ogni coda. Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono rese disponibili in modo intuitivo dall'agente di Response Group Live.

<div>

## <a name="features"></a>Caratteristiche

Lo strumento Response Group Agent Live si basa su Response Group Service e Microsoft Lync 2013 SDK. Fornisce agli agenti di Response Group le informazioni e le funzionalità disponibili dal servizio Response Group, ad esempio l'appartenenza ai gruppi, la presenza di altri agenti e il numero di chiamate in attesa.

Nella figura seguente viene illustrata l'interfaccia principale di Response Group Agent Live.

![Strumento di Response Group Agent Live.](images/JJ945604.63cb0374-a6ef-4a59-b60e-bec86a880d09(OCS.15).jpg "Strumento di Response Group Agent Live.")

Sono disponibili le tre funzionalità principali seguenti per gli agenti di Response Group Agent Live:

  - **Accesso/uscita:** Contrariamente alla pagina gruppi di agenti (accessibile da Lync 2013), l'agente di Response Group Live consente solo agli agenti di accedere o uscire contemporaneamente da tutti i gruppi di agenti. Questa applicazione offre tre modi rapidi per gli agenti di accedere o uscire:
    
      - Fare clic sui pulsanti di accesso/uscita (verde e rosso) all'interno dell'applicazione.
    
      - Fare clic con il pulsante destro del mouse sull'icona del vassoio di sistema e scegliere Accedi o Disconnetti.
    
      - Utilizzo di tasti di scelta rapida configurabili.

  - **Appartenenza ai gruppi:** Quando si seleziona un gruppo di agenti, Response Group Agent Live Visualizza l'elenco degli agenti di questo gruppo nel riquadro destro. Se Lync 2013 è in esecuzione nello stesso computer in cui si trova questa applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate nell'agente Response Group Live. Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da qui.

  - **Statistiche in tempo reale:** Agente di Response Group Live fornisce statistiche in tempo reale per tutti i gruppi di agenti. La frequenza di aggiornamento è di un minuto. Quando una chiamata viene risolta da un Response Group, viene aggiunto un indicatore visivo accanto al nome del gruppo con il numero corrente di chiamate in coda. La sospensione del puntatore su un gruppo Visualizza anche il tempo di attesa più lungo.

</div>

</div>

<div>

## <a name="requirements"></a>Requisiti

L'agente Response Group Live richiede .NET Framework 4,0. Per sfruttare le funzionalità di presenza e scheda contatto, è inoltre necessario che Lync 2013 sia installato localmente (ed è in esecuzione).

<div>

## <a name="configuration"></a>Configurazione

L'agente di Response Group Live può essere personalizzato per le preferenze individuali utilizzando la finestra di dialogo Opzioni nell'applicazione. Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive. exe. config.

Nella figura seguente è illustrata la finestra di dialogo Opzioni che gli agenti possono utilizzare per configurare l'indirizzo host e i tasti di scelta rapida. È possibile accedere a questa finestra di dialogo facendo clic sul pulsante Opzioni nell'angolo in alto a destra dell'interfaccia principale.

![La finestra di dialogo Opzioni di Response Group Agent Live.](images/JJ945604.3cc15e29-8699-45ab-90c3-e1565fa6ebf6(OCS.15).jpg "La finestra di dialogo Opzioni di Response Group Agent Live.")

Nella configurazione di Response Group Agent Live è possibile personalizzare le tre diverse impostazioni seguenti:

  - Indirizzo host: questo è in genere l'FQDN del pool Web che appartiene al pool di origine dell'agente. L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (accodando il percorso destro dopo l'host).

  - Tasti di scelta rapida: i collegamenti esatti per l'accesso/uscita possono essere personalizzati. L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere il tasto "Windows logo" (oltre ad almeno un altro tasto).

  - Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.

</div>

</div>

<div>

## <a name="examples"></a>Esempi

Nella figura seguente viene illustrato come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.

![Effettuare una chiamata o inviare un messaggio istantaneo.](images/JJ945604.009cebe0-5a93-4745-89c3-8a16c7c13009(OCS.15).jpg "Effettuare una chiamata o inviare un messaggio istantaneo.")

Nella figura seguente viene illustrato il modo in cui agente di Response Group Live Visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte le chiamate in arrivo.

![Visualizzazione delle informazioni sulla coda.](images/JJ945604.131d7f79-b7ed-41f5-a9da-ffc556e31037(OCS.15).jpg "Visualizzazione delle informazioni sulla coda.")

</div>

<div>

## <a name="summary"></a>Riepilogo

L'accesso rapido e l'accesso, l'appartenenza a gruppi e le statistiche di base in tempo reale sono interessanti funzionalità di agente di Response Group disponibili solo all'esterno dell'applicazione dal servizio Response Group. Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Lync possono fornire ai propri agenti un'applicazione Windows che consenta di eseguire le attività in modo più rapido e grafico.

</div>

</div>

<div>

## <a name="sefautil"></a>SEFAUtil

SEFAUtil (Secondary Extension feature Activation) è uno strumento da riga di comando che consente a Microsoft Lync Server 2013 Communications Administrators e agli agenti del supporto tecnico di configurare l'anello delegato, l'inoltro di chiamata, lo squillo simultaneo, la chiamata di Team impostazioni e raccolta di chiamate di gruppo per conto di un utente di Lync Server 2013. Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro delle chiamate o squillare contemporaneamente per conto dell'utente. L'amministratore può specificare la destinazione (nel formato di un URI SIP) oppure utilizzare una destinazione che è già stata pubblicata dall'utente. Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere i delegati o i membri del gruppo di chiamata del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0 e richiede che gli amministratori creino un'applicazione attendibile nell'archivio di gestione centrale per SEFAUtil

SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori e agli agenti del supporto tecnico di Lync Server 2013 di configurare lo squillo di delegati, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni di chiamata di team e di gruppo per conto di un utente di Lync Server 2013. . Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un utente specifico.

<div>

## <a name="description"></a>Descrizione

La versione corrente di SEFAUtil è solo uno strumento da riga di comando. non è disponibile un'interfaccia utente grafica di supporto. Questo strumento si basa su Microsoft Unified Communications Managed API (UCMA) 3,0. Le funzionalità di questo strumento consentono agli amministratori e agli agenti del supporto tecnico di eseguire le operazioni seguenti:

  - Visualizzare tutte le impostazioni di routing delle chiamate per un utente (include l'inoltro di chiamata, la delega, lo squillo simultaneo, la chiamata di team e il prelievo delle chiamate di gruppo)

  - Abilitazione/disabilitazione/modifica dell'impostazione di inoltro di chiamata (include il timer di destinazione e no-answer)

  - Abilitare/disabilitare/modificare le configurazioni immediate di inoltro di chiamata

  - Abilitazione/disabilitazione/modifica delle impostazioni di delega

  - Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamata del team
    
    <div>
    

    > [!NOTE]  
    > Nuovo strumento di SEFAUtil di Lync Server 2013

    
    </div>

  - Abilitazione/disabilitazione/modifica delle impostazioni di squillo simultaneo (include la destinazione)
    
    <div>
    

    > [!NOTE]  
    > Nuovo strumento di SEFAUtil di Lync Server 2013

    
    </div>

  - Abilitazione/disabilitazione/modifica delle impostazioni di prelievo delle chiamate di gruppo
    
    <div>
    

    > [!WARNING]  
    > Nuovo strumento di SEFAUtil di Lync Server 2013

    
    </div>

Questo strumento presenta le limitazioni seguenti:

  - Supportato solo per gli utenti ospitati in un pool di Lync Server

  - La modifica in blocco delle impostazioni di routing delle chiamate per più utenti non è supportata

</div>

<div>

## <a name="output"></a>Output

La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi. Per ulteriori informazioni, vedere la sezione Examples più avanti in questo documento.

</div>

<div>

## <a name="purpose"></a>Scopo

Di seguito sono riportati alcuni degli scenari principali in cui è possibile utilizzare questo strumento:

  - Bob è un dirigente ed è stato spostato nella telefonia di Lync Server. Ha una delega per il sistema PBX esistente. Come parte dello spostamento in Lync, l'amministratore è in grado di configurare il routing di Roberto per riflettere la configurazione della delega preesistente.

  - Alice è in viaggio e si rende conto che è in attesa di una chiamata importante da uno dei suoi clienti. Tuttavia, si trova in un hotel e non ha accesso a un computer. Chiama il supporto tecnico e richiede di inoltrare al proprio numero di cellulare tutte le chiamate effettuate al proprio numero di lavoro. Il personale del supporto tecnico è in grado di eseguire la configurazione per suo conto.

  - Le chiamate di Joe al suo numero di lavoro stanno per passare alla segreteria telefonica mobile ogni volta che è al lavoro; Tuttavia, la maggior parte delle altre posizioni sembra funzionare correttamente. Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di routing di Joe e rileva che Joe ha squillato simultaneamente configurato sul suo cellulare. Il tecnico chiede a Joe la copertura per dispositivi mobili nel suo ufficio ed è in grado di determinare che la regola di squillo simultaneo è ciò che sta causando la chiamata per andare alla segreteria telefonica di Joe quando la sua copertura di rete è scadente.

  - Mike è un nuovo dipendente di contoso ed entra a far parte di un nuovo team in cui tutti i membri sono configurati per la chiamata di Team, quando viene abilitato per Microsoft Lync, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamata del team per includere tutti i nuovi membri del team, inoltre, il l'amministratore aggiunge Mike come membro del gruppo di chiamata del team per ognuno dei membri del team.

  - Una pratica del servizio clienti nel reparto risorse umane di Contoso è quella di fornire un servizio personale per tutti i chiamanti dopo la prima chiamata. Dato che tutti i membri del dipartimento siedono molto vicini l'uno all'altro, tutti i telefoni che squillano contemporaneamente con il team-Call sono molto sconvolgenti per il team. Per fornire il miglior servizio senza interrompere i membri del team, l'amministratore di Lync sfrutta la funzionalità di prelievo delle chiamate di gruppo. L'amministratore aggiunge tutti i membri del reparto a un gruppo di prelievo e comunica al reparto il numero del gruppo di prelievo. Quando Samantha è assente dalla sua scrivania, Joe si accorge di squillare il telefono e procede a rispondere alla telefonata dalla sua scrivania.

</div>

<div>

## <a name="requirements"></a>Requisiti

Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. UCMA 3,0 deve essere installato nel computer in questione. Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID dell'applicazione SEFAUtil in tale pool.

**Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil**

1.  Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere completata tramite Lync Server Management Shell con il cmdlet seguente:
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
    
    <div>
    

    > [!NOTE]  
    > UCMA 3,0 deve essere installato in qualsiasi computer che verrà utilizzato per eseguire lo strumento SEFAUtil.

    
    </div>

2.  È necessario definire un'applicazione attendibile nella topologia per lo strumento SEFAUtil. Per definire SEFAUtil come nuova applicazione attendibile, utilizzare Lync Server Management Shell ed eseguire il cmdlet seguente:
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > Se necessario, è possibile utilizzare una porta diversa.

    
    </div>

3.  Le modifiche alla topologia devono essere attivate. L'abilitazione delle modifiche alla topologia può essere eseguita tramite Lync Server Management Shell eseguendo il cmdlet seguente:
    
        Enable-CsToplogy

4.  Se necessario, installare gli strumenti di Lync Server 2013 Resource Kit nel server che verrà utilizzato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).

5.  Verificare che SEFAUtil sia in esecuzione correttamente. A tale scopo, eseguire lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. Per impostazione predefinita, lo strumento sarà disponibile in: "... \\File\\di programma Microsoft Lync Server\\2013 reskit ". Per visualizzare le impostazioni di inoltro di chiamata di un utente, utilizzare il seguente comando:
    
        SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
    
    Le impostazioni di inoltro di chiamata dell'utente devono essere visualizzate.

<div>

## <a name="group-call-pickup"></a>Prelievo delle chiamate di gruppo

La funzionalità di prelievo delle chiamate di gruppo richiede una configurazione aggiuntiva in Lync Server per la possibilità di essere abilitata completamente. Prima di assegnare i gruppi di prelievo agli utenti, fare riferimento alla documentazione del prodotto di prelievo delle chiamate di gruppo per i passaggi di pianificazione e distribuzione di questa funzionalità.

</div>

</div>

<div>

## <a name="examples"></a>Esempi

<div>

## <a name="display-current-call-handling-settings"></a>Visualizzazione delle impostazioni di gestione delle chiamate correnti

Il comando seguente consente di visualizzare la gestione delle chiamate per l'utente. `SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com`

<div>


> [!NOTE]  
> In questo esempio viene utilizzata l'opzione <STRONG>/Server</STRONG> per specificare il server Lync a cui connettersi.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:20
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-call-forwardno-answer-destination"></a>Impostare la destinazione di chiamata forward/no answer

In questo esempio viene impostata la destinazione di chiamata forward/No Answer e il ritardo dell'anello. In questo caso, l'opzione/server non è disponibile. SEFAUtil tenta di individuare in modo automatico il server Lync.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="enable-call-forwarding-immediately"></a>Abilitazione immediata dell'inoltro di chiamata

In questo esempio viene immediatamente abilitato l'inoltro di chiamata a un altro utente.

    SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Forward immediate to: sip:anders@contoso.com

</div>

<div>

## <a name="disable-call-forwarding-immediately"></a>Disabilitare immediatamente l'inoltro di chiamata

In questo esempio viene disabilitato immediatamente l'inoltro di chiamata.

    SEFAUtil.exe /server:lyncserver.contoso.com katarina@contoso.com  /disablefwdimmediate

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Aggiungere un utente come delegato e impostare lo squillo simultaneo dei delegati

In questo esempio viene aggiunto un utente come delegato e viene impostato lo squillo simultaneo dei delegati.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simultaneously Ringing Delegates: sip:joe@contoso.com

</div>

<div>

## <a name="change-simultaneous-ringing-rule-of-delegates"></a>Modificare la regola di chiamata simultanea dei delegati

In questo esempio viene modificata la regola di chiamata simultanea configurata nell'esempio precedente alla regola di chiamata ritardata.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com

</div>

<div>

## <a name="remove-the-delegate"></a>Rimuovere il delegato

In questo esempio viene rimosso il delegato.

<div>


> [!NOTE]  
> Quando l'ultimo delegato viene rimosso, il delegare squillo viene disabilitato automaticamente.



</div>

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Aggiungere un delegato e impostare la regola per i delegati di chiamata in avanti

In questo esempio viene aggiunto un delegato e viene impostata la regola dei delegati di chiamata inoltrata.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Forwarding calls to Delegates: sip:anders@contoso.com

</div>

<div>

## <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Abilitare lo squillo simultaneo e impostare un numero di destinazione

In questo esempio viene abilitato lo squillo simultaneo e viene impostato un numero di destinazione di squillo simultaneo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring

<div>


> [!NOTE]  
> Per modificare il numero di destinazione di squillo simultaneo di un utente che ha già attivato lo squillo simultaneo, mantenere il comando con l'opzione/enablesimulring, altrimenti il numero di destinazione non verrà modificato.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: True
    Simul_Ringing to: sip:+14255550126@contoso.com;user=phone

</div>

<div>

## <a name="disable-simultaneous-ringing"></a>Disabilitare lo squillo simultaneo

In questo esempio viene disabilitato lo squillo simultaneo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablesimulring

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Simulring enabled: False
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Aggiungere un membro del team per la chiamata di team e configurare lo squillo simultaneo al gruppo membri chiamata team

In questo esempio viene aggiunto un membro del team al gruppo di chiamata del team di un utente e viene abilitato lo squillo simultaneo al gruppo di chiamata del team.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam

<div>


> [!NOTE]  
> L'aggiunta di un membro al gruppo di chiamata del team di un utente commuterà automaticamente la settigs di suoneria simultanea degli utenti per simulring il gruppo di chiamata del team.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Team ringing enabled. Team: sip:anders@contoso.com

</div>

<div>

## <a name="remove-a-member-from-the-team-call-group"></a>Rimuovere un membro dal gruppo di chiamata del team

In questo esempio viene rimosso un membro del team del gruppo di chiamata del team di un utente.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com

<div>


> [!NOTE]  
> Se il membro che si sta rimuovendo è l'unico membro del gruppo di chiamata del team, lo squillo simultaneo al gruppo di chiamata del team verrà disabilitato automaticamente.



</div>

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="set-the-delayed-ring-to-the-team-call-group"></a>Impostare l'anello ritardato sul gruppo di chiamata del team

In questo esempio viene modificato l'anello ritardato nell'impostazione di tempo del gruppo di chiamata del team.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /delayringteam:5

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com

</div>

<div>

## <a name="enable-team-call"></a>Abilitazione di Team-Call

In questo esempio viene abilitata la chiamata di team per un utente specificato.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /simulringteam

<div>


> [!NOTE]  
> Se il gruppo di chiamata del team dell'utente non dispone di membri, la chiamata del team non verrà abilitata.



</div>

**Output**

</div>

<div>

## <a name="disable-team-call"></a>Disabilitare la chiamata di Team

In questo esempio viene disabilitata la chiamata del team per un utente specificato.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disableteamcall

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    User Ring time: 00:00:30
    Call Forward No Answer to: voicemail

</div>

<div>

## <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Attivazione del prelievo delle chiamate di gruppo e assegnazione di un gruppo di prelievo a un utente

In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitato il prelievo delle chiamate di gruppo.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199

**Output**

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True
    Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone

</div>

<div>

## <a name="disable-group-call-pickup"></a>Disattiva prelievo delle chiamate di gruppo

In questo esempio viene disabilitato il prelievo delle chiamate di gruppo per un utente specificato.

    SEFAUtil.exe /server:lyncserver.contoso.com sip:katarina@contoso.com /disablegrouppickup

<div>


> [!NOTE]  
> Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero del gruppo assegnato all'utente non viene mantenuto. Se successivamente si desidera riabilitare il prelievo delle chiamate di gruppo per tale utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione/enablegrouppickup.



</div>

    User Aor: sip:katarina@contoso.com
    Display Name: Katarina Larsson
    UM Enabled: True

</div>

</div>

</div>

<div>

## <a name="sysprepps1"></a>SYSPrep. ps1

<div>

## <a name="description"></a>Descrizione

SYSPrep. ps1 è uno script di Windows PowerShell che installerà i prerequisiti di Lync Server 2013 seguenti nel computer del sistema operativo Windows Server 2008.

  - Microsoft .NET Framework 4,5

  - Microsoft SQL Server Express

  - Windows PowerShell versione 3,0

  - Visual C++ 2010 Redistributable

  - Aggiornamenti di Internet Information Server

  - Windows Identity Foundation

  - File di base di Lync Server 2013

Sebbene il nome dello script sia analogo a quello dello strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi. Questo script consente di installare solo i prerequisiti necessari per Lync Server 2013. Dopo aver installato i prerequisiti, lo strumento SYSPrep di Windows può quindi essere utilizzato per creare un'immagine del server.

</div>

<div>

## <a name="requirements"></a>Requisiti

Prima di eseguire lo script SYSPrep. ps1, è necessario copiare i file prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008, ad esempio **D:\\Setup**. Questa cartella deve includere anche una copia dei file di Lync Server 2013, in particolare **Setup. exe.** È possibile scaricare i file prerequisiti dalle seguenti posizioni:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Posizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft .NET Framework 4,5</p></td>
<td><p>http://go.microsoft.com/?linkid=9816306</p></td>
</tr>
<tr class="even">
<td><p>Microsoft SQL Server Express 2008 R2</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=23650</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell versione 3,0</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34595</p></td>
</tr>
<tr class="even">
<td><p>Visual C++ 2010 Redistributable</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=5555</p></td>
</tr>
<tr class="odd">
<td><p>Aggiornamenti di Internet Information Server</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=34869</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation</p></td>
<td><p>https://www.microsoft.com/download/details.aspx?id=17331</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Setup. exe</p></td>
<td><p>Copia da Lync Server 2013 media</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="parameter"></a>Parametro

Il parametro **– SetupFolder** accetta come argomento il percorso della directory dei file prerequisiti

</div>

<div>

## <a name="examples"></a>Esempi

Per eseguire lo script SYSPrep. ps1 e installare i prerequisiti di Lync Server 2013, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:

    ./SysPrep.PS1 -SetupFolder D:\Setup

</div>

</div>

<div>

## <a name="unassigned-number-announcements-migration"></a>Migrazione degli annunci di numeri non assegnati

Lo strumento di migrazione annunci numeri non assegnati consente a un amministratore di Lync di spostare la configurazione dei numeri non assegnati serviti dall'applicazione annuncio da un server o pool di origine Lync a un Lync Server o un pool di destinazione.

<div>

## <a name="description"></a>Descrizione

Lo strumento di migrazione annunci numeri non assegnati è uno script di Windows PowerShell che consente di spostare la configurazione dei numeri non assegnati serviti dall'applicazione Annuncio di un server o di un pool di origine in un altro server o pool.

Quando viene eseguito, lo script di migrazione degli annunci dei numeri non assegnati eseguirà le operazioni seguenti:

1.  Spostare tutti i file audio utilizzati dagli annunci di numeri non assegnati dell'applicazione Annuncio ospitati nel server o nel pool di origine nell'archivio file del server o del pool di destinazione.
    
    <div>
    

    > [!NOTE]  
    > i file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.

    
    </div>

2.  Spostare tutti gli annunci di numeri non assegnati configurati per l'applicazione annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.

3.  Riassegnare tutti gli intervalli di numeri non assegnati serviti dall'applicazione annuncio ospitata nel server o nel pool di origine al server o al pool di destinazione.

Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati che sono stati serviti dall'applicazione annuncio ospitata nel server o nel pool di origine verranno ora serviti con la stessa configurazione dal server o dal pool di destinazione.

</div>

<div>

## <a name="output"></a>Output

Lo script **Move-CsAnnouncementConfiguration** indica nella finestra di Lync Management Shell dalla quale è stato eseguito l'esito positivo o negativo dell'operazione di migrazione.

Se l'esecuzione dell'operazione viene interrotta da un errore, gli intervalli di numeri non assegnati che sono stati spostati nella destinazione rimarranno nella destinazione in un modulo operativo e gli altri intervalli di numeri non assegnati di cui eseguire la migrazione rimarranno in l'origine anche in un modulo operativo. Per eseguire la migrazione completa del resto della configurazione, rieseguire lo script dopo l'indirizzamento dell'errore.

</div>

<div>

## <a name="purpose"></a>Scopo

Lo script di migrazione degli annunci dei numeri non assegnati può essere utilizzato nei tre scenari seguenti:

  - **Migrazione delle impostazioni di configurazione a una nuova versione di Lync Server:** Contoso è in fase di migrazione a Lync Server 2013 e come parte del processo di migrazione, l'amministratore di Lync Server desidera spostare la configurazione dei numeri non assegnati serviti dall'applicazione annuncio dalla distribuzione di Lync Server 2010 alla nuova distribuzione di Lync Server 2013. Per spostare le impostazioni di configurazione, l'amministratore di Lync Server utilizza lo strumento di migrazione annunci numeri non assegnati.

  - **Rollback di una distribuzione da Lync server 2013 a Lync server 2010:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Lync Server 2013. Per ridurre al minimo le interruzioni del servizio, l'amministratore di Lync Server utilizza lo strumento di migrazione degli annunci dei numeri non assegnati per eseguire il rollback della configurazione dalla distribuzione di Lync Server 2013 alla distribuzione di Lync Server 2010.

  - **Spostamento dei dati tra distribuzioni di Lync:** Contoso è in fase di sostituzione di tutti i server di un pool con server più recenti. La strategia è quella di distribuire un nuovo pool di Lync Server 2013, spostare tutti i dati dal vecchio al nuovo pool e quindi disapprovare il pool precedente. Dopo la distribuzione del nuovo pool, lo strumento di migrazione annunci di numeri non assegnati viene utilizzato per spostare la configurazione dal pool precedente a quello nuovo.

<div>

## <a name="requirements"></a>Requisiti

Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:

1.  Lo script deve essere eseguito da un computer in cui è installato Lync Server 2013 Management Shell.

2.  L'applicazione annuncio deve essere distribuita correttamente nei server o nei pool Lync di origine e di destinazione.

<div>

## <a name="move-csannouncementconfiguration-script"></a>Move-CsAnnouncementConfiguration script

Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.

![Parametri Move-CsAnnouncementConfiguration.](images/JJ945604.7ab66ad3-d0db-4d77-8b93-ebccf0cb0663(OCS.15).jpg "Parametri Move-CsAnnouncementConfiguration.")

</div>

</div>

</div>

<div>

## <a name="examples"></a>Esempi

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2010-pool-to-a-lync-server-2013-pool"></a>Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Lync Server 2010 a un pool di Lync Server 2013

In questo esempio vengono spostati gli annunci dei numeri non assegnati dal pool di origine (Lync Server 2010) al pool di destinazione (Lync Server 2013).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2010Pool.contoso.com -Destination LS2013Pool.contoso.com

</div>

<div>

## <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-lync-server-2010-pool"></a>Spostamento della configurazione degli annunci dei numeri non assegnati da un pool di Lync Server 2013 a un pool di Lync Server 2010

In questo esempio vengono spostati gli annunci dei numeri non assegnati dal pool di origine (Lync Server 2013) al pool di destinazione (Lync Server 2010).

    Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination LS2010Pool.contoso.com

</div>

</div>

</div>

<div>

## <a name="web-conf-data"></a>Dati Web conf

Lo strumento di dati di Web conf consente a un amministratore del software di comunicazione di Lync Server 2013 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore. Gli scenari includono la possibilità di eliminare i dati di una riunione di un utente specifico in base a criteri timestamp.

<div>

## <a name="description"></a>Descrizione

Questo strumento consente all'amministratore di eseguire le operazioni seguenti:

1.  Individuare tutti i dati di Web Conferencing associati a un singolo utente.

2.  Eliminare tutti i dati di Web Conferencing associati a un singolo utente.

3.  Eliminare tutti i dati di Web Conferencing associati a un singolo utente antecedente a una determinata data.

4.  Spostare tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.

<div>


> [!NOTE]  
> Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro. Questa funzionalità è ora obsoleta da questo strumento a favore del parametro <STRONG>MoveConferenceData</STRONG> . Per informazioni dettagliate su questo parametro, vedere il cmdlet <A href="https://technet.microsoft.com/library/gg398528(v=ocs.15)">Move-CsUser</A> .



</div>

Lo strumento consente di eliminare i dati delle riunioni solo per le riunioni inattive. Le riunioni attive (o le riunioni in sessioni) non possono essere eliminate.

Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione. L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere ospitato nello stesso pool di utenti.

</div>

<div>

## <a name="output"></a>Output

Questo strumento restituisce i risultati di ciascuna delle operazioni seguenti:

  - Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati riunione inattive che dispongono di tale utente come organizzatore.

  - Se viene eseguita un'operazione di eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati riunione i cui dati verranno eliminati.

</div>

<div>

## <a name="requirements"></a>Requisiti

Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitato l'organizzatore.

È necessario eseguire lo strumento utilizzando i privilegi di amministratore con accesso all'archivio file di contenuto.

</div>

<div>

## <a name="examples"></a>Esempi

Nella tabella seguente vengono descritti i parametri, alcuni dei quali sono utilizzati negli esempi.

![Parametri degli strumenti di dati Web conf.](images/JJ945604.a733c1c6-5dfc-4874-a74f-bfdee81c1401(OCS.15).jpg "Parametri degli strumenti di dati Web conf.")

    WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""

Nell'esempio precedente viene illustrato il funzionamento di un comando di query. L'output di un comando di questo tipo è un elenco di tutte le cartelle del contenuto delle riunioni che potrebbero essere intaccate da questo strumento.

    WebConfDataTool.exe /User:user0@contoso.com /Action:delete

Il precedente è un esempio di un comando Delete. Il comando Delete rimuoverà tutte le cartelle riunione inattive dall'utente.

</div>

<div>

## <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa importante per gli amministratori che hanno bisogno di un controllo più preciso sui dati delle riunioni.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>
