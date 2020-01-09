---
title: Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Questo argomento descrive gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi di utilizzo. Il Resource Kit di Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento di dati Web conf può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento SEFAUtil può essere usato per configurare l'inoltro di chiamata e la risposta dei delegati per gli utenti. Consigliamo agli amministratori IT di usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.
ms.openlocfilehash: 0087f4286246833f0266ad0c78636bad00167756
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992533"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentazione degli strumenti del Resource Kit di Skype for Business Server 2015

Questo argomento descrive gli strumenti del Resource Kit di Skype for Business Server 2015, incluso lo scopo di ogni strumento ed esempi di utilizzo. Il Resource Kit di Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento di **dati Web conf** può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento **SEFAUtil** può essere usato per configurare l'inoltro di chiamata e la risposta dei delegati per gli utenti. Consigliamo agli amministratori IT di usare questi strumenti per gestire in modo più efficace Skype for Business Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Installazione degli strumenti del Resource Kit

Per installare il Resource Kit di Skype for Business Server 2015, scaricare [OCSReskit. msi](https://www.microsoft.com/en-us/download/details.aspx?id=52631) dall'area download.

Eseguire **OCSResKit. msi** per eseguire un'installazione semplice. Il file con estensione msi installa tutti gli strumenti disponibili nel percorso seguente: **% Program Files%\Skype for Business Server 2015 \ reskit**. Gli strumenti che sono eseguibili indipendenti si trovano in questa cartella. Gli strumenti che hanno anche file di supporto sono presenti nelle sottocartelle.

## <a name="supported-environments"></a>Ambienti supportati

Il Resource Kit di Skype for Business Server 2015 deve essere installato in un server che soddisfi le specifiche richieste per Skype for Business Server 2015, in genere uno usato per eseguire Skype for Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Panoramica degli strumenti di Resource Kit

Di seguito è riportato un elenco degli strumenti forniti in Skype for Business Server 2015 Resource Kit. Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nelle sezioni seguenti.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitoraggio del servizio criteri di larghezza di banda](resource-kit-tools.md#bpsm)

- [Analizzatore dell'utilizzo della larghezza di banda](resource-kit-tools.md#bua)

- [Chiama Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importare i dati del servizio di archiviazione](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Console utente di ricerca](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visualizzatore Configurazione di rete](resource-kit-tools.md#NCV)

- [Agente di Response Group Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep. ps1](resource-kit-tools.md#SYSPrep)

- [Migrazione degli annunci di numeri non assegnati](resource-kit-tools.md#UNAM)

- [Dati Web conf](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Lo strumento di configurazione del servizio Rubrica (ABSConfig) è uno strumento di amministrazione che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Skype for Business Server 2015. Questo strumento consente inoltre agli amministratori di Skype for Business Server 2015 di ripristinare le impostazioni predefinite del servizio Rubrica.

### <a name="description"></a>Descrizione

ABSConfig è un'applicazione di interfaccia utente grafica che consente agli amministratori di configurare gli attributi dei servizi di dominio Active Directory correlati al servizio Rubrica.

Gli scenari principali per lo strumento sono i seguenti:

- Per consentire agli amministratori di eseguire il mapping degli attributi in servizi di dominio Active Directory agli attributi per Skype for Business Server 2015.

- Per consentire agli amministratori di specificare l'attributo servizi di dominio Active Directory da includere o escludere nei file del servizio Rubrica.

- Per consentire agli amministratori di ripristinare le impostazioni predefinite del servizio Rubrica.

Lo strumento ABSConfig può essere avviato usando il file ABSConfig. exe. Lo strumento viene aperto nella scheda **configura attributi** . Questa tabella include opzioni per eseguire il mapping degli attributi dei servizi di dominio Active Directory ai campi degli attributi per Skype for Business Server 2015 e per specificare quali utenti includere o escludere nei file del servizio Rubrica in base a specifici filtri di attributi. Include anche opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica. L'opzione **Ripristina predefiniti** consente agli amministratori di ripristinare le impostazioni del servizio Rubrica per i valori predefiniti.

> [!NOTE]
> La rimappatura degli attributi degli annunci in nomi di campi OC diversi può essere eseguita solo per il download di file della Rubrica e non è supportata dalla query Web Rubrica.

### <a name="output"></a>Output

ABSConfig archivia la configurazione del servizio Rubrica nel database.

```PowerShell
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Scopo

ABSConfig offre un modo semplice e rapido per personalizzare il servizio Rubrica di Skype for Business Server 2015.

### <a name="requirements"></a>Requisiti

#### <a name="computer"></a>Computer

ABSConfig può essere eseguito solo da un computer collegato al dominio in cui è installato Skype for Business Server 2015. Nel caso di Skype for Business Server 2015, Enterprise Edition, questo strumento può essere eseguito in qualsiasi server front-end in cui il servizio Rubrica è abilitato durante l'installazione.

#### <a name="network"></a>Rete

Il computer dovrebbe essere in grado di connettersi al pool Front-end e al database back-end.

#### <a name="software"></a>Software

Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:

- Skype for Business Server 2015

#### <a name="users"></a>Utenti

Amministratori che hanno le autorizzazioni necessarie per aggiornare la distribuzione di Skype for Business Server 2015.

### <a name="examples"></a>Esempi

ABSConfig può essere avviato digitando **ABSConfig. exe** al prompt dei comandi. Di seguito è riportata l'interfaccia utente dello strumento ABSConfig.

![Strumento ABSConfig.exe](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Riepilogo

Lo strumento ABSConfig offre agli amministratori uno strumento rapido e facile da usare per personalizzare il servizio Rubrica di Skype for Business Server 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitoraggio del servizio criteri di larghezza di banda
<a name="bpsm"> </a>

Lo strumento Monitoraggio dei servizi per la larghezza di banda è progettato per consentire agli amministratori di visualizzare un elenco delle operazioni seguenti:

1. Tutti i servizi per i criteri di larghezza di banda (autenticazione e Core) configurati in Skype for Business Server 2015 nella topologia

2. Le connessioni che ogni servizio apporta ad altri servizi per i criteri di larghezza di banda e agli Edge Server

3. Tutti i collegamenti configurati nel documento di configurazione della rete e nell'utilizzo della larghezza di banda in tempo reale riportati da ognuno dei servizi per i criteri di larghezza di banda

### <a name="description"></a>Descrizione

Lo strumento Monitoraggio del servizio di Bandwidth Policy viene implementato come applicazione basata su GUI. Gli amministratori avviano lo strumento eseguendo PDPMonUI. exe.

Quando lo strumento viene avviato, cerca di individuare l'elenco dei servizi per i criteri di larghezza di banda nella topologia. Dopo aver completato l'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati per i cluster a cui appartengono.

Quando gli amministratori selezionano un particolare servizio per i criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni relative al particolare servizio. Il riquadro contiene anche due schede principali che visualizzano le informazioni.

#### <a name="machine-info-tab"></a>Scheda info computer

La scheda **info computer** Mostra i dettagli del servizio dei criteri di larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri di larghezza di banda selezionato ad altri servizi.

#### <a name="topology-info-tab"></a>Scheda informazioni topologia

Nella scheda **informazioni topologia** viene visualizzato un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione della rete. Per ogni collegamento viene visualizzata la capacità di larghezza di banda audio e video. Viene inoltre visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità. Lo strumento usa la codifica a colori per evidenziare i collegamenti con l'utilizzo che è vicino alla capacità, che consente agli amministratori di isolare rapidamente tali collegamenti.

> [!NOTE]
>  Se lo strumento Monitoraggio servizi di larghezza di banda non funziona quando si connette a uno dei servizi configurati per i criteri di larghezza di banda, le informazioni nelle schede informazioni **computer** e **informazioni topologia** non verranno popolate. Tuttavia, è possibile che lo strumento possa connettersi inizialmente, ma in seguito perde la connessione al servizio. In questi casi, gli amministratori possono visualizzare informazioni obsolete. È disponibile un **ultimo timestamp aggiornato** in ognuna delle schede che consentono agli amministratori di vedere quando i dati sono stati aggiornati per un particolare servizio per i criteri di larghezza di banda.

### <a name="output"></a>Output

Non è disponibile alcun output della riga di comando; l'output del programma è contenuto nell'interfaccia utente grafica principale (GUI).

### <a name="purpose"></a>Scopo

Lo scopo dello strumento Monitoraggio dei servizi per la larghezza di banda è consentire agli amministratori la visibilità dello stato di ognuno dei servizi per i criteri di larghezza di banda definiti nella topologia. Gli amministratori possono inoltre visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento di configurazione della rete.

### <a name="requirements"></a>Requisiti

Lo strumento Monitoraggio del servizio di Bandwidth Policy deve essere eseguito in un computer che fa parte della topologia di Skype for Business Server.

### <a name="summary"></a>Riepilogo

Lo strumento Monitoraggio dei servizi per la larghezza di banda può essere una risorsa preziosa per gli amministratori in modo che possano ispezionare lo stato di tutti i servizi dei criteri di larghezza di banda nella topologia e, cosa più importante, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definito nelle impostazioni di configurazione della rete.

## <a name="bandwidth-utilization-analyzer"></a>Analizzatore dell'utilizzo della larghezza di banda
<a name="bua"> </a>

L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che crea report su varie visualizzazioni del consumo di larghezza di banda dagli endpoint UC in collegamenti WAN nella rete aziendale. Questi report possono essere usati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità di larghezza di banda.

### <a name="description"></a>Descrizione

L'analizzatore dell'utilizzo della larghezza di banda viene implementato come applicazione basata su GUI. Questo strumento genera report specifici per l'utilizzo dell'audio in tutta la rete e consente la pianificazione della capacità. Viene inoltre iterata sulla capacità di larghezza di banda assegnata a diversi collegamenti.

### <a name="output"></a>Output

L'analizzatore dell'utilizzo della larghezza di banda offre grafici al grafico della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.

### <a name="purpose"></a>Scopo

In qualsiasi distribuzione di voce e video, è fondamentale monitorare e comprendere l'andamento dell'utilizzo della larghezza di banda del traffico multimediale attraverso la rete aziendale. Lo strumento Analizzatore di utilizzo della larghezza di banda consente a un amministratore di raggiungere questo obiettivo. Questo strumento esegue le operazioni seguenti:

- Genera report specifici per l'utilizzo audio in rete

- Facilita la pianificazione e l'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a diversi collegamenti

L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche della capacità e dei report di utilizzo della larghezza di banda; sono i seguenti:

- Tutti i collegamenti WAN nella rete aziendale

- Filtrato da collegamenti WAN selezionati scelti

- Filtrati da collegamenti WAN che hanno superato la capacità di collegamento

- Filtrati da collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning

- Filtrare in base a collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda maggiore di 90% della capacità di larghezza di banda del collegamento WAN)

- Filtrato tramite il tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito

- Filtrata per area di rete

#### <a name="applications"></a>Applicazioni

L'analizzatore dell'utilizzo della larghezza di banda include le due applicazioni seguenti (strumenti):

- **WanLinkLogCollector. exe** questo strumento consente all'utente di immettere le informazioni richieste.

- **BandwidthUtilizationAnalyzer. xlsm** un report del foglio di calcolo di Microsoft Excel viene avviato automaticamente da WanLinkLogCollector. exe. Questa applicazione consente all'utente di applicare filtri al report come illustrato più avanti in questo articolo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fasi dell'uso dell'analizzatore dell'utilizzo della larghezza di banda

Quando si usa l'analizzatore dell'utilizzo della larghezza di banda, esistono due fasi:

- Raccolta di log, eseguita tramite WanLinkLogCollector. exe

- Personalizzare i report, che vengono eseguiti tramite BandwidthUtilizationAnalyzer. xlsm

> [!IMPORTANT]
> Consigliamo vivamente che BandwidthUtilizationAnalyzer. xlsm non venga lanciato manualmente dagli utenti finali.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Avvio dell'analizzatore dell'utilizzo della larghezza di banda

Avviare WanLinkLogCollector. exe al prompt dei comandi o usando Esplora risorse.

 **Uso di WanLinkLogCollector. exe**

Sono disponibili tre passaggi per l'uso di WanLinkLogCollector. exe:

1. **Registrare la sequenza temporale** Specificare la sequenza temporale per la quale deve essere generato il report

2. **Specificare le directory dei file** Specificare le informazioni sulla posizione del file

3. **Raccogliere i registri e avviare il Visualizzatore report** Eseguire il comando per generare il report

#### <a name="step-1---log-the-timeline"></a>Passaggio 1-registrare la sequenza temporale

La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue, come illustrato nella figura seguente.

1. **Data di inizio** Questa è la data di inizio della sequenza temporale a cui deve essere generato il report; ad esempio, 1 agosto 2010.

2. **Data di fine** Questa è la data di fine della sequenza temporale a cui deve essere generato il report; ad esempio, il 30 settembre 2010.

     ![Date di inizio e fine per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Passaggio 2-specificare le directory dei file

Le directory di file seguenti possono essere specificate dall'utente come illustrato.

- **Posizione dei file di log del server** Percorso della cartella in cui sono archiviati i registri del server dei criteri di larghezza di banda. Si \<tratta in genere di\> \\ Fileserver<scelta di\>Fe \AppServerFiles\PDP.

- **Percorso di archiviazione file temporaneo** Percorso del file temporaneo in cui vengono archiviati i file intermedi mentre viene generato il report.

![Directory di file per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

> [!NOTE]
> Verificare che l'accesso a un file sufficiente ai registri del server e alla cartella temporanea dell'archivio file venga fornito all'utente dello strumento.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Passaggio 3-raccogliere i registri e avviare il Visualizzatore report

Per raccogliere i log e avviare il Visualizzatore report, fare clic su **Esegui** come illustrato di seguito. Questo passaggio raccoglie i dati necessari.

![Raccolta dei dati per l'analisi dell'utilizzo della larghezza di banda](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Quando la convalida dell'input è riuscita, viene visualizzato il messaggio mostrato di seguito.

![Notifica della raccolta dei log in Bandwidth Utili](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Fare clic su **OK**. BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente. Seguire le istruzioni nella finestra di messaggio. Per informazioni dettagliate, vedere **uso di BandwidthUtilizationAnalyzer. xlsm** nella sezione successiva.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso di BandwidthUtilizationAnalyzer. xlsm

1. Quando BandwidthUtilizationAnalyzer. xlsm viene avviato automaticamente, fare clic su **Aggiorna** come illustrato di seguito.

     ![BandwidthUtilizationAnalyzer.xlsm](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Quando si apre una cartella di file, selezionare consolidato. csv dalla posizione specificata nella finestra di messaggio, come illustrato di seguito. Viene inoltre visualizzata la posizione come **C:\Temp**.

     ![Apertura di una cartella in Bandwidth Utilization Analyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Fare clic su **Importa**.

4. La trama grafica viene generata automaticamente. È disponibile quando il puntatore di lavoro in background scompare.

     ![Applicazione di filtri nella visualizzazione Report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Applicazione di filtri alla visualizzazione report

I filtri che è possibile applicare alla visualizzazione report come illustrato di seguito sono descritti di seguito:

![Applicazione di filtri nella visualizzazione Report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nome** Filtrare per collegamenti WAN (il filtro si trova sul lato destro del grafico). Il prefisso denota i tipi di collegamento seguenti: vedere la casella verticale (blu):

   - **Sito S** Collegamento WAN da un sito di rete a un'area di rete

   - **È tra siti** Collegamento WAN tra due siti di rete

   - **Inter-area geografica R** Collegamento WAN tra due aree geografiche di rete

2. **Limite superato** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è maggiore della capacità di larghezza di banda

3. **Livelli critici** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto 90% o più della capacità di larghezza di banda

4. **Sottoutilizzati** Filtrare per collegamenti WAN il cui utilizzo della larghezza di banda è inferiore al 25% della capacità di larghezza di banda

5. **Tipo di collegamento** Filtrare in base ai tipi di collegamenti WAN seguenti:

   - Tipo di **sito di rete**

   - Tipo **inter-sito**

   - Tipo **di collegamento tra aree** geografiche

6. **Area geografica** Filtrare per area di rete

Le figure seguenti mostrano i filtri descritti in precedenza.

Filtrare in base al **nome**. Selezionare l'elenco di collegamenti che devono essere visualizzati nel grafico.

![Filtro per nome in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtrare in base al **limite superato**. Selezionare **true** per applicare il filtro.

![Filtro per Exceeded Limit.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrare in base a **livelli critici**. Selezionare **true** per applicare il filtro.

![Filtro per Critical Levels.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrare in **base a usato**. Selezionare **true** per applicare il filtro.

![Filtro per Under Utilized.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtra per **tipo di collegamento**. Selezionare il tipo o i tipi che devono essere visualizzati.

![Filtro per Link Type.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrare per **area geografica**. Selezionare un elenco di aree di cui devono essere visualizzati i collegamenti.

![Filtro per Region.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisiti

- .NET Framework 3,5

- Microsoft Excel 2010 o Excel 2007

### <a name="summary"></a>Riepilogo

L'analizzatore dell'utilizzo della larghezza di banda viene usato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC attraverso la rete. Questo strumento può essere usato per segnalare l'utilizzo della larghezza di banda video anche nella rete.

## <a name="call-parkometer"></a>Chiama Parkometer
<a name="callpark"> </a>

Call Parkometer è un'applicazione della riga di comando che consente di accedere facilmente al database Orbit di Call Park.

### <a name="description"></a>Descrizione

Chiamata Parkometer è uno strumento per tenere traccia delle chiamate parcheggiate attualmente. Raccoglie anche statistiche sulle orbite e sull'utilizzo di Call Park Server (CPS). Questo strumento della riga di comando offre sia la lettura che l'accesso in scrittura al database di SQL Server Orbit di CPS da un computer locale o connesso in remoto.

Tutte le opzioni si escludono a vicenda. La sintassi della riga di comando è la seguente:

- **-o** parameter: elenca tutti gli intervalli di Orbit configurati per questo pool.

- **-n** parameter: elenca tutte le orbite attualmente usate in questo pool. Le informazioni visualizzate sono le seguenti:

  - URI (Uniform Resource Identifier) SIP di Parkee e Parker.

  - Nome host del CPS in cui è parcheggiata la chiamata.

  - Indicatore di data e ora di quando la chiamata è stata parcheggiata.

- **-parametro f** : elenca il numero di orbite attualmente libere nel pool.

- **-r \<n\> ** Parameter-elenca le \<n\> ultime chiamate parcheggiate. Le informazioni visualizzate sono le seguenti:

  - URI SIP di Parkee.

  - URI SIP di Parker.

  - Nome host del CPS in cui è stata parcheggiata la chiamata.

  - Indicatore di data e ora di quando la chiamata è stata recuperata o eliminata.

- **-parametro\<t\> n** -test che riservano un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.

### <a name="output"></a>Output

In base ai parametri di input specificati al prompt dei comandi, chiama Parkometer Visualizza l'output seguente:

- Tutti gli intervalli di orbita configurati per il pool

- Chiamate attualmente parcheggiate

- Numero di orbite libere (disponibili)

- Chiamate parcheggiate di recente

- Orbite riservate per testare i valori dell'orbita uniforme e casuale

### <a name="purpose"></a>Scopo

Lo scopo dello strumento CPS è quello di consentire l'accesso della riga di comando al database CPS. L'amministratore può visualizzare l'utilizzo di CPS e determinare il numero di orbite assegnate a un pool.

### <a name="requirements"></a>Requisiti

Se questo strumento viene eseguito nello stesso computer in cui è in esecuzione CPS, non sono previsti requisiti. Se questo strumento viene eseguito in un computer remoto, il database di SQL Server usato da Skype for Business Server 2015 deve essere configurato per consentire l'accesso remoto. La chiamata di Parkometer deve essere configurata con una stringa di connessione al database di SQL Server per connettersi al server SQL del pool. Questa stringa di connessione al database di SQL Server è definita nel file di configurazione **parkometer. exe. config**. Deve essere posizionato nella stessa directory in cui si trova parkometer. exe. Il file XML seguente è un esempio di parkometer. exe. config. I parametri che devono essere configurati sono nome utente (ad esempio, mydomain\Administrator), password (ad esempio, password) e nome host, ad esempio myserver.

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

### <a name="examples"></a>Esempi

Intervalli di Orbit distribuiti: il parametro-o elenca tutti gli intervalli di orbita configurati per il pool come illustrato

![Intervalli dei codici orbit in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Chiamate attualmente parcheggiate: il parametro-n elenca tutte le orbite attualmente usate in questo pool come illustrato

![Chiamate attualmente parcheggiate in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Numero di orbite gratuite: il parametro-f elenca il numero di orbite attualmente libere nel pool come illustrato

![Codici orbit liberi in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Chiamate parcheggiate di recente: il parametro \<-\> r n elenca \<le\> n ultime chiamate parcheggiate come illustrato

![Chiamate parcheggiate di recente in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Verifica prenotazione in orbita: i test \<dei\> parametri-t n riservano un'orbita nel database come illustrato

![Prenotazione codici orbit di test in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Riepilogo

Call Parkometer è uno strumento della riga di comando che fornisce informazioni dettagliate sul server di Call Park.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descrizione

DBAnalyze è uno strumento della riga di comando che consente agli amministratori di raccogliere report di analisi sui database di Skype for Business Server 2015. DBAnalyze ha le modalità seguenti: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:

- **Modalità diagnostica** Crea un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati, e le dimensioni degli indici), le dimensioni dei file di dati e di log, l'ultima ora di backup, la distribuzione di contatti tra server che esegue Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, abbonamenti, pubblicazioni, endpoint per utente, eventuali utenti non correttamente ospitati, utenti non instradati, il numero medio di conferenze organizzate per utente e la versione del database.

    > [!NOTE]
    > L'esecuzione della modalità diagnostica può influire sulle prestazioni del server.

- **Modalità dati utente** Segnala i dati relativi a contatti, contenitori, abbonamenti, pubblicazioni, autorizzazioni e gruppi di contatti per un utente specificato o per gli utenti che hanno tale utente negli elenchi contatti e autorizzazioni. Questa modalità riporta anche i dati di riepilogo per le conferenze a cui un utente organizza o è invitato.

- **Modalità conferenza** Riporta i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli relativi alla programmazione per la conferenza, l'elenco di invitati, l'elenco dei tipi di elementi multimediali consentiti per la conferenza, i MCU attivi (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.

- **Decodificare l'ID riunione** Decodifica un ID riunione PSTN (Public Switched Telephone Network) specificato dall'opzione **/pstnid** ma non si connette al back-end per informazioni dettagliate.

- **Risoluzione conferenza** Decodifica un ID riunione PSTN specificato dall'opzione **/pstnid** e visualizza le informazioni sulla Conferenza indicata dall'ID.

- **Modalità MCU** Riporta l'ID, il tipo di elemento multimediale, l'URL, lo stato di heartbeat, il carico delle conferenze e il carico dei partecipanti per ogni MCU nel pool.

- **Modalità di frammentazione del disco** Visualizza lo stato di frammentazione di tutti i dischi.

Questo strumento può essere usato per diagnosticare vari problemi o per aiutare gli amministratori con la pianificazione della capacità. Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie utenti ospitati nel server B come contatti, l'amministratore può trasferire gli utenti nel server a nel server B per ridurre il traffico tra server.

### <a name="output"></a>Output

Questo strumento restituisce i report predefiniti relativi al database di Skype for Business Server 2015. **Percorso**:%ProgramFiles%\Skype for Business Server 2015 \ reskit

### <a name="purpose"></a>Scopo

Per installare Dbanalyze. exe, copiarlo in una cartella locale e quindi eseguire lo strumento. Per usare lo strumento, eseguire il comando seguente dalla riga di comando. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]`Di seguito sono elencate le descrizioni delle opzioni della riga di comando.

![Opzioni della riga di comando per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisiti

 **Computer** DBAnalyze può essere eseguito solo da un computer collegato al dominio in cui è installato Skype for Business Server 2015.

 **Rete** Il computer dovrebbe essere in grado di connettersi al database back-end.

 **Software** I componenti software di Skype for Business Server 2015 devono essere installati prima di eseguire DBAnalyze.

 **Utenti** La tabella seguente Mostra gli amministratori che hanno le autorizzazioni necessarie per accedere ai database di Skype for Business Server 2015.

![Tabella di autorizzazioni per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> È necessario un account di amministratore locale per **/report: modalità disco** .

### <a name="examples"></a>Esempi

Di seguito sono riportati alcuni esempi di comandi Dbanalyze. exe validi:

```
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Riepilogo

DBAnalyzer consente agli amministratori di analizzare in modo rapido e semplice i database di Skype for Business Server 2015.

## <a name="import-storage-service-data"></a>Importare i dati del servizio di archiviazione
<a name="Issd"> </a>

Lo strumento ImportStorageServiceData Resource Kit consente di riimportare i dati di Accodamento e endpoint che sono stati svuotati dal servizio di archiviazione (LYSS) di nuovo nel servizio di archiviazione.

### <a name="description"></a>Descrizione

I dati svuotati del servizio di archiviazione avrebbero potuto essere automatici (periodici) in base allo stato dell'elemento della coda o alle dimensioni del database. Potrebbe essere accaduto a causa della chiamata manuale del cmdlet di failover del pool o del cmdlet StorageServiceFullFlush (che richiama il cmdlet di failover del pool). Tieni presente che i dati non devono essere reimportati idealmente se una delle dimensioni del database del servizio di archiviazione (LYSS) nei Front Ends è superiore al livello normale, perché in questo modo probabilmente causerà l'esportazione di più dati. Inoltre, gli eventuali problemi che potrebbero avere contribuito agli errori che hanno causato l'aumento della coda del servizio di archiviazione devono essere risolti prima di tutto, ad esempio gli errori degli endpoint di Exchange, i problemi di rete o altri problemi.

 **Scenario 1:** durante il failover del pool, i file possono essere svuotati dal servizio di archiviazione per ogni front-end. Dopo aver completato il failover, lo strumento deve essere eseguito per reimportare i dati.

 **Scenario 2:** i dati vengono svuotati automaticamente ogni giorno o in risposta al database del servizio di archiviazione che supera determinate soglie di dimensione (ad esempio 60%, 80%, 90% Full). I dati scaricati automaticamente devono essere reimportati di routine dall'amministratore. Nella situazione precedente, se il monitoraggio SCOM Pack non è distribuito, esistono eventi per il servizio di archiviazione di Skype for Business Server relativo ai dati da svuotare dal servizio di archiviazione. ID evento di 32075 (operazione di svuotamento completo), 32076 (il colore completo è completato), 32082 (livello di manutenzione a filo iniziato), 32083 (livello di manutenzione), 32089 (lo svuotamento si è verificato a causa del riempimento del database). Nota Questi ID evento corrispondono alla versione RTM. Quando un amministratore vede questi eventi, significa che ci sono file che sono stati svuotati. Questi dati devono essere di routine importati di nuovo usando questo strumento, ad esempio una volta alla settimana.

Per la versione del servizio online, se è distribuito SCOM Pack per Skype for Business Server, è possibile che vengano generati nuovi avvisi che chiedono all'amministratore di reimportare nuovamente i dati svuotati in un servizio di archiviazione. Verrà visualizzato un evento corrispondente nel log eventi del server front-end che ha attivato l'avviso. L'evento darà una descrizione del percorso padre in cui si trovano i file di dati svuotati, nonché il numero di file che soddisfano i criteri di avviso. I criteri di avviso sono che ci sono X o più file sotto il percorso padre specifico che hanno almeno Y giorni prima (dove X e Y sono preimpostati all'interno del StorageService ma possono essere ignorati modificando il file APPCONFIG). Di seguito sono illustrati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che è il percorso padre. Una possibilità è in condivisione file del servizio Web, mentre l'altra possibilità è la directory dei dati dell'applicazione locale di ogni front-end. ad esempio c:\ProgramData\Microsoft\Skype for Business Server 2015 \ StorageService). L'amministratore eseguirà quindi questo strumento di reskit.

Questo strumento incrementerà il carico di CPU e IO nella parte anteriore in cui è in esecuzione, oltre ad altri front ends, nella situazione in cui i dati non sono di proprietà del front-end in cui viene eseguito lo strumento. Ti consigliamo di Runng questo strumento quando i Front ends non sono sotto il carico di CPU e IO elevato, ad esempio al di fuori delle ore di punta. In secondo luogo, questo strumento può eseguire da 2 a 3 minuti per importare un file di dati. Tieni presente quando valuti quanto tempo verrà eseguito lo strumento. Il file di log dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file. Eliminarlo se non sono stati segnalati errori, perché il file di log può essere di decine di MB o più.

![Esempio di eventi nel registro eventi del server di archiviazione.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di Skype for Business Server 2015. Lo strumento viene eseguito su computer Uniti a un dominio in cui sono installati Skype for Business Server e Skype for Business Server Management Shell. Lo strumento usa un cmdlet di Management Shell per identificare tutti i server front-end nel pool. In secondo luogo, lo strumento deve essere eseguito da un computer nel pool in cui è installato il database **RtcLocal** . Questo database viene usato dallo strumento per recuperare la posizione della condivisione di file WEBSERVICE per il pool. Inoltre, prima di usare lo strumento, ogni server front-end deve prima consentire la comunicazione remota di Windows PowerShell tramite **Enable-PSRemoting** su ogni server front-end e il computer da cui viene eseguito lo strumento. In caso contrario, i comandi remoti di Windows PowerShell da questo strumento avranno esito negativo. La comunicazione remota di Windows PowerShell può essere disattivata in tutti i server front-end nel pool al termine dell'operazione. Infine, l'account o le credenziali che richiamano lo strumento devono avere l'autorizzazione di lettura/scrittura per la condivisione di file WebService per il pool in cui eseguono questo strumento. In caso contrario, lo strumento non riuscirà con gli errori di autorizzazione IO.

> [!NOTE]
> In Windows Server 2012 la comunicazione remota di Windows PowerShell è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.

### <a name="examples"></a>Esempi

```
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
```

## <a name="lcssync"></a>LCSSync
<a name="LCSSync"> </a>

Lo strumento LCSSync consente di distribuire il software di comunicazione di Skype for Business Server 2015 in un ambiente con più foreste. Questo strumento viene usato per sincronizzare utenti e gruppi di foreste di utenti diversi come un oggetto contatto di servizi di dominio Active Directory in una foresta centrale in cui è installato Skype for Business Server 2015.

### <a name="description"></a>Descrizione

 LCSSync usa gli oggetti contatto di servizi di dominio Active Directory sincronizzati nella foresta centrale per consentire agli utenti di Skype for Business Server. Per specificare Single Sign-in, l'account utente principale deve essere mappato all'oggetto contatto Active Directory Domain Services nella foresta centrale per Skype for Business Server 2015. Questo strumento consente di eseguire tale mapping. Questo strumento include modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.

### <a name="summary"></a>Riepilogo

Lo strumento LCSSync consente di distribuire Skype for Business Server 2015 in un ambiente con più insiemi di strutture.

## <a name="lookup-user-console"></a>Console utente di ricerca
<a name="LUC"> </a>

Lo strumento LookupUserConsole Visualizza le informazioni di routing interne di Skype for Business Server su utenti specifici. Queste informazioni possono essere utili per il supporto Microsoft personale per la diagnosi dei problemi di distribuzione e routing.

### <a name="description"></a>Descrizione

 L'esecuzione di LookupUserConsole. exe apre un prompt dei comandi che accetta gli indirizzi SIP e cerca di visualizzare le informazioni di routing interne di Skype for Business Server. Digitare **Exit** per chiudere lo strumento LookupUserConsole.

### <a name="requirements"></a>Requisiti

Installare il Resource Kit di Skype for Business Server 2015. Lo strumento viene eseguito su computer Uniti a un dominio in cui è installato Skype for Business Server.

### <a name="examples"></a>Esempi

C: Skype for Business Server 2015 \ reskit\>LookupUserConsole. exe

```
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
```

## <a name="msturnping"></a>MsTurnPing
<a name="MsTurnPing"> </a>

Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che gestiscono i servizi di autenticazione audio/video e di video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.

### <a name="description"></a>Descrizione

Lo strumento MSTurnPing consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di controllare lo stato dei server che gestiscono i servizi di autenticazione audio/video e di video, nonché i server che gestiscono i servizi per i criteri di larghezza di banda nella topologia.

Lo strumento consente all'amministratore di eseguire i test seguenti:

1. Test a/V Edge Server: lo strumento esegue i test su tutti i/V Edge Server della topologia eseguendo le operazioni seguenti:

   - Verificare che il servizio di autenticazione audio/video di Skype for Business Server sia avviato e possa emettere le credenziali appropriate.

   - Verificare che il servizio Edge audio/video di Skype for Business Server sia stato avviato e che sia possibile allocare le risorse sul bordo esterno con successo.

2. Test del servizio criteri di larghezza di banda: lo strumento esegue i test in tutti i server che eseguono i servizi per i criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:

   - Verificare che il servizio di gestione della larghezza di banda (autenticazione) di Skype for Business Server sia avviato e possa emettere le credenziali appropriate.

   - Verificare che il servizio di gestione della larghezza di banda (Core) di Skype for Business Server sia stato avviato e possa eseguire correttamente il controllo della larghezza di banda.

Questo strumento deve essere eseguito da un computer che fa parte della topologia e ha installato lo Store locale.

### <a name="output"></a>Output

Lo strumento restituisce i risultati di ogni operazione.

- Se viene eseguito il test **AudioVideoEdgeServer** , gli output degli strumenti sono i seguenti:

  - I risultati del test dei computer che includono il servizio di autenticazione audio/video di Skype for Business Server 2015 nella topologia

  - I risultati del test dei computer che prevedono il servizio Edge audio/video di Skype for Business Server 2015 nella topologia

- Se viene eseguito il test **BandwidthPolicyServer** , gli output degli strumenti sono i seguenti:

  - I risultati del test dei computer che includono il servizio di gestione dei criteri di larghezza di banda di Skype for Business Server 2015 (autenticazione) nella topologia

  - I risultati del test dei computer che includono il servizio di gestione dei criteri di larghezza di banda di Skype for Business Server 2015 (Core) nella topologia

### <a name="requirements"></a>Requisiti

- Questo strumento deve essere eseguito da un computer che si trova nella topologia e che contiene lo Store locale.

- Lo strumento deve essere eseguito come amministratore che ha accesso allo Store locale.

### <a name="examples"></a>Esempi

Di seguito è riportato un esempio di input dello strumento.

```
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che vogliono controllare lo stato dei server in cui sono in uso servizi per i criteri di larghezza di banda e audio/video.

## <a name="network-configuration-viewer"></a>Visualizzatore Configurazione di rete
<a name="NCV"> </a>

Il Visualizzatore di configurazione di rete può essere usato dagli amministratori del software di comunicazione di Skype for Business Server 2015 per visualizzare la topologia di rete di controllo di ammissione di chiamata (CAC) per un'organizzazione che ha eseguito il provisioning per consentire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o video in base alla capacità di larghezza di banda specificata. Gli amministratori di Skype for Business Server 2015 definiscono i criteri di CAC, applicati dai servizi per i criteri di larghezza di banda installati con Skype for Business Server 2015.

### <a name="description"></a>Descrizione

Network Configuration Viewer (NetworkConfigurationViewer. exe) consente agli amministratori di eseguire le attività seguenti:

- Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business Server 2015 in formato grafico.

- Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico.

- Salvare e archiviare la topologia di rete CAC in un formato XML sul disco.

- Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP.

- Visualizzare i dati di configurazione della topologia di rete CAC.

- Visualizzare la topologia di rete CAC in uno stile di visualizzazione albero.

- Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area geografica, da area geografica e da sito a sito.

- Visualizzare le informazioni sul sito della topologia di rete CAC, le informazioni sulle aree geografiche e i collegamenti di rete con provisioning.

### <a name="purpose"></a>Scopo

Visualizzare i collegamenti della topologia di rete Enterprise CAC in un'interfaccia grafica.

### <a name="examples"></a>Esempi

 **Caricare e visualizzare la topologia di rete CAC da una distribuzione di Skype for Business server 2015 in un formato grafico**: gli amministratori di Skype for business server 2015 possono caricare e visualizzare la configurazione della topologia di rete di CAC in qualsiasi computer Skype for business server 2015 usando l'opzione di **configurazione della rete download** , come illustrato nella figura seguente. Lo strumento non riesce a scaricare o visualizzare tale configurazione quando viene distribuita in un computer che non ha connettività con lo Store di configurazione di Skype for Business Server 2015.

![Download della configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Caricare e visualizzare la topologia di rete CAC da un file di log del server dei criteri di larghezza di banda in formato grafico:** I server dei criteri di larghezza di banda di Skype for Business Server 2015 salvano la topologia di rete CAC come parte del meccanismo di registrazione nella posizione di condivisione file di Skype for Business Server 2015. Skype for Business Server 2015 gli amministratori possono visualizzare un file in formato grafico usando l'opzione di **configurazione della rete aperta** , come illustrato di seguito.

![Apertura di un file di log del server criteri larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Salvare e archiviare la topologia di rete CAC in un formato XML sul disco: Skype for Business Server 2015 gli amministratori possono salvare il file di configurazione della topologia di rete CAC in un formato XML usando l'opzione **Salva una copia di configurazione di rete** , come illustrato di seguito. Il file di configurazione salvato può quindi essere usato offline per scopi di visualizzazione grafica.

![Salvataggio della configurazione di rete come file XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Salvare e archiviare il diagramma della topologia di rete in formato JPG o BMP: Skype for Business Server 2015 gli amministratori possono salvare la configurazione della topologia di rete CAC in un formato grafico (formati di file JPG e BMP) usando l'opzione **Salva diagramma configurazione di rete come immagine** come illustrato di seguito.

![Salvataggio della configurazione di rete come immagine.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Visualizzare i dati di configurazione della topologia di rete CAC:</strong> Skype for Business Server 2015 gli amministratori possono visualizzare i dati di configurazione della rete correlati, ad esempio aree di rete, siti di rete, profili di larghezza di banda e indirizzi IP della subnet del sito in un formato testuale usando l'opzione Visualizza dati di configurazione della rete come illustrato di seguito.

![Visualizzazione dei dati sulla configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Visualizzare la topologia di rete CAC in uno stile di visualizzazione ad albero:** Skype for Business Server 2015 gli amministratori possono visualizzare i dati di configurazione della rete correlati in uno stile di visualizzazione ad albero grafico usando il pannello di controllo sul lato sinistro della finestra degli strumenti, come illustrato di seguito.

![Visualizzazione dei dati sulla configurazione di rete in una visualizzazione ad albero.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definire connettori personalizzati per i collegamenti alla topologia di rete CAC, ad esempio i collegamenti da sito a area** geografica, dall'area geografica e da sito a sito: Skype for Business Server 2015 gli amministratori possono definire connettori grafici personalizzati per i collegamenti WAN della configurazione di rete CAC usando l'opzione impostazioni come illustrato di seguito. Questo consente di distinguere tra i vari tipi di collegamenti di rete che vengono provisionati nella configurazione di rete.

![Strumenti](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Visualizzare informazioni sul sito della topologia di rete CAC, informazioni sulle aree geografiche e criteri di larghezza di banda provisioning:** Gli amministratori di Skype for Business Server 2015 possono visualizzare informazioni relative all'area di rete CAC correlate, informazioni sul sito e informazioni sul provisioning della larghezza di banda di CAC usando le opzioni illustrate di seguito. Ad esempio, fare clic su **informazioni** in un'area di rete o in un oggetto sito di rete.

![Definizione di connettori personalizzati per la rete.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per gli amministratori di Skype for Business Server 2015 che desiderano visualizzare la topologia di rete CAC per la distribuzione in un formato grafico.

## <a name="response-group-agent-live"></a>Agente di Response Group Live
<a name="RGAL"> </a>

L'applicazione Response Group offre agli agenti la possibilità di accedere a informazioni in tempo reale utili usando il servizio Web incorporato. Sfortunatamente, nessuna visualizzazione grafica di questi dati è disponibile all'esterno dell'applicazione. Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo un modo semplice e grafico per accedere a queste informazioni, migliorate con le informazioni del software Skype for Business Communications in tempo reale, come la presenza di altri agenti.

### <a name="description"></a>Descrizione

Response Group Agent Live è un'applicazione Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale, ad esempio l'appartenenza al gruppo e il numero corrente di chiamate, agli agenti del gruppo di risposta. Si tratta di una versione avanzata della pagina gruppi di agenti (accessibile da Skype for business.

### <a name="purpose"></a>Scopo

L'applicazione Response Group Accoda le chiamate in arrivo e le instrada ai gruppi di agenti. Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere a informazioni in tempo reale sui gruppi di agenti, ad esempio gli altri agenti disponibili e il numero di chiamate in attesa in ogni coda. Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono messe a disposizione in modo intuitivo dall'agente di Response Group Live.

#### <a name="features"></a>Caratteristiche

Lo strumento di Response Group Agent Live è basato sul servizio Response Group e su Skype for Business Server 2015 SDK. Fornisce agli agenti del gruppo di risposta le informazioni e le funzionalità disponibili nel servizio Response Group, ad esempio l'appartenenza ai gruppi, la presenza di altri agenti e il numero di chiamate in attesa.

La figura seguente illustra l'interfaccia principale di Response Group Agent Live.

![Strumento Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Le tre caratteristiche principali seguenti sono disponibili per gli agenti in Response Group Agent Live:

- **Accesso/uscita:** Contrariamente alla pagina gruppi di agenti (accessibile da Skype for Business Server 2015), Response Group Agent Live consente solo agli agenti di accedere o disconnettersi da tutti i gruppi di agenti contemporaneamente. Questa applicazione offre tre modi rapidi per l'accesso o la disconnessione degli agenti:

  - Fare clic sui pulsanti di accesso/uscita (verde e rosso) all'interno dell'applicazione.

  - Fare clic con il pulsante destro del mouse sull'icona della barra di sistema e scegliere Accedi o Disconnetti.

  - Uso delle scelte rapide da tastiera configurabili.

- **Appartenenza al gruppo:** Quando viene selezionato un gruppo di agenti, il gruppo di risposte in Live Visualizza l'elenco di agenti in questo gruppo nel riquadro destro. Se Skype for Business Server 2015 è in uso nello stesso computer di questa applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate nell'agente di Response Group Live. Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da lì.

- **Statistiche in tempo reale:** Response Group Agent Live offre statistiche in tempo reale per tutti i gruppi di agenti. La frequenza di aggiornamento è di un minuto. Quando una chiamata viene risolta da un gruppo di risposte, accanto al nome del gruppo viene aggiunto un indicatore visivo con il numero corrente di chiamate in coda. Se si sospende il puntatore del mouse su un gruppo, viene visualizzato anche il tempo di attesa più lungo.

### <a name="requirements"></a>Requisiti

L'agente di Response Group Live richiede .NET Framework 4,0. Inoltre, per sfruttare le caratteristiche della presenza e della scheda contatto, Skype for business deve essere installato localmente (ed essere in funzione).

#### <a name="configuration"></a>Configurazione

Response Group Agent Live può essere personalizzato per le singole preferenze usando la finestra di dialogo Opzioni nell'applicazione. Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive. exe. config.

Nella figura seguente è illustrata la finestra di dialogo Opzioni che gli agenti possono usare per configurare l'indirizzo host e i tasti di scelta rapida. Per accedere a questa finestra di dialogo, fare clic sul pulsante Opzioni nell'angolo in alto a destra dell'interfaccia principale.

![Finestra di dialogo Options di Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Le tre diverse impostazioni seguenti possono essere personalizzate nella configurazione Live dell'agente di Response Group:

- Indirizzo host: in genere è il nome di dominio completo del pool Web che appartiene al pool di Home dell'agente. L'indirizzo esatto del servizio Response Group viene automaticamente derivato in background da queste informazioni (accodando il percorso corretto dopo l'host).

- Scelte rapide: i collegamenti esatti per l'accesso/uscita possono essere personalizzati. L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere la chiave "Windows logo" (oltre ad almeno un altro tasto).

- Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.

### <a name="examples"></a>Esempi

La figura seguente illustra come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.

![Esecuzione di una chiamata o invio di un messaggio istantaneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

Nella figura seguente viene illustrato il modo in cui l'agente di Response Group Live Visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte le chiamate in arrivo.

![Visualizzazione di informazioni sulla coda.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Riepilogo

L'accesso rapido e la disconnessione, l'appartenenza ai gruppi e le statistiche di base in tempo reale sono interessanti funzionalità dell'agente di Response Group che sono disponibili solo all'esterno dell'applicazione dal servizio Response Group. Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Skype for Business Server 2015 possono consentire agli agenti di usare un'applicazione Windows che consente loro di eseguire attività in modo più rapido e grafico.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (attivazione delle funzionalità di estensione secondaria) è uno strumento della riga di comando che consente agli amministratori del software di comunicazione di Skype for Business Server 2015 e agli agenti dell'helpdesk di configurare le chiamate Delegate, l'inoltro di chiamata, lo squillo simultaneo impostazioni di chiamata del team e raccolta di chiamate di gruppo per conto di un utente di Skype for Business Server 2015. Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro di chiamata o di squillare contemporaneamente per conto dell'utente. L'amministratore può specificare la destinazione (sotto forma di URI SIP) o usare una destinazione già pubblicata dall'utente. Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere delegati o membri del gruppo di chiamate del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0 e richiede che gli amministratori creino un'applicazione attendibile nell'Central Management store per SEFAUtil.

SEFAUtil (attivazione delle funzionalità di estensione secondaria) consente agli amministratori e agli agenti di helpdesk di Skype for Business Server 2015 di configurare le chiamate Delegate, l'inoltro di chiamata, lo squillo simultaneo, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di Skype per gli utenti di Business Server 2015. Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente.

### <a name="description"></a>Descrizione

La versione corrente di SEFAUtil è solo uno strumento della riga di comando. non è disponibile un'interfaccia utente grafica di supporto. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3,0. Le funzionalità di questo strumento consentono agli amministratori e agli agenti helpdesk di eseguire le operazioni seguenti:

- Visualizzare tutte le impostazioni di routing delle chiamate per un utente (include l'inoltro di chiamata, la delega, lo squillo simultaneo, la chiamata in team e il pick-up di gruppo)

- Abilitare/disabilitare/modificare l'impostazione di inoltro di chiamata (include la destinazione e il timer senza risposta)

- Abilitare/disabilitare/modificare le configurazioni immediate dell'inoltro di chiamata

- Abilitare/disabilitare/modificare le impostazioni di delega

- Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamate team

    > [!NOTE]
    > Nuovo strumento di SEFAUtil di Skype for Business Server 2015

- Abilitare/disabilitare/modificare le impostazioni di chiamata simultanea (include la destinazione)

    > [!NOTE]
    > Nuovo strumento di SEFAUtil di Skype for Business Server 2015

- Abilitare/disabilitare/modificare le impostazioni di raccolta delle chiamate di gruppo

    > [!CAUTION]
    > Nuovo strumento di SEFAUtil di Skype for Business Server 2015

Questo strumento presenta le limitazioni seguenti:

- Supportato solo per gli utenti ospitati in un pool di Skype for Business Server

- La modifica in blocco delle impostazioni di routing delle chiamate per diversi utenti non è supportata

### <a name="output"></a>Output

La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi. Per informazioni dettagliate, vedere la sezione esempi più avanti in questo documento.

### <a name="purpose"></a>Scopo

Di seguito sono riportati alcuni degli scenari principali in cui può essere usato questo strumento:

- Roberto è un dirigente ed è stato spostato in Skype for Business Server per la telefonia. Ha delegazioni nel sistema PBX esistente. Come parte del passaggio a Skype for Business Server 2015, l'amministratore è in grado di configurare il routing di Roberto per riflettere la configurazione di delega preesistente.

- Alice è in viaggio e si rende conto che si aspetta una chiamata importante da uno dei suoi clienti. Tuttavia, si trova in un hotel e non ha accesso a un computer. Chiama l'helpdesk e chiede di inoltrare al numero di cellulare tutte le chiamate effettuate al suo numero di lavoro. Il personale dell'helpdesk è in grado di eseguire la configurazione per suo conto.

- Le chiamate di Joe al suo numero di lavoro andranno alla segreteria telefonica per dispositivi mobili ogni volta che è al lavoro; Tuttavia, le cose sembrano funzionare correttamente nella maggior parte degli altri percorsi. Il tecnico dell'helpdesk è in grado di visualizzare la configurazione di routing di Joe e rileva che Joe ha squillato simultaneamente configurato per il cellulare. Il tecnico chiede a Joe della copertura per dispositivi mobili presso il suo ufficio ed è in grado di determinare che la regola di chiamata simultanea è ciò che causa le chiamate per accedere alla segreteria telefonica di Joe quando la sua copertura di rete è scadente.

- Mike è un nuovo dipendente di Contoso e si unisce a un nuovo team in cui tutti i membri sono configurati per la chiamata del team, quando viene abilitato per Skype for Business Server 2015, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate del team per includere tutti i nuovi membri del team l'amministratore aggiunge inoltre Mike come membro del gruppo di chiamate team per ognuno dei membri del team.

- Una pratica di servizio al cliente nel reparto risorse umane di Contoso consiste nel prestare un servizio personalizzato per tutti i chiamanti dopo la prima chiamata. Considerato che tutti i membri del dipartimento si siedono molto vicini l'uno all'altro, è molto fastidioso per il team avere tutti i telefoni che squillano contemporaneamente alla chiamata del team. Per garantire un servizio ottimale senza interrompere i membri del team, l'amministratore di Skype for Business Server 2015 sfrutta la funzionalità di raccolta delle chiamate di gruppo. L'amministratore aggiunge tutti i membri del reparto a un gruppo di raccolta e comunica al reparto il numero del gruppo di pick-up. Quando Samantha è assente dalla sua scrivania, Joe nota che squilla il telefono e procede a rispondere alla chiamata dalla sua scrivania.

### <a name="requirements"></a>Requisiti

Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile. UCMA 3,0 deve essere installato nel computer in cui si trova. Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID applicazione SEFAUtil in tale pool.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil

1. Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile. Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere eseguita tramite Skype for Business Server Management Shell con il cmdlet seguente:

   ```PowerShell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3,0 deve essere installato in qualsiasi computer che verrà usato per eseguire lo strumento SEFAUtil.

2. Un'applicazione attendibile deve essere definita nella topologia dello strumento SEFAUtil. Per definire SEFAUtil come nuova applicazione attendibile, usare Skype for Business Server Management Shell ed eseguire il cmdlet seguente:

   ```PowerShell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Se necessario, è possibile usare una porta diversa.
    
    > [!NOTE]
    > FQDN del pool: il nome di dominio completo del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un server front-end di Skype for business > o pool).
    > FQDN del registrar del pool: il nome di dominio completo del server front end o del pool di Skype for business associato al pool di applicazioni.
    > Sito del pool: ID sito del sito in cui è ospitato questo pool.

3. Le modifiche della topologia devono essere abilitate. L'attivazione delle modifiche della topologia può essere eseguita tramite Skype for Business Server Management Shell eseguendo il cmdlet seguente:

   ```PowerShell
   Enable-CsToplogy
   ```

4. Se necessario, installare gli strumenti di Skype for Business Server 2015 Resource Kit nel server che verrà usato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibili).

5. Verificare che SEFAUtil sia in corso correttamente. A questo scopo, Esegui lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. Per impostazione predefinita, lo strumento si trova in: ". ..\Program Skype for Business Server 2015 \ reskit". Per visualizzare le impostazioni di inoltro di chiamata di un utente, usare il comando seguente:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Devono essere visualizzate le impostazioni di inoltro di chiamata dell'utente.

#### <a name="group-call-pickup"></a>Risposta alle chiamate di gruppo

Il pick-up per le chiamate di gruppo richiede una configurazione aggiuntiva in Skype for Business Server 2015 per consentire la completa abilitazione della funzionalità. Prima di assegnare gruppi di prelievo agli utenti, vedere la documentazione del prodotto pick-up per la pianificazione e la distribuzione di questa funzionalità.

### <a name="examples"></a>Esempi

#### <a name="display-current-call-handling-settings"></a>Visualizzare le impostazioni di gestione delle chiamate correnti

Il comando seguente Visualizza la gestione delle chiamate per l'utente.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> Questo esempio usa l'opzione **/Server** per specificare il server Skype for business a cui connettersi.

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Impostare la destinazione di chiamata inoltra/nessuna risposta

Questo esempio imposta la destinazione per la chiamata in avanti/nessuna risposta e il ritardo della suoneria. In questo caso, l'opzione/server non è disponibile; SEFAUtil tenta di individuare l'individuazione automatica di Skype for Business Server 2015.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+1425555 0126@contoso.com;user=phone
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Abilitare l'inoltro di chiamata immediatamente

Questo esempio consente immediatamente l'inoltro di chiamata a un altro utente.

```
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Disabilitare immediatamente l'inoltro di chiamata

Questo esempio disattiva immediatamente l'inoltro di chiamata.

```
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com  /disablefwdimmediate
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Aggiungere un utente come delegato e configurare lo squillo simultaneo dei delegati

In questo esempio viene aggiunto un utente come delegato e viene impostata la chiamata simultanea dei delegati.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Modificare la regola di chiamata simultanea dei delegati

Questo esempio modifica la regola di chiamata simultanea impostata nell'esempio precedente sulla regola di chiamata in ritardo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Rimuovere il delegato

In questo esempio viene rimosso il delegato.

> [!NOTE]
> Quando l'ultimo delegato viene rimosso, il delegare squilla viene disabilitato automaticamente.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Aggiungere un delegato e configurare la regola di inoltro di chiamata a delegati

In questo esempio viene aggiunto un delegato e viene impostata la regola inoltro di chiamata a delegati.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Abilitare la chiamata simultanea e impostare un numero di destinazione

Questo esempio Abilita la chiamata simultanea e imposta un numero di destinazione squillante simultaneo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Per cambiare il numero di destinazione squillo simultaneo di un utente che ha già attivato la chiamata simultanea, Mantieni il comando con l'opzione/enablesimulring, altrimenti il numero di destinazione non verrà modificato.

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Disabilitare lo squillo simultaneo

Questo esempio disabilita la chiamata simultanea.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Aggiungere un membro del team per la chiamata al team e configurare lo squillo simultaneo al gruppo membri della chiamata del team

Questo esempio aggiunge un membro del team al gruppo di chiamate team di un utente e consente la chiamata simultanea al gruppo di chiamate del team.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> L'aggiunta di un membro al gruppo di chiamata del team di un utente cambia automaticamente il settigs di chiamata simultanea degli utenti per simulring il gruppo di chiamate del team.

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Rimuovere un membro dal gruppo di chiamate team

Questo esempio rimuove un membro del team del gruppo di chiamate team di un utente.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Se il membro da rimuovere è l'unico membro del gruppo di chiamate del team, lo squillo simultaneo al gruppo di chiamate del team verrà disabilitato automaticamente.

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Impostare l'anello ritardato sul gruppo di chiamate team

Questo esempio cambia l'intervallo di tempo in ritardo con l'impostazione dell'ora del gruppo di chiamate team.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Abilitare la chiamata del team

Questo esempio consente di abilitare la chiamata al team per un utente specifico.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Se il gruppo di chiamata del team dell'utente non ha membri, la chiamata del team non verrà abilitata.

 **Output**

#### <a name="disable-team-call"></a>Disabilitare la chiamata del team

Questo esempio disabilita la chiamata del team per un utente specifico.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Abilitare il ritiro delle chiamate di gruppo e assegnare un gruppo di raccolta a un utente

In questo esempio viene assegnato un gruppo di prelievo a un utente e viene abilitato il ritiro delle chiamate di gruppo.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Output**

```output
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@ contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Disabilitare il ritiro delle chiamate di gruppo

In questo esempio viene disabilitato il ritiro delle chiamate di gruppo per un utente specifico.

```
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Quando si disattiva il prelievo delle chiamate di gruppo per un utente, il numero di gruppo assegnato all'utente non viene mantenuto. Se in seguito si vuole riabilitare il ritiro delle chiamate di gruppo per l'utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione/enablegrouppickup.

```
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep. ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descrizione

SYSPrep. ps1 è uno script di Windows PowerShell che installerà i prerequisiti di Skype for Business Server 2015 seguenti nel computer del sistema operativo Windows Server 2008.

- Microsoft .NET Framework 4,5

- Microsoft SQL Server Express

- Versione 3,0 di Windows PowerShell

- Visual C++ 2010 ridistribuibile

- Aggiornamenti di Internet Information Server

- Windows Identity Foundation

- File di base di Skype for Business Server 2015

  Mentre il nome dello script è simile allo strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi. Questo script installerà solo i prerequisiti necessari per Skype for Business Server 2015. Dopo aver installato questi prerequisiti, lo strumento SYSPrep di Windows può quindi essere usato per creare un'immagine del server.

### <a name="requirements"></a>Requisiti

Prima di eseguire lo script SYSPrep. ps1, è necessario copiare i file dei prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008, ad esempio **D:\setup**. Questa cartella deve includere anche una copia dei file di 2015 di Skype for Business Server, in particolare **Setup. exe.** I file dei prerequisiti possono essere scaricati dai percorsi seguenti:


| **Prerequisiti**                                | **Posizione**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4,5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/en-us/download/details.aspx?id=23650>  <br/> |
| Versione 3,0 di Windows PowerShell  <br/>           | <https://www.microsoft.com/en-us/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 ridistribuibile  <br/>          | <https://www.microsoft.com/en-us/download/details.aspx?id=5555>  <br/>  |
| Aggiornamenti di Internet Information Server  <br/>      | <https://www.microsoft.com/en-us/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/en-us/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup. exe  <br/> | Copia da Skype for Business Server 2015 media  <br/>                   |

### <a name="parameter"></a>Parametro

Il parametro **-SetupFolder** accetta come argomento la posizione della directory dei file di prerequisiti

### <a name="examples"></a>Esempi

Per eseguire lo script SYSPrep. ps1 e installare i prerequisiti di Skype for Business Server 2015, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migrazione degli annunci di numeri non assegnati
<a name="UNAM"> </a>

Lo strumento di migrazione annunci numeri non assegnati consente a un amministratore di Skype for Business Server 2015 di trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio da un server o pool Skype for business di origine a un destinazione Skype for Business Server o pool.

### <a name="description"></a>Descrizione

Lo strumento di migrazione annunci numeri non assegnati è uno script di Windows PowerShell che sposta la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio di un server o pool di origine a un altro server o pool.

Quando viene eseguita, lo script di migrazione degli annunci di numeri non assegnati esegue le operazioni seguenti:

1. Consente di trasferire tutti i file audio usati dagli annunci di numeri non assegnati dell'applicazione di annunci ospitati nel server di origine o nel pool nell'archivio file del server o del pool di destinazione.

    > [!NOTE]
    > I file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.

2. Consente di trasferire tutti gli annunci di numeri non assegnati configurati per l'applicazione di annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.

3. Riassegnare tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool al server o al pool di destinazione.

Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati serviti dall'applicazione di annuncio ospitata nel server di origine o nel pool verranno ora serviti con la stessa configurazione dal server o dal pool di destinazione.

### <a name="output"></a>Output

Lo script **Move-CsAnnouncementConfiguration** indica nella finestra di gestione di Skype for Business Server in cui è stato eseguito l'esito positivo o negativo dell'operazione di migrazione.

Se l'esecuzione dell'operazione viene interrotta da qualsiasi errore, gli intervalli di numeri non assegnati spostati correttamente nella destinazione rimarranno nella destinazione in una maschera operativa e il resto degli intervalli di numeri non assegnati di cui eseguire la migrazione rimarrà in anche l'origine in una maschera operativa. Per eseguire la migrazione completa del resto della configurazione, rieseguire lo script dopo avere indirizzato l'errore.

### <a name="purpose"></a>Scopo

Lo script di migrazione annunci numero non assegnati può essere usato nei tre scenari seguenti:

- **Migrazione delle impostazioni di configurazione a una nuova versione di Skype for Business Server:** Contoso sta eseguendo la migrazione a Skype for Business Server 2015 e durante il processo di migrazione l'amministratore di Skype for Business Server desidera trasferire la configurazione dei numeri non assegnati serviti dall'applicazione di annuncio dalla distribuzione di Lync Server 2013 alla nuova distribuzione di Skype for Business Server 2015. Per cambiare le impostazioni di configurazione, l'amministratore di Skype for Business Server usa lo strumento di migrazione annunci numero non assegnati.

- **Rollback di una distribuzione da Skype for Business Server 2015 a Lync server 2013:** A causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione di Skype for Business Server 2015. Per ridurre al minimo le interruzioni del servizio, l'amministratore di Skype for Business Server usa lo strumento di migrazione annunci numero non assegnati per eseguire il rollback della configurazione dalla distribuzione di Skype for Business Server 2015 alla distribuzione di Lync Server 2013.

- **Spostamento di dati tra distribuzioni:** Contoso sta sostituendo tutti i server di un pool con server più recenti. La loro strategia consiste nel distribuire un nuovo pool di Skype for Business Server 2015, trasferire tutti i dati dal vecchio al nuovo pool e quindi deprecare il vecchio pool. Dopo la distribuzione del nuovo pool, viene usato lo strumento di migrazione annunci numeri non assegnati per trasferire la configurazione dal pool precedente a quello nuovo.

#### <a name="requirements"></a>Requisiti

Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:

1. Lo script deve essere eseguito da un computer in cui è installato Skype for Business Server Management Shell.

2. L'applicazione di annuncio deve essere distribuita correttamente nei server o nei pool di Skype for business di origine e di destinazione.

#### <a name="move-csannouncementconfiguration-script"></a>Script Move-CsAnnouncementConfiguration

Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.

![Parametri di Move-CsAnnouncementConfiguration.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Esempi

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Lync Server 2013 a un pool di Skype for Business Server 2015

Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Lync Server 2013) nel pool di destinazione (Skype for Business Server 2015).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Skype for Business Server 2015 a un pool di Lync Server 2013

Questo esempio sposta gli annunci del numero non assegnati dal pool di origine (Skype for Business Server 2015) nel pool di destinazione (Lync Server 2013).

```PowerShell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Dati Web conf
<a name="WebConfData"> </a>

Lo strumento di dati Web conf consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore. Gli scenari includono la possibilità di eliminare i dati di una riunione di un utente specifico in base a un criterio di timestamp.

### <a name="description"></a>Descrizione

Questo strumento consente all'amministratore di eseguire le operazioni seguenti:

1. Trovare tutti i dati di Web Conferencing associati a un singolo utente.

2. Eliminare tutti i dati di Web Conferencing associati a un singolo utente.

3. Eliminare tutti i dati di Web Conferencing associati a un singolo utente antecedente a una determinata data.

4. Spostare tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro.

> [!NOTE]
> Gli strumenti del Resource Kit per Lync Server 2010 supportano lo spostamento di tutti i dati di Web Conferencing associati a un singolo utente quando l'utente viene spostato da un pool a un altro. Questa funzionalità è ora deprecata da questo strumento a favore del parametro **MoveConferenceData** . Per informazioni dettagliate su questo parametro, vedere il cmdlet [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser.md?view=skype-ps) .

Lo strumento Elimina i dati delle riunioni solo per le riunioni inattive. Le riunioni attive (o le riunioni in sessioni) non possono essere eliminate.

Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione. L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere ospitato nello stesso pool di utenti.

### <a name="output"></a>Output

Questo strumento restituisce i risultati di ogni operazione:

- Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione inattive che hanno l'utente come organizzatore.

- Se viene eseguita un'eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati della riunione i cui dati verranno eliminati.

### <a name="requirements"></a>Requisiti

Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitato l'organizzatore.

Lo strumento deve essere eseguito usando i privilegi di amministratore con l'accesso all'archivio di file di contenuto.

### <a name="examples"></a>Esempi

La tabella seguente descrive i parametri, alcuni dei quali vengono usati negli esempi.

![Parametri dello strumento Web Conf Data.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Nell'esempio precedente viene illustrato il funzionamento di un comando di query. L'output di un comando di questo tipo è un elenco di tutte le cartelle del contenuto della riunione interessate da questo strumento.

```
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

Il precedente è un esempio di comando Elimina. Il comando Elimina consente di rimuovere tutte le cartelle riunione inattiva da questo utente.

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per gli amministratori che hanno bisogno di un controllo più preciso sui dati della riunione di conferenza.


