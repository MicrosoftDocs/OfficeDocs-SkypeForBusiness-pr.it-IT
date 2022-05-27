---
title: Documentazione di Skype for Business Server Resource Kit Tools 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/20/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c341f1-86fa-479d-ba4d-28df5a4c1622
description: Questo articolo descrive gli strumenti di Skype for Business Server Resource Kit 2015, inclusi lo scopo di ogni strumento ed esempi del relativo uso. Il resource kit Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento Web Conf Data può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento SEFAUtil può essere usato per configurare l'inoltro di chiamata delegato e la risposta per gli utenti. È consigliabile che gli amministratori IT usino questi strumenti per gestire in modo più efficace Skype for Business Server 2015.
ms.openlocfilehash: 83777dbe16e70030b13c07fced716ffbc4d51f35
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675498"
---
# <a name="skype-for-business-server-2015-resource-kit-tools-documentation"></a>Documentazione di Skype for Business Server Resource Kit Tools 2015

Questo articolo descrive gli strumenti di Skype for Business Server Resource Kit 2015, inclusi lo scopo di ogni strumento ed esempi del relativo uso. Il resource kit Skype for Business Server 2015 consente di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono Skype for Business Server 2015. Ad esempio, lo strumento **Web Conf Data** può essere usato per controllare facilmente i dati caricati dagli utenti durante una riunione online. Lo strumento **SEFAUtil** può essere usato per configurare l'inoltro di chiamata delegato e la risposta per gli utenti. È consigliabile che gli amministratori IT usino questi strumenti per gestire in modo più efficace Skype for Business Server 2015.

## <a name="installation-of-the-resource-kit-tools"></a>Installazione degli strumenti di Resource Kit

Per installare Skype for Business Server Resource Kit 2015, scaricare [OCSReskit.msi](https://www.microsoft.com/download/details.aspx?id=52631) dall'Area download.

Eseguire **OCSResKit.msi** per eseguire un'installazione semplice. Il .msi installa tutti gli strumenti nel percorso seguente: **%Programmi%\Skype for Business Server 2015\ResKit**. Gli strumenti che sono eseguibili autonomi si trovano in questa cartella. Gli strumenti che dispongono anche di file di supporto si trovano nelle proprie sottocartelle.

## <a name="supported-environments"></a>Ambienti supportati

L'Skype for Business Server Resource Kit 2015 deve essere installato in un server che soddisfi le specifiche necessarie per Skype for Business Server 2015, in genere uno usato per eseguire Skype for Business Server 2015.

## <a name="resource-kit-tools-overview"></a>Panoramica degli strumenti di Resource Kit

Di seguito è riportato un elenco degli strumenti forniti nel Resource Kit di Skype for Business Server 2015. Una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio, è illustrata nelle sezioni seguenti.

- [ABSConfig](resource-kit-tools.md#ABSConfig)

- [Monitoraggio del servizio criteri di larghezza di banda](resource-kit-tools.md#bpsm)

- [Analizzatore utilizzo larghezza di banda](resource-kit-tools.md#bua)

- [Chiamare Parkometer](resource-kit-tools.md#callpark)

- [DBAnalyze](resource-kit-tools.md#dba)

- [Importare i dati del servizio Archiviazione](resource-kit-tools.md#Issd)

- [LCSSync](resource-kit-tools.md#LCSSync)

- [Console utente ricerca](resource-kit-tools.md#LUC)

- [MsTurnPing](resource-kit-tools.md#MsTurnPing)

- [Visualizzatore configurazione di rete](resource-kit-tools.md#NCV)

- [Response Group Agent Live](resource-kit-tools.md#RGAL)

- [SEFAUtil](resource-kit-tools.md#SEFAUtil)

- [SYSPrep.ps1](resource-kit-tools.md#SYSPrep)

- [Migrazione degli annunci di numeri non assegnati](resource-kit-tools.md#UNAM)

- [Dati web conf](resource-kit-tools.md#WebConfData)

## <a name="absconfig"></a>ABSConfig
<a name="ABSConfig"> </a>

Lo strumento di configurazione del servizio Rubrica (ABSConfig) è uno strumento amministrativo che consente agli amministratori di personalizzare la configurazione del servizio Rubrica in Skype for Business Server 2015. Questo strumento consente inoltre agli amministratori di Skype for Business Server 2015 di ripristinare le impostazioni predefinite del servizio Rubrica.

### <a name="description"></a>Descrizione

ABSConfig è un'applicazione interfaccia utente grafica che consente agli amministratori di configurare Active Directory Domain Services attributi correlati al servizio Rubrica.

Gli scenari principali per lo strumento sono i seguenti:

- Per consentire agli amministratori di eseguire il mapping degli attributi in Active Directory Domain Services agli attributi per Skype for Business Server 2015.

- Per consentire agli amministratori di specificare l'attributo Active Directory Domain Services da includere o escludere nei file del servizio Rubrica.

- Per consentire agli amministratori di eseguire il ripristino, impostazioni predefinite del servizio Rubrica.

È possibile avviare lo strumento ABSConfig usando il file ABSConfig.exe. Lo strumento viene aperto nella scheda **Configura attributi**. Questa tabella include opzioni per eseguire il mapping degli attributi Active Directory Domain Services ai campi degli attributi per Skype for Business Server 2015 e per specificare gli utenti da includere o escludere nei file del servizio Rubrica in base a filtri di attributo specifici. Ha anche opzioni per personalizzare il valore del numero di telefono da includere nel file della Rubrica. L'opzione **Ripristina impostazioni predefinite** consente agli amministratori di ripristinare i valori predefiniti delle impostazioni del servizio Rubrica.

> [!NOTE]
> Il nuovo mapping degli attributi di Active Directory a nomi di campi OC diversi funzionerà solo per il download di file della rubrica e non è supportato da Query Web rubrica.

### <a name="output"></a>Output

ABSConfig archivia la configurazione del servizio Rubrica nel database.

```console
Path: %ProgramFiles%\Skype for Business Server 2015\Reskit
```

### <a name="purpose"></a>Finalità

ABSConfig offre un modo semplice e rapido per personalizzare Skype for Business Server servizio Rubrica 2015.

### <a name="requirements"></a>Requisiti

#### <a name="computer"></a>Computer

ABSConfig può essere eseguito solo da un computer aggiunto a un dominio in cui è installato Skype for Business Server 2015. Nel caso di Skype for Business Server 2015, edizione Enterprise, questo strumento può essere eseguito in qualsiasi server Front-End in cui il servizio Rubrica è abilitato durante l'installazione.

#### <a name="network"></a>Rete

Il computer deve essere in grado di connettersi al pool di Front-End e al database back-end.

#### <a name="software"></a>Software

Prima di eseguire lo strumento ABSConfig, è necessario installare i componenti software seguenti:

- Skype for Business Server 2015

#### <a name="users"></a>Utenti

Amministratori che dispongono delle autorizzazioni necessarie per aggiornare la distribuzione Skype for Business Server 2015.

### <a name="examples"></a>Esempi

È possibile avviare ABSConfig digitando **ABSConfig.exe** al prompt dei comandi. Di seguito è illustrata l'interfaccia utente dello strumento ABSConfig.

![Strumento ABSConfig.exe.](../media/Reskit_2012_Tools_Documentation_ABSConfig.JPG)

### <a name="summary"></a>Riepilogo

Lo strumento ABSConfig offre agli amministratori uno strumento rapido e facile da usare per personalizzare Skype for Business Server servizio Rubrica 2015.

## <a name="bandwidth-policy-service-monitor"></a>Monitoraggio del servizio criteri di larghezza di banda
<a name="bpsm"> </a>

Lo strumento Monitoraggio servizio criteri di larghezza di banda consente agli amministratori di visualizzare un elenco dei seguenti elementi:

1. Tutti i servizi di criteri di larghezza di banda Skype for Business Server 2015 configurati (autenticazione e core) nella topologia

2. Le connessioni che ogni servizio effettua ad altri servizi dei criteri di larghezza di banda e ai server Perimetrali

3. Tutti i collegamenti configurati nel documento di configurazione della rete e l'utilizzo della larghezza di banda in tempo reale, come indicato da ognuno dei servizi criteri di larghezza di banda

### <a name="description"></a>Descrizione

Lo strumento Monitoraggio servizio criteri di larghezza di banda viene implementato come applicazione basata su GUI. Gli amministratori avviano lo strumento eseguendo PDPMonUI.exe.

All'avvio dello strumento, tenta di individuare l'elenco dei servizi criteri di larghezza di banda nella topologia. Al termine dell'aggiornamento iniziale, il riquadro a sinistra della finestra viene popolato con un elenco di servizi raggruppati in base ai cluster a cui appartengono.

Quando gli amministratori selezionano un particolare servizio di criteri di larghezza di banda, nel riquadro a destra vengono visualizzate le informazioni su quel particolare servizio. Tale riquadro include anche due schede principali che visualizzano informazioni.

#### <a name="machine-info-tab"></a>Scheda Informazioni computer

La scheda **Informazioni computer** mostra i dettagli del servizio criteri larghezza di banda selezionato e l'elenco e lo stato di tutte le connessioni effettuate dal servizio criteri larghezza di banda selezionato ad altri servizi.

#### <a name="topology-info-tab"></a>Scheda Info topologia

La scheda **Informazioni topologia** mostra un elenco di tutti i collegamenti configurati nelle impostazioni di configurazione di rete. Per ogni collegamento, viene visualizzata la capacità della larghezza di banda audio e video. Viene inoltre visualizzata la larghezza di banda attualmente utilizzata, sia in Kbps che come percentuale della capacità. Lo strumento usa la codifica a colori per evidenziare i collegamenti con un utilizzo vicino alla capacità, consentendo agli amministratori di isolare rapidamente tali collegamenti.

> [!NOTE]
>  Se lo strumento Monitoraggio servizio criteri di larghezza di banda si verifica un errore quando si connette a uno dei servizi criteri di larghezza di banda configurati, le informazioni nelle schede **Informazioni** computer e **Info topologia** non verranno popolate. Tuttavia, è possibile che lo strumento si connetta inizialmente, ma successivamente perda la connessione al servizio. In questi casi, gli amministratori potrebbero visualizzare informazioni obsolete. In ognuna delle schede è presente un timestamp **ultimo aggiornamento** che consente agli amministratori di visualizzare l'ultimo aggiornamento dei dati per un determinato servizio criteri di larghezza di banda.

### <a name="output"></a>Output

Non è disponibile alcun output della riga di comando; l'output del programma è contenuto all'interno dell'interfaccia utente grafica (GUI) principale.

### <a name="purpose"></a>Finalità

Lo scopo dello strumento Monitoraggio servizio criteri di larghezza di banda è consentire agli amministratori di visualizzare lo stato di ognuno dei servizi criteri di larghezza di banda definiti nella topologia. Inoltre, gli amministratori possono visualizzare l'utilizzo della larghezza di banda in tempo reale per tutti i collegamenti definiti nel documento configurazione di rete.

### <a name="requirements"></a>Requisiti

Lo strumento Monitoraggio servizio criteri di larghezza di banda deve essere eseguito in un computer che fa parte della topologia Skype for Business Server.

### <a name="summary"></a>Riepilogo

Lo strumento Monitoraggio servizio criteri di larghezza di banda può essere una risorsa utile per gli amministratori, in modo che possano controllare lo stato di tutti i servizi criteri di larghezza di banda nella topologia e, cosa più importante, possono ottenere l'utilizzo della larghezza di banda in tempo reale per i collegamenti definiti nelle impostazioni di configurazione della rete.

## <a name="bandwidth-utilization-analyzer"></a>Analizzatore utilizzo larghezza di banda
<a name="bua"> </a>

Analizzatore utilizzo larghezza di banda è uno strumento che crea report su varie visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC tra i collegamenti WAN nella rete aziendale. Questi report possono essere usati per comprendere il modello di consumo corrente della larghezza di banda e per facilitare la pianificazione della capacità della larghezza di banda.

### <a name="description"></a>Descrizione

L'analizzatore utilizzo larghezza di banda viene implementato come applicazione basata su GUI. Questo strumento genera report specifici per l'utilizzo audio in rete e consente di pianificare la capacità. Esegue inoltre l'iterazione sulla capacità della larghezza di banda assegnata a vari collegamenti.

### <a name="output"></a>Output

L'analizzatore utilizzo larghezza di banda fornisce tracciati grafici della capacità e dell'utilizzo della larghezza di banda per l'audio per tutti i collegamenti WAN configurati nel sistema.

### <a name="purpose"></a>Finalità

In qualsiasi distribuzione di voce e video, è fondamentale monitorare e comprendere la tendenza di utilizzo della larghezza di banda del traffico multimediale nella rete aziendale. Lo strumento Analizzatore utilizzo larghezza di banda consente a un amministratore di ottenere questo risultato. Questo strumento esegue le operazioni seguenti:

- Genera report specifici per l'utilizzo audio nella rete

- Consente una pianificazione della capacità e un'iterazione più efficaci sulla capacità della larghezza di banda assegnata a vari collegamenti

L'analizzatore utilizzo larghezza di banda può generare grafici di report sulla capacità della larghezza di banda e sull'utilizzo; sono i seguenti:

- Tutti i collegamenti WAN nella rete aziendale

- Filtrato in base ai collegamenti WAN selezionati che sono stati scelti

- Filtrato in base ai collegamenti WAN che hanno superato la capacità dei collegamenti

- Filtrato in base ai collegamenti WAN che hanno utilizzato in modo insufficiente la larghezza di banda di cui è stato effettuato il provisioning

- Filtrare in base ai collegamenti WAN che hanno raggiunto livelli critici (un utilizzo della larghezza di banda superiore al 90% della capacità della larghezza di banda del collegamento WAN)

- Filtrato in base al tipo di collegamento WAN: collegamenti di rete-sito, collegamenti interregionali e collegamenti all'interno di un sito

- Filtrato in base all'area di rete

#### <a name="applications"></a>Applicazioni

L'analizzatore utilizzo larghezza di banda include le due applicazioni seguenti (strumenti):

- **WanLinkLogCollector.exe** Questo strumento consente all'utente di immettere le informazioni necessarie.

- **BandwidthUtilizationAnalyzer.xlsm** Un report software Microsoft Excel foglio di calcolo viene avviato automaticamente da WanLinkLogCollector.exe. Questa applicazione consente all'utente di applicare filtri al report, come illustrato più avanti in questo articolo.

#### <a name="phases-of-using-bandwidth-utilization-analyzer"></a>Fasi dell'uso dell'analizzatore utilizzo larghezza di banda

L'uso dell'analizzatore utilizzo larghezza di banda prevede due fasi:

- Raccogliere i log, che vengono eseguiti tramite WanLinkLogCollector.exe

- Personalizzare i report, che vengono eseguiti tramite BandwidthUtilizationAnalyzer.xlsm

  > [!IMPORTANT]
  > È consigliabile che BandwidthUtilizationAnalyzer.xlsm non venga avviato manualmente dagli utenti finali.

#### <a name="starting-bandwidth-utilization-analyzer"></a>Avvio dell'analizzatore utilizzo larghezza di banda

Avviare WanLinkLogCollector.exe al prompt dei comandi o usando Windows Explorer.

 **Uso di WanLinkLogCollector.exe**

L'uso di WanLinkLogCollector.exe prevede tre passaggi:

1. **Registrare la sequenza temporale** Specificare la sequenza temporale per cui deve essere generato il report

2. **Specificare le directory dei file** Specificare le informazioni sul percorso del file

3. **Raccogliere i log e avviare il visualizzatore di report** Eseguire il comando per generare il report

#### <a name="step-1---log-the-timeline"></a>Passaggio 1 - Registrare la sequenza temporale

La registrazione della sequenza temporale consente all'utente dello strumento di specificare quanto segue, come illustrato nella figura seguente.

1. **Data di inizio** Si tratta della data di inizio della sequenza temporale per cui deve essere generato il report; ad esempio, 1 agosto 2010.

2. **Data di fine** Si tratta della data di fine della sequenza temporale per cui deve essere generato il report; ad esempio, il 30 settembre 2010.

     ![Date di inizio e fine nell'utilizzo della larghezza di banda A.](../media/Reskit_2012_Tools_Documentation_Image4.jpg)

#### <a name="step-2---specify-the-file-directories"></a>Passaggio 2- Specificare le directory dei file

Le directory di file seguenti possono essere specificate dall'utente come illustrato.

- **Percorso dei file di log del server** Percorso della cartella in cui vengono archiviati i log del server dei criteri di larghezza di banda. Si tratta in genere di \<fileserver\>\\<scelta tra FE\>\AppServerFiles\PDP.

- **Percorso di archiviazione temporanea dei file** Percorso del file temporaneo in cui vengono archiviati i file intermedi durante la generazione del report.

  ![Directory dei file nell'anale utilizzo larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image5.jpg)

  > [!NOTE]
  > Assicurarsi che l'accesso ai log del server e alla cartella dell'archivio file temporaneo sia sufficiente per l'utente dello strumento.

#### <a name="step-3---collect-the-logs-and-start-the-report-viewer"></a>Passaggio 3: Raccogliere i log e avviare il visualizzatore di report

Per raccogliere i log e avviare il visualizzatore di report, fare clic su **Esegui** come illustrato di seguito. Questo passaggio raccoglie i dati necessari.

![Raccolta di dati nell'analisi dell'utilizzo della larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image6.jpg)

Quando la convalida dell'input ha esito positivo, viene visualizzato il messaggio riportato di seguito.

![Log raccolti notifica in Larghezza di banda Utili.](../media/Reskit_2012_Tools_Documentation_Image7.jpg)

Fare clic su **OK**. BandwidthUtilizationAnalyzer.xlsm viene avviato automaticamente. Seguire le istruzioni nella finestra di messaggio. Per informazioni dettagliate, vedere **Uso di BandwidthUtilizationAnalyzer.xlsm** nella sezione successiva.


### <a name="using-bandwidthutilizationanalyzerxlsm"></a>Uso di BandwidthUtilizationAnalyzer.xlsm

1. Quando BandwidthUtilizationAnalyzer.xlsm viene avviato automaticamente, fare clic su **Aggiorna** come illustrato di seguito.

     ![BandwidthUtilizationAnalyzer.xlsm.](../media/Reskit_2012_Tools_Documentation_Image8.jpg)

2. Quando viene aperta una cartella file, selezionare consolidated.csv dal percorso specificato nella finestra di messaggio, come illustrato di seguito. Il percorso viene inoltre visualizzato come **C:\Temp**.

     ![Apertura di una cartella in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image9.jpg)

3. Fare clic su **Importa**.

4. Il tracciato grafico viene generato automaticamente. È disponibile quando il puntatore working-in-the-background scompare.

     ![Applicazione di filtri nella visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

#### <a name="applying-filters-to-the-report-view"></a>Applicazione di filtri alla visualizzazione report

I filtri che possono essere applicati alla visualizzazione report come illustrato di seguito sono descritti di seguito:

![Applicazione di filtri nella visualizzazione report.](../media/Reskit_2012_Tools_Documentation_Image11.jpg)

1. **Nome** Filtrare in base ai collegamenti WAN (il filtro si trova sul lato destro del grafico). Il prefisso indica i tipi di collegamento seguenti; vedere la casella verticale (blu):

   - **Sito S** Collegamento WAN da un sito di rete a un'area di rete

   - **IS intersito** Collegamento WAN tra due siti di rete

   - **Inter-area R** Collegamento WAN tra due aree di rete

2. **Limite superato** Filtrare in base ai collegamenti WAN il cui utilizzo della larghezza di banda è superiore alla capacità della larghezza di banda

3. **Livelli critici** Filtrare in base ai collegamenti WAN il cui utilizzo della larghezza di banda ha raggiunto il 90% o più della capacità della larghezza di banda

4. **Sottoutilizzato** Filtrare in base ai collegamenti WAN il cui utilizzo della larghezza di banda è stato inferiore al 25% della capacità della larghezza di banda

5. **Tipo di collegamento** Filtrare in base ai tipi di collegamenti WAN seguenti:

   - **Tipo di sito di rete**

   - **Tipo tra siti**

   - **Tipo di collegamento tra aree**

6. **Regione** Filtrare in base all'area di rete

Le figure seguenti mostrano i filtri descritti in precedenza.

Filtrare in base al **nome**. Selezionare l'elenco di collegamenti che devono essere visualizzati nel grafico.

![Filtro in base al nome in BandwidthUtilizationAnalyzer.](../media/Reskit_2012_Tools_Documentation_Image12.jpg)

Filtro in base **al limite superato**. Selezionare **True** per applicare il filtro.

![Filtro in base al limite superato.](../media/Reskit_2012_Tools_Documentation_Image13.jpg)

Filtrare in base **ai livelli critici**. Selezionare **True** per applicare il filtro.

![Filtro in base ai livelli critici.](../media/Reskit_2012_Tools_Documentation_Image14.jpg)

Filtrare in base **a Sottoutilizzato**. Selezionare **True** per applicare il filtro.

![Filtro in base a Sottoutilizzato.](../media/Reskit_2012_Tools_Documentation_Image15.jpg)

Filtrare in base **al tipo di collegamento**. Selezionare il tipo o i tipi da visualizzare.

![Filtro in base al tipo di collegamento.](../media/Reskit_2012_Tools_Documentation_Image16.jpg)

Filtrare in base **all'area**. Selezionare un elenco di aree i cui collegamenti devono essere visualizzati.

![Filtro in base all'area.](../media/Reskit_2012_Tools_Documentation_Image17.jpg)

### <a name="requirements"></a>Requisiti

- .NET Framework 3.5

- Microsoft Excel 2010 o Excel 2007

### <a name="summary"></a>Riepilogo

L'analizzatore utilizzo larghezza di banda viene usato per tracciare l'utilizzo della larghezza di banda audio per il traffico UC attraverso la rete. Questo strumento può essere usato anche per segnalare l'utilizzo della larghezza di banda video in rete.

## <a name="call-parkometer"></a>Chiamare Parkometer
<a name="callpark"> </a>

Call Parkometer è un'applicazione da riga di comando che consente di accedere facilmente al database orbita di Parcheggio di chiamata.

### <a name="description"></a>Descrizione

Call Parkometer è uno strumento per tenere traccia delle chiamate attualmente parcheggiate. Raccoglie anche statistiche sulle orbite e sull'utilizzo del server di parcheggio di chiamata (CPS). Questo strumento da riga di comando fornisce l'accesso in lettura e scrittura all'orbita CPS SQL Server database da un computer locale o connesso in remoto.

Tutte le opzioni si escludono a vicenda. La sintassi della riga di comando è la seguente:

- **Parametro -o** : elenca tutti gli intervalli di orbita configurati per il pool.

- **-n** parametro: elenca tutte le orbite attualmente usate in questo pool. Le informazioni visualizzate sono le seguenti:

  - URI (Uniform Resource Identifier) SIP del parkee e del parker.

  - Nome host del CPS in cui è parcheggiata la chiamata.

  - Timestamp di quando la chiamata è stata parcheggiata.

- **Parametro -f** : elenca il numero di orbite attualmente disponibili nel pool.

- **-r \<n\>** parameter: elenca le \<n\> ultime chiamate parcheggiate. Le informazioni visualizzate sono le seguenti:

  - URI SIP parkee.

  - URI SIP Parker.

  - Nome host del CPS in cui è stata parcheggiata la chiamata.

  - Timestamp del momento in cui la chiamata è stata recuperata o eliminata.

- **-t\<n\>** parameter : testa la prenotazione di un'orbita nel database per mostrare la casualità dei numeri di orbita assegnati.

### <a name="output"></a>Output

A seconda dei parametri di input specificati al prompt dei comandi, Il parkometro di chiamata visualizza l'output seguente:

- Tutti gli intervalli di orbita configurati per questo pool

- Chiamate attualmente parcheggiate

- Numero di orbite gratuite (disponibili)

- Chiamate parcheggiate di recente

- Orbite riservate per il test di valori di orbita uniformi e casuali

### <a name="purpose"></a>Finalità

Lo scopo dello strumento CPS è fornire l'accesso da riga di comando al database CPS. L'amministratore può visualizzare l'utilizzo cps e determinare il numero di orbite assegnate a un pool.

### <a name="requirements"></a>Requisiti

Non sono previsti requisiti se questo strumento viene eseguito nello stesso computer che esegue CPS. Se questo strumento viene eseguito in un computer remoto, è necessario configurare il database SQL Server usato da Skype for Business Server 2015 per consentire l'accesso remoto. Il parkometro di chiamata deve essere configurato con una stringa di connessione di database SQL Server per connettersi alla SQL Server del pool. Questa stringa di connessione del database SQL Server è definita nel file di configurazione **parkometer.exe.config**. Deve essere inserito nella stessa directory in cui si trova parkometer.exe. Il file XML seguente è un esempio di parkometer.exe.config. I parametri che devono essere configurati sono il nome utente (ad esempio, mydomain\Administrator), la password (ad esempio, mypassword) e il nome host (ad esempio, myserver).

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

Intervalli di orbita distribuiti: il parametro -o elenca tutti gli intervalli di orbita configurati per questo pool, come illustrato

![Intervalli di orbita nel parkometro di chiamata.](../media/Reskit_2012_Tools_Documentation_Image18.jpg)

Chiamate attualmente parcheggiate: il parametro -n elenca tutte le orbite attualmente usate in questo pool, come illustrato

![Chiamate attualmente parcheggiate in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image19.jpg)

Numero di orbite libere: il parametro -f elenca il numero di orbite attualmente libere nel pool, come illustrato

![Orbite libere nel parkometro di chiamata.](../media/Reskit_2012_Tools_Documentation_Image20.jpg)

Chiamate parcheggiate di recente: il parametro -r \<n\> elenca le \<n\> ultime chiamate parcheggiate, come illustrato

![Chiamate parcheggiate di recente in Call Parkometer.](../media/Reskit_2012_Tools_Documentation_Image21.jpg)

Prenotazione dell'orbita di test: il parametro -t \<n\> testa la prenotazione di un'orbita nel database, come illustrato

![Testare le prenotazioni dell'orbita nel parkometro di chiamata.](../media/Reskit_2012_Tools_Documentation_Image22.jpg)

### <a name="summary"></a>Riepilogo

Call Parkometer è uno strumento da riga di comando che fornisce informazioni dettagliate sul server parcheggio di chiamata.

## <a name="dbanalyze"></a>DBAnalyze
<a name="dba"> </a>

### <a name="description"></a>Descrizione

DBAnalyze è uno strumento da riga di comando che consente agli amministratori di raccogliere report di analisi sui database Skype for Business Server 2015. DBAnalyze ha le modalità seguenti: diagnostica, dati utente, conferenza, MCU e frammentazione del disco:

- **Modalità di diagnostica** Crea un report che include informazioni sulle tabelle (numero di record, frammentazione, dimensioni dei dati e dimensioni dell'indice), dimensioni dei file di dati e di log, l'ultimo tempo di backup, la distribuzione dei contatti tra i server che eseguono Microsoft Office Communications Server, il numero medio di autorizzazioni, contatti, contenitori, sottoscrizioni, pubblicazioni, endpoint per utente, tutti gli utenti non ospitati correttamente, gli utenti che non possono essere indirizzati,  numero medio di conferenze organizzate per utente, conferenze pianificate, conferenze attive e versione del database.

    > [!NOTE]
    > L'esecuzione della modalità di diagnostica può influire sulle prestazioni del server.

- **Modalità dati utente** Segnala i dati di contatto, contenitore, sottoscrizione, pubblicazione, autorizzazione e gruppo di contatti per un utente specificato o per gli utenti che hanno tale utente negli elenchi di contatti e autorizzazioni. Questa modalità segnala anche i dati di riepilogo per le conferenze a cui un utente organizza o a cui è invitato.

- **Modalità conferenza** Segnala i dati dettagliati per una conferenza specifica, inclusi tutti i dettagli pianificare-time per la conferenza, l'elenco degli invitati, l'elenco dei tipi di supporti consentiti per la conferenza, gli MCU attivi (unità di controllo multipunto), l'elenco dei partecipanti attivi e lo stato di segnalazione di ogni partecipante.

- **Decodificare l'ID riunione** Decodifica un ID riunione PSTN (Public Switched Telephone Network) specificato dal commutatore **/pstnid** ma che non si connette al back-end per informazioni dettagliate.

- **Risolvere la conferenza** Decodifica un ID riunione PSTN specificato dall'opzione **/pstnid** e visualizza informazioni sulla conferenza indicata dall'ID.

- **Modalità MCU** Segnala l'ID, il tipo di supporto, l'URL, lo stato dell'heartbeat, il carico della conferenza e il carico dei partecipanti per ogni MCU nel pool.

- **Modalità di frammentazione del disco** Visualizza lo stato di frammentazione di tutti i dischi.

Questo strumento può essere usato per diagnosticare vari problemi o per assistere gli amministratori nella pianificazione della capacità. Ad esempio, se la maggior parte degli utenti ospitati nel server A sceglie gli utenti ospitati nel server B come contatti, l'amministratore può spostare gli utenti nel server A al server B per ridurre il traffico tra server.

### <a name="output"></a>Output

Questo strumento restituisce report predefiniti sul database Skype for Business Server 2015. **Percorso**: %ProgramFiles%\Skype for Business Server 2015\Reskit

### <a name="purpose"></a>Finalità

Per installare Dbanalyze.exe, copiarlo in una cartella locale e quindi eseguire lo strumento. Per usare lo strumento, eseguire il comando seguente dalla riga di comando. `dbanalyze.exe [/v] [/report:value] [/sqlserver:value] [/user:user@domain.com] [/conf:value][/pstnid:Value] [/maxcontacts:value]` Di seguito sono riportate le descrizioni per le opzioni della riga di comando.

![Opzioni della riga di comando per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image35.JPG)

### <a name="requirements"></a>Requisiti

 **Computer** DBAnalyze può essere eseguito solo da un computer aggiunto a un dominio in cui è installato Skype for Business Server 2015.

 **Rete** Il computer deve essere in grado di connettersi al database back-end.

 **I componenti software** Skype for Business Server 2015 devono essere installati prima di eseguire DBAnalyze.

 **Gli utenti** La tabella seguente mostra gli amministratori che dispongono delle autorizzazioni necessarie per accedere ai database Skype for Business Server 2015.

![Tabella delle autorizzazioni per Dbanalyze.exe.](../media/Reskit_2012_Tools_Documentation_Image36.JPG)

> [!NOTE]
> Per **la modalità /report:disk** è necessario un account amministratore locale.

### <a name="examples"></a>Esempi

Di seguito sono riportati alcuni esempi di comandi di Dbanalyze.exe validi:

```console
dbanalyze.exe /report:diag
dbanalyze.exe /report:user /user:usera@domainb.com
dbanalyze.exe /report:conf /user:bob@example.com /conf:1W9J71SKSX2X
dbanalyze.exe /report:resolve /pstnid:12345
dbanalyze.exe /report:mcus
dbanalyze.exe /report:disk
```

### <a name="summary"></a>Riepilogo

DBAnalyzer offre agli amministratori un'analisi rapida e semplice dei database Skype for Business Server 2015.

## <a name="import-storage-service-data"></a>Importare i dati del servizio Archiviazione
<a name="Issd"> </a>

Lo strumento Resource Kit ImportStorageServiceData consente di reimportare i dati di coda ed endpoint scaricati dal servizio Archiviazione (LYSS) nel servizio Archiviazione.

### <a name="description"></a>Descrizione

I dati scaricati dal servizio Archiviazione potrebbero essere stati automatici (periodici) in base allo stato dell'elemento della coda o alle dimensioni del database. Potrebbe essersi verificato a causa della chiamata manuale del cmdlet di failover del pool o del cmdlet StorageServiceFullFlush (richiamato dal cmdlet di failover del pool). Si noti che i dati idealmente non devono essere reimportati se una delle dimensioni del database del servizio Archiviazione (LYSS) nei front-end è superiore al livello normale, perché in questo modo è probabile che vengano esportati di nuovo altri dati. Inoltre, eventuali problemi che potrebbero aver contribuito a causare errori che hanno causato l'aumento della coda del servizio Archiviazione devono essere risolti prima di tutto, ad esempio Exchange errori dell'endpoint, problemi di rete o altri problemi.

 **Scenario 1:** durante il failover del pool, i file possono essere scaricati dal servizio di archiviazione per ogni front-end. Al termine del failover, è necessario eseguire lo strumento per reimportare i dati.

 **Scenario 2:** i dati vengono scaricati automaticamente ogni giorno o in risposta a Archiviazione database del servizio che supera determinate soglie di dimensioni (ad esempio 60%, 80%, 90% pieno). Questi dati scaricati automaticamente devono essere reimportati regolarmente dall'amministratore. Nella situazione precedente, se il pacchetto SCOM di monitoraggio non viene distribuito, sono presenti eventi per Skype for Business Server Archiviazione Servizio relativi ai dati scaricati dal servizio Archiviazione. ID evento 32075 (operazione di scaricamento completo avviata), 32076 (scaricamento completo completato), 32082 (scaricamento livello di manutenzione avviato), 32083 (scaricamento livello di manutenzione completato), 32089 (scaricamento dovuto al riempimento del database). Si noti che questi ID evento corrispondono alla versione RTM. Quando un amministratore visualizza questi eventi, significa che sono presenti file che sono stati scaricati. Questi dati devono essere regolarmente importati usando questo strumento, ad esempio una volta alla settimana.

Per la versione del servizio online, se viene distribuito il pacchetto SCOM di monitoraggio dell'integrità per Skype for Business Server, è possibile che vengano generati nuovi avvisi che chiedono all'amministratore di reimportare i dati scaricati nuovamente nel servizio Archiviazione. Nel registro eventi nel server Front-End che ha attivato l'avviso sarà presente un evento corrispondente. L'evento fornirà una descrizione del percorso padre in cui si trovano i file di dati scaricati e del numero di file che soddisfano i criteri di avviso. I criteri di avviso prevedono che siano presenti X o più file nel percorso padre specifico che hanno almeno Y giorni precedenti (dove X e Y sono preimpostati all'interno di StorageService, ma possono essere sostituiti modificando il file APPCONFIG). Di seguito sono riportati due esempi di eventi che possono attivare l'avviso di integrità, con la differenza che si tratta del percorso padre. Una possibilità è nella condivisione file del servizio Web, mentre l'altra è la directory application data locale di ogni front-end. (ad esempio c:\ProgramData\Microsoft\Skype for Business Server 2015\StorageService). L'amministratore eseguirà quindi questo strumento reskit.

Questo strumento aumenterà il carico di CPU e I/O sul front-end su cui è in esecuzione e su altri front-end, nel caso in cui i dati non siano di proprietà del front-end in cui viene eseguito lo strumento. È consigliabile eseguire questo strumento quando i front-end non sono sottoposti a un carico elevato di CPU e I/O, ad esempio al di fuori delle ore di punta. In secondo luogo, questo strumento può da 2 a 3 minuti per importare un file di dati. Tenere presente questo aspetto quando si stima per quanto tempo lo strumento sarà in esecuzione. Il file di log dettagliato generato dallo strumento verrà visualizzato per impostazione predefinita nell'archivio file. Eliminarlo se non sono stati segnalati errori, perché il file di log può essere di decine di MB o più.

![Eventi di esempio del registro eventi Archiviazione Server.](../media/Reskit_2012_Tools_Documentation_Image1.jpg)

### <a name="requirements"></a>Requisiti

Installare gli strumenti Skype for Business Server Resource Kit 2015. Lo strumento viene eseguito in computer aggiunti a un dominio in cui sono installati Skype for Business Server e Skype for Business Server Management Shell. Lo strumento usa un cmdlet dalla shell di gestione per identificare tutti i server Front-End nel pool. In secondo luogo, lo strumento deve essere eseguito da un computer nel pool in cui è installato il database **RtcLocal** . Questo database viene usato dallo strumento per recuperare il percorso della condivisione file WEBSERVICE per il pool. Inoltre, prima di usare lo strumento, ogni server Front-End deve prima abilitare Windows PowerShell comunicazione remota tramite **Enable-PSRemoting** in ogni server Front-End e il computer da cui viene eseguito lo strumento. In caso contrario, i comandi Windows PowerShell remoti di questo strumento avranno esito negativo. Windows PowerShell comunicazione remota può essere disattivata in tutti i server Front-End nel pool al termine. Infine, l'account o le credenziali che richiamano lo strumento devono disporre dell'autorizzazione di lettura/scrittura per la condivisione file del servizio Web per il pool in cui esegue questo strumento. In caso contrario, lo strumento avrà esito negativo con errori di autorizzazione I/O.

> [!NOTE]
> In Windows Server 2012 Windows PowerShell comunicazione remota è abilitata per impostazione predefinita, ma non nel sistema operativo Windows Server 2008.

### <a name="examples"></a>Esempi

```console
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

Lo strumento LCSSync consente di distribuire Skype for Business Server software di comunicazione 2015 in un ambiente a più foreste. Questo strumento viene usato per sincronizzare utenti e gruppi da foreste utente diverse come oggetto contatto Active Directory Domain Services a una foresta centrale in cui è installato Skype for Business Server 2015.

### <a name="description"></a>Descrizione

 LCSSync usa gli oggetti contatto Active Directory Domain Services sincronizzati nella foresta centrale per consentire agli utenti di Skype for Business Server. Per fornire l'accesso Single Sign-In, è necessario eseguire il mapping dell'account utente primario all'oggetto contatto Active Directory Domain Services nella foresta centrale per Skype for Business Server 2015. Questo strumento consente di eseguire tale mapping. Questo strumento fornisce modelli per la creazione di agenti di gestione in Microsoft Identity Integration Server.

### <a name="summary"></a>Riepilogo

Lo strumento LCSSync consente di distribuire Skype for Business Server 2015 in un ambiente a più foreste.

## <a name="lookup-user-console"></a>Console utente ricerca
<a name="LUC"> </a>

Lo strumento LookupUserConsole visualizza informazioni di routing Skype for Business Server interne su utenti specifici. Queste informazioni possono essere utili per il supporto personale di Microsoft nella diagnosi dei problemi di distribuzione e routing.

### <a name="description"></a>Descrizione

 L'esecuzione di LookupUserConsole.exe aprirà un prompt dei comandi che accetta gli indirizzi SIP e tenta di visualizzare le informazioni di routing Skype for Business Server interne correlate. Digitare **exit** per uscire dallo strumento LookupUserConsole.

### <a name="requirements"></a>Requisiti

Installare Skype for Business Server Resource Kit 2015. Lo strumento viene eseguito in computer aggiunti a un dominio in cui è installato Skype for Business Server.

### <a name="examples"></a>Esempi

C:\Programmi\Skype for Business Server 2015\ResKit\>LookupUserConsole.exe

```console
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

Lo strumento MSTurnPing consente a un amministratore di Skype for Business Server software di comunicazione 2015 di controllare lo stato dei server che eseguono i servizi Audio/Video Edge, Audio/Video Authentication e i server che eseguono Servizi criteri larghezza di banda nella topologia.

### <a name="description"></a>Descrizione

Lo strumento MSTurnPing consente a un amministratore di Skype for Business Server software di comunicazione 2015 di controllare lo stato dei server che eseguono i servizi Audio/Video Edge, Audio/Video Authentication e i server che eseguono Servizi criteri larghezza di banda nella topologia.

Lo strumento consente all'amministratore di eseguire i test seguenti:

1. Test A/V Edge Server: lo strumento esegue test su tutti i server A/V Edge nella topologia eseguendo le operazioni seguenti:

   - Verifica che il servizio di autenticazione audio/video Skype for Business Server sia avviato e possa emettere credenziali appropriate.

   - Verifica dell'avvio del servizio Skype for Business Server Audio/Video Edge e può allocare correttamente le risorse nel perimetro esterno.

2. Test del servizio criteri di larghezza di banda: lo strumento esegue test su tutti i server che eseguono i servizi criteri di larghezza di banda nella topologia eseguendo le operazioni seguenti:

   - Verificare che l'Skype for Business Server Servizio criteri larghezza di banda (autenticazione) sia avviato e possa emettere credenziali appropriate.

   - Verifica che l'Skype for Business Server Bandwidth Policy Service (Core) sia avviato e possa eseguire correttamente il controllo della larghezza di banda.

Questo strumento deve essere eseguito da un computer che fa parte della topologia e in cui è installato l'archivio locale.

### <a name="output"></a>Output

Lo strumento restituisce i risultati di ognuna delle operazioni.

- Se viene eseguito il test **AudioVideoEdgeServer** , gli output dello strumento sono i seguenti:

  - Risultati dei test dei computer che forniscono il servizio di autenticazione audio/video Skype for Business Server 2015 nella topologia

  - Risultati dei test dei computer che forniscono il servizio Skype for Business Server Audio/Video Edge 2015 nella topologia

- Se viene eseguito il test **BandwidthPolicyServer** , gli output dello strumento sono i seguenti:

  - Risultati dei test dei computer che forniscono il servizio criteri di larghezza di banda (autenticazione) Skype for Business Server 2015 nella topologia

  - Risultati dei test dei computer che forniscono il servizio criteri di larghezza di banda (Core) Skype for Business Server 2015 nella topologia

### <a name="requirements"></a>Requisiti

- Questo strumento deve essere eseguito da un computer che si trova nella topologia e che ha l'archivio locale.

- Lo strumento deve essere eseguito come amministratore che ha accesso all'archivio locale.

### <a name="examples"></a>Esempi

Di seguito è riportato un esempio dell'input dello strumento.

```console
MsTurnPing -ServerRole AudioVideoEdgeServer

MsTurnPing -ServerRole BandwidthPolicyServer
```

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per Skype for Business Server amministratori del 2015 che vogliono controllare lo stato dei server che eseguono servizi di criteri audio/video e larghezza di banda.

## <a name="network-configuration-viewer"></a>Visualizzatore configurazione di rete
<a name="NCV"> </a>

Network Configuration Viewer può essere usato dagli amministratori del software di comunicazione di Skype for Business Server 2015 per visualizzare la topologia di rete del controllo di ammissione di chiamata per un'azienda di cui viene effettuato il provisioning per consentire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o videochiamate in base alla capacità di larghezza di banda specificata. Skype for Business Server 2015 gli amministratori definiscono i criteri di controllo di ammissione di accesso, applicati dai servizi criteri di larghezza di banda installati con Skype for Business Server 2015.

### <a name="description"></a>Descrizione

Network Configuration Viewer (NetworkConfigurationViewer.exe) consente agli amministratori di eseguire le attività seguenti:

- Caricare e visualizzare la topologia di rete di Controllo di ammissione di controllo di accesso da una distribuzione Skype for Business Server 2015 in un formato grafico.

- Caricare e visualizzare la topologia di rete cac da un file di log del server dei criteri di larghezza di banda in un formato grafico.

- Salvare e archiviare la topologia di rete cac in un formato XML sul disco.

- Salvare e archiviare il diagramma della topologia di rete cac in formato JPG o BMP.

- Visualizzare i dati di configurazione della topologia di rete di Controllo di ammissione di controllo di accesso.

- Visualizzare la topologia di rete cac in uno stile di visualizzazione albero.

- Definire connettori personalizzati per i collegamenti di topologia di rete di Controllo di ammissione di controllo di accesso(ad esempio, collegamenti da sito a area, da area a area e da sito a sito).

- Visualizzare le informazioni sul sito della topologia di rete del servizio Di controllo di ammissione di accesso, le informazioni sull'area e i criteri di larghezza di banda di cui è stato effettuato il provisioning e i collegamenti di rete.

### <a name="purpose"></a>Finalità

Visualizzare i collegamenti alla topologia di rete di Controllo di ammissione di accesso aziendale in un'interfaccia grafica.

### <a name="examples"></a>Esempi

 **Caricare e visualizzare la topologia di rete di Controllo di ammissione di controllo di accesso da una distribuzione di Skype for Business Server 2015 in un formato grafico**: Skype for Business Server 2015 gli amministratori possono caricare e visualizzare la **configurazione della topologia di rete del servizio di controllo di accesso in qualsiasi computer Skype for Business Server 2015 usando Scaricare l'opzione Configurazione di rete** come illustrato nella figura seguente. Lo strumento non riuscirà a scaricare o visualizzare tale configurazione quando viene distribuito in un computer che non ha connettività all'archivio di configurazione Skype for Business Server 2015.

![Download della configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image23.jpg)

 **Caricare e visualizzare la topologia di rete di Controllo di accesso condiviso da un file di log del server Criteri di larghezza di banda in un formato grafico:** Skype for Business Server server Criteri di larghezza di banda 2015 salva la topologia di rete del servizio Di controllo di accesso condiviso come parte del meccanismo di registrazione nel percorso di condivisione file Skype for Business Server 2015. Skype for Business Server gli amministratori di 2015 possono visualizzare tale file in formato grafico usando l'opzione **Apri configurazione di rete**, come illustrato di seguito.

![Apertura di un file di log del server dei criteri di larghezza di banda.](../media/Reskit_2012_Tools_Documentation_Image24.jpg)

Salvare e archiviare la topologia di rete cac in un formato XML sul disco: gli amministratori di Skype for Business Server 2015 possono salvare il file di configurazione della topologia di rete del Servizio di controllo di ammissione di chiamata in un formato XML usando l'opzione **Salva una copia di Configurazione di rete**, come illustrato di seguito. Il file di configurazione salvato può quindi essere usato offline per scopi di visualizzazione grafica.

![Salvataggio della configurazione di rete come file XML.](../media/Reskit_2012_Tools_Documentation_Image25.jpg)

Salvare e archiviare il diagramma della topologia di rete CAC in formato JPG o BMP: Skype for Business Server 2015 gli amministratori possono salvare la configurazione della topologia di rete di Controllo di ammissione di chiamata in un formato grafico (formati di file JPG e BMP) usando l'opzione **Salva diagramma configurazione di rete come immagine**, come illustrato di seguito.

![Salvataggio della configurazione di rete come immagine.](../media/Reskit_2012_Tools_Documentation_Image26.jpg)

 <strong>Visualizzare i dati di configurazione della topologia di rete di Controllo</strong> di ammissione di controllo di accesso: gli amministratori di Skype for Business Server 2015 possono visualizzare i dati di configurazione di rete correlati, ad esempio aree di rete, siti di rete, profili di larghezza di banda e indirizzi IP della subnet del sito in formato testuale usando l'opzione Visualizza dati di configurazione di rete, come illustrato di seguito.

![Visualizzazione dei dati di configurazione di rete.](../media/Reskit_2012_Tools_Documentation_Image27.jpg)

 **Visualizzare la topologia di rete cac in uno stile di visualizzazione ad albero:** Skype for Business Server gli amministratori di 2015 possono visualizzare i dati di configurazione di rete correlati in uno stile di visualizzazione ad albero grafico usando il pannello di controllo sul lato sinistro della finestra degli strumenti, come illustrato di seguito.

![Visualizzazione dei dati di configurazione di rete in una visualizzazione albero.](../media/Reskit_2012_Tools_Documentation_Image28.jpg)

 **Definire connettori personalizzati per i collegamenti di topologia di rete di Controllo di ammissione di controllo di accesso (ad esempio collegamenti da sito a area, da area a area e da sito a sito):** gli amministratori di Skype for Business Server 2015 possono definire connettori grafici personalizzati per i collegamenti WAN di configurazione di rete di Controllo di ammissione di accesso tramite l'opzione Impostazioni, come illustrato di seguito. Ciò consente di distinguere tra i vari tipi di collegamenti di rete di cui viene effettuato il provisioning nella configurazione di rete.

![Strumenti.](../media/Reskit_2012_Tools_Documentation_Image29.jpg)

 **Visualizzare le informazioni sul sito della topologia di rete del servizio Di controllo di ammissione di controllo di accesso, le informazioni sull'area e i criteri di larghezza di banda di cui è stato effettuato il provisioning:** Skype for Business Server 2015 gli amministratori possono visualizzare le informazioni correlate sull'area di rete, le informazioni sul sito e le informazioni sul provisioning della larghezza di banda del servizio Di controllo di ammissione di accesso tramite le opzioni illustrate di seguito. Ad esempio, fare clic su **Info** in un'area di rete o in un oggetto sito di rete.

![Definizione di connettori personalizzati per la rete.](../media/Reskit_2012_Tools_Documentation_Image30.jpg)

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per Skype for Business Server amministratori del 2015 che desiderano visualizzare la topologia di rete del servizio di controllo di accesso per la distribuzione in un formato grafico.

## <a name="response-group-agent-live"></a>Response Group Agent Live
<a name="RGAL"> </a>

L'applicazione Response Group offre agli agenti la possibilità di accedere a informazioni utili in tempo reale usando il servizio Web predefinito. Sfortunatamente, non è disponibile alcuna visualizzazione grafica di questi dati all'esterno dell'applicazione. Lo strumento Response Group Agent Live Resource Kit risolve questo problema fornendo un modo semplice e grafico per accedere a queste informazioni, migliorato con informazioni software di comunicazione Skype for Business in tempo reale, ad esempio la presenza di altri agenti.

### <a name="description"></a>Descrizione

Response Group Agent Live è un'applicazione Windows che fornisce funzionalità di accesso e disconnessione e alcune informazioni in tempo reale (ad esempio l'appartenenza al gruppo e il numero corrente di chiamate) agli agenti di Response Group. Si tratta di una versione avanzata della pagina Gruppi di agenti (accessibile da Skype for Business.

### <a name="purpose"></a>Finalità

L'applicazione Response Group accoda le chiamate in ingresso e quindi le indirizza ai gruppi di agenti. Per prendere decisioni informate sulle chiamate al servizio, gli agenti possono accedere a informazioni in tempo reale sui gruppi di agenti, ad esempio quali altri agenti sono disponibili e quante chiamate sono in attesa in ogni coda. Queste informazioni, inizialmente accessibili solo tramite il servizio Response Group, vengono rese disponibili in modo intuitivo da Response Group Agent Live.

#### <a name="features"></a>Funzionalità

Lo strumento Response Group Agent Live si basa sul servizio Response Group e sull'SDK Skype for Business Server 2015. Fornisce agli agenti di Response Group le informazioni e le funzionalità disponibili dal servizio Response Group, ad esempio l'appartenenza al gruppo, la presenza di altri agenti e il numero di chiamate in attesa.

La figura seguente illustra l'interfaccia principale di Response Group Agent Live.

![Strumento Response Group Agent Live.](../media/Reskit_2012_Tools_Documentation_Image37.JPG)

Le tre funzionalità principali seguenti sono disponibili per gli agenti in Response Group Agent Live:

- **Accesso/uscita:** Contrariamente alla pagina Gruppi di agenti (accessibile da Skype for Business Server 2015), Response Group Agent Live consente solo agli agenti di accedere o uscire da tutti i gruppi di agenti contemporaneamente. Questa applicazione offre tre modi rapidi per consentire agli agenti di accedere o uscire:

  - Fare clic sui pulsanti Di accesso/uscita (verde e rosso) all'interno dell'applicazione.

  - Fare clic con il pulsante destro del mouse sull'icona della barra degli strumenti di sistema e selezionare Accedi o disconnettersi.

  - Uso di tasti di scelta rapida configurabili.

- **Appartenenza a gruppi:** Quando si seleziona un gruppo di agenti, Response Group Agent Live visualizza l'elenco degli agenti in questo gruppo nel riquadro destro. Se Skype for Business Server 2015 è in esecuzione nello stesso computer dell'applicazione, le informazioni sulla presenza e la scheda contatto vengono visualizzate in Response Group Agent Live. Gli agenti possono inviare un messaggio istantaneo o chiamare altri agenti direttamente da questa istanza.

- **Statistiche in tempo reale:** Response Group Agent Live fornisce statistiche in tempo reale per tutti i gruppi di agenti. La frequenza di aggiornamento è di un minuto. Quando un Response Group risponde a una chiamata, viene aggiunto un indicatore visivo accanto al nome del gruppo con il numero corrente di chiamate in coda. Se si sospende il puntatore su un gruppo, viene visualizzato anche il tempo di attesa più lungo.

### <a name="requirements"></a>Requisiti

Response Group Agent Live richiede .NET Framework 4.0. Inoltre, per sfruttare le funzionalità di presenza e scheda contatto, Skype for Business devono essere installate in locale (ed essere in esecuzione).

#### <a name="configuration"></a>Configurazione

Response Group Agent Live può essere personalizzato in base alle singole preferenze usando la finestra di dialogo Opzioni nell'applicazione. Inoltre, l'amministratore può definire l'indirizzo host predefinito modificando direttamente la proprietà defaultHostAddress del file RGAgentLive.exe.config.

La figura seguente illustra la finestra di dialogo Opzioni che gli agenti possono usare per configurare l'indirizzo host e i tasti di scelta rapida. Per accedere a questa finestra di dialogo, fare clic sul pulsante Opzioni in alto a destra dell'interfaccia principale.

![Finestra di dialogo Opzioni dinamiche dell'agente di Response Group.](../media/Reskit_2012_Tools_Documentation_Image38.JPG)

Le tre diverse impostazioni seguenti possono essere personalizzate nella configurazione di Response Group Agent Live:

- Indirizzo host: si tratta in genere del nome di dominio completo del pool Web appartenente al pool home dell'agente. L'indirizzo esatto del servizio Response Group viene derivato automaticamente in background da queste informazioni (aggiungendo il percorso corretto dopo l'host).

- Collegamenti: i collegamenti esatti per l'accesso/uscita possono essere personalizzati. L'unica limitazione è che entrambi i tasti di scelta rapida devono contenere il tasto "Windows Logo" (oltre ad almeno un altro tasto).

- Iniziare con Windows: l'applicazione può essere configurata per l'avvio automatico con Windows.

### <a name="examples"></a>Esempi

La figura seguente illustra come chiamare o inviare un messaggio istantaneo a un altro agente facendo clic con il pulsante destro del mouse sul contatto nel riquadro destro.

![Effettuare una chiamata o inviare un messaggio istantaneo.](../media/Reskit_2012_Tools_Documentation_Image39.JPG)

La figura seguente illustra come Response Group Agent Live visualizza il numero corrente di chiamate nella coda e il tempo di attesa più lungo tra tutte queste chiamate in ingresso.

![Visualizzazione delle informazioni sulla coda.](../media/Reskit_2012_Tools_Documentation_Image40.JPG)

### <a name="summary"></a>Riepilogo

L'accesso rapido e la disconnessione, l'appartenenza ai gruppi e le statistiche di base in tempo reale sono interessanti funzionalità dell'agente di Response Group disponibili solo all'esterno dell'applicazione dal servizio Response Group. Con lo strumento Response Group Agent Live Resource Kit, gli amministratori di Skype for Business Server 2015 possono fornire ai propri agenti un'applicazione Windows che consente loro di eseguire le attività in modo più rapido e grafico.

## <a name="sefautil"></a>SEFAUtil
<a name="SEFAUtil"> </a>

SEFAUtil (attivazione delle funzionalità dell'estensione secondaria) è uno strumento da riga di comando che consente agli amministratori del software di comunicazione e agli agenti helpdesk di Skype for Business Server 2015 di configurare la chiamata di delegati, l'inoltro di chiamata, il squillo simultaneo, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di un utente di Skype for Business Server 2015. Lo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente. Lo strumento SEFAUtil consente all'amministratore di abilitare/disabilitare/modificare l'inoltro di chiamata o di squillare simultaneamente per conto dell'utente. L'amministratore può specificare la destinazione (sotto forma di URI SIP) o usare una destinazione già pubblicata dall'utente. Questo strumento consente inoltre agli amministratori di aggiungere o rimuovere delegati o membri del gruppo di chiamate del team per conto dell'utente. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3.0 e richiede che gli amministratori creino un'applicazione attendibile nell'archivio di gestione centrale per SEFAUtil.

SEFAUtil (attivazione delle funzionalità dell'estensione secondaria) consente agli amministratori e agli agenti helpdesk di Skype for Business Server 2015 di configurare la chiamata ai delegati, l'inoltro di chiamata, la chiamata simultanea, le impostazioni di chiamata del team e il ritiro delle chiamate di gruppo per conto di un utente di Skype for Business Server 2015. Questo strumento consente inoltre agli amministratori di eseguire query sulle impostazioni di routing delle chiamate pubblicate per un determinato utente.

### <a name="description"></a>Descrizione

La versione corrente di SEFAUtil è solo uno strumento da riga di comando; non è disponibile un'interfaccia utente grafica di supporto. Questo strumento è basato su Microsoft Unified Communications Managed API (UCMA) 3.0. Le funzionalità di questo strumento consentono agli amministratori e agli agenti helpdesk di eseguire le operazioni seguenti:

- Visualizzare tutte le impostazioni di routing delle chiamate per un utente (inclusi inoltro di chiamata, delega, squillo simultaneo, chiamata in team e ritiro delle chiamate di gruppo)

- Abilitare/disabilitare/modificare l'impostazione di inoltro di chiamata (include il timer di destinazione e senza risposta)

- Abilitare/disabilitare/modificare configurazioni immediate di inoltro di chiamata

- Abilitare/disabilitare/modificare le impostazioni di delega

- Abilitare/disabilitare/modificare le impostazioni del gruppo di chiamate del team

    > [!NOTE]
    > Novità dello strumento SEFAUtil di Skype for Business Server 2015

- Abilitare/disabilitare/modificare le impostazioni di squillo simultanee (include la destinazione)

    > [!NOTE]
    > Novità dello strumento SEFAUtil di Skype for Business Server 2015

- Abilitare/disabilitare/modificare le impostazioni di ritiro delle chiamate di gruppo

    > [!CAUTION]
    > Novità dello strumento SEFAUtil di Skype for Business Server 2015

Questo strumento presenta le limitazioni seguenti:

- Supportato solo per gli utenti ospitati in un pool di Skype for Business Server

- La modifica in blocco delle impostazioni di routing delle chiamate per più utenti non è supportata

### <a name="output"></a>Output

La versione corrente di questo strumento fornisce l'output solo nella finestra del prompt dei comandi. Per informazioni dettagliate, vedere la sezione Esempi più avanti in questo documento.

### <a name="purpose"></a>Finalità

Di seguito sono riportati alcuni degli scenari principali in cui è possibile usare questo strumento:

- Bob è un dirigente ed è stato spostato nella telefonia Skype for Business Server. Ha una delega sul suo sistema PBX esistente. Come parte del passaggio a Skype for Business Server 2015, l'amministratore è in grado di configurare il routing di Bob in modo che rifletta la configurazione della delega preesistente.

- Alice è in viaggio e si rende conto che si aspetta una chiamata importante da uno dei suoi clienti. Tuttavia, lei è in un hotel e non ha accesso a un computer. Chiama l'helpdesk e richiede che inoltrano al suo numero di cellulare tutte le chiamate effettuate al suo numero di lavoro. Il personale del supporto tecnico è in grado di eseguire la configurazione per suo conto.

- Le chiamate di Joe al suo numero di lavoro stanno andando alla sua segreteria telefonica mobile ogni volta che è al lavoro; tuttavia, le cose sembrano funzionare correttamente nella maggior parte delle altre posizioni. Il tecnico del supporto tecnico è in grado di visualizzare la configurazione di routing di Joe e scopre che Joe ha la chiamata simultanea configurata per il suo telefono cellulare. Il tecnico chiede a Joe circa la copertura mobile nel suo ufficio ed è in grado di determinare che la regola di squillo simultaneo è ciò che sta causando le chiamate per andare alla segreteria telefonica mobile di Joe quando la sua copertura di rete è scarsa.

- Mike è un nuovo dipendente di Contoso e si sta unendo a un nuovo team in cui tutti i membri sono configurati per la chiamata al team, quando viene abilitato per Skype for Business Server 2015, l'amministratore è in grado di impostare le impostazioni del gruppo di chiamate del team in modo da includere tutti i nuovi membri del team, inoltre, l'amministratore aggiunge Mike come membro del gruppo di chiamate al team per ognuno dei membri del suo team.

- Una pratica del servizio clienti nel reparto risorse umane di Contoso consiste nel fornire un servizio personale per tutti i chiamanti dalla prima chiamata. Dato che tutti i membri del reparto siedono molto vicini l'uno all'altro, avere tutti i telefoni squillare allo stesso tempo con la chiamata al team è dirompente per il team. Per offrire il servizio migliore senza interrompere i membri del team, l'amministratore di Skype for Business Server 2015 sfrutta la funzionalità di ritiro delle chiamate di gruppo. L'amministratore aggiunge tutti i membri del reparto a un gruppo di ritiro e comunica al reparto il numero del gruppo di ritiro. Quando Samantha è assente dalla sua scrivania, Joe nota il suo telefono squillare e lui continua a rispondere alla chiamata dalla sua scrivania.

### <a name="requirements"></a>Requisiti

Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. UCMA 3.0 deve essere installato in tale computer. Per eseguire lo strumento, è necessario creare una nuova applicazione attendibile con l'ID applicazione SEFAUtil in tale pool.

### <a name="creating-a-new-trusted-application-for-the-sefautil-tool"></a>Creazione di una nuova applicazione attendibile per lo strumento SEFAUtil

1. Lo strumento SEFAUTil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile. Se necessario, l'aggiunta di un pool come nuovo pool di applicazioni attendibili può essere eseguita tramite Skype for Business Server Management Shell con il cmdlet seguente:

   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

    > [!NOTE]
    > UCMA 3.0 deve essere installato in qualsiasi computer che verrà usato per eseguire lo strumento SEFAUtil.

2. È necessario definire un'applicazione attendibile nella topologia per lo strumento SEFAUtil. Per definire SEFAUtil come nuova applicazione attendibile, usare Skype for Business Server Management Shell ed eseguire il cmdlet seguente:

   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN> -Port 7489
   ```

    > [!NOTE]
    > Se necessario, è possibile usare una porta diversa.
    
    > [!NOTE]
    > FQDN pool: fqdn del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un Skype for Business server Front End > o un pool).
    > FQDN del registrar del pool: nome di dominio completo del server front-end o del pool di Skype for Business associato al pool di applicazioni.
    > Sito pool: ID sito del sito in cui si trova il pool.

3. Le modifiche alla topologia devono essere abilitate. L'abilitazione delle modifiche della topologia può essere eseguita tramite Skype for Business Server Management Shell eseguendo il cmdlet seguente:

   ```powershell
   Enable-CsToplogy
   ```

4. Se necessario, installare il Skype for Business Server Strumenti resource kit 2015 nel server che verrà usato per eseguire lo strumento SEFAUtil (il server deve far parte di un pool di applicazioni attendibile).

5. Verificare che SEFAUtil sia in esecuzione correttamente. A tale scopo, eseguire lo strumento da un prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione. Per impostazione predefinita, lo strumento si trova in: "...\Programmi\Skype for Business Server 2015\Reskit". Per visualizzare le impostazioni di inoltro di chiamata di un utente, usare il comando seguente:

   ```console
   SEFAUtil.exe <user SIP address> /server:<Skype for Business Server/Pool FQDN>
   ```

    Devono essere visualizzate le impostazioni di inoltro di chiamata dell'utente.

#### <a name="group-call-pickup"></a>Risposta alle chiamate di gruppo

Il ritiro delle chiamate di gruppo richiede una configurazione aggiuntiva in Skype for Business Server 2015 per consentire l'abilitazione completa della funzionalità. Prima di assegnare gruppi di ritiro agli utenti, fare riferimento alla documentazione del prodotto Group Call Pickup per i passaggi di pianificazione e distribuzione di questa funzionalità.

### <a name="examples"></a>Esempi

#### <a name="display-current-call-handling-settings"></a>Visualizzare i Impostazioni di gestione delle chiamate correnti

Il comando seguente visualizza la gestione delle chiamate per l'utente.  `SEFAUtil.exe /server:SfBS2015server.contoso.com katarina@contoso.com`

> [!NOTE]
> In questo esempio viene utilizzata l'opzione **/server** per specificare il Skype for Business Server a cui connettersi.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:20
Call Forward No Answer to: voicemail
```

#### <a name="set-the-call-forwardno-answer-destination"></a>Impostare l'inoltro di chiamata/Nessuna destinazione di risposta

In questo esempio vengono impostati la destinazione di inoltro di chiamata/nessuna risposta e il ritardo dell'anello. In questo caso, l'opzione /server non viene fornita; SEFAUtil tenta di individuare automaticamente il Skype for Business Server 2015.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablefwdnoanswer /callanswerwaittime:30 /setfwddestination:+14255550126@contoso.com;user=phone
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="enable-call-forwarding-immediately"></a>Abilitare immediatamente l'inoltro di chiamata

Questo esempio abilita immediatamente l'inoltro di chiamata a un altro utente.

```console
SEFAUtil.exe sip:katarina@contoso.com /enablefwdimmediate /setfwddestination:anders@contoso.com
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Forward immediate to: sip:anders@contoso.com
```

#### <a name="disable-call-forwarding-immediately"></a>Disabilitare immediatamente l'inoltro di chiamata

Questo esempio disabilita immediatamente l'inoltro di chiamata.

```console
SEFAUtil.exe /server:SfBserver.contoso.com katarina@contoso.com /disablefwdimmediate
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-user-as-a-delegate-and-set-up-simultaneous-ringing-of-delegates"></a>Aggiungere un utente come delegato e configurare il squillo simultaneo dei delegati

In questo esempio viene aggiunto un utente come delegato e viene impostato il squillo simultaneo dei delegati.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:joe@contoso.com /simulringdelegates
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simultaneously Ringing Delegates: sip:joe@contoso.com
```

#### <a name="change-simultaneous-ringing-rule-of-delegates"></a>Modificare la regola di squillo simultaneo dei delegati

In questo esempio la regola di squillo simultaneo impostata nell'esempio precedente viene modificata in base alla regola di squillo ritardata.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringdelegates:10
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
Delay Ringing Delegates (delay:10 seconds): sip:joe@contoso.com
```

#### <a name="remove-the-delegate"></a>Rimuovere il delegato

In questo esempio viene rimosso il delegato.

> [!NOTE]
> Quando l'ultimo delegato viene rimosso, il ringing dei delegati viene disabilitato automaticamente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removedelegate:joe@contoso.com
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-delegate-and-set-up-the-call-forward-to-delegates-rule"></a>Aggiungere un delegato e configurare la regola Call-Forward ai delegati

In questo esempio viene aggiunto un delegato e viene impostata la regola di inoltro di chiamata ai delegati.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /adddelegate:anders@contoso.com /fwdtodelegates
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Forwarding calls to Delegates: sip:anders@contoso.com
```

#### <a name="enable-simultaneous-ringing-and-set-a-destination-number"></a>Abilitare la squillo simultaneo e impostare un numero di destinazione

In questo esempio viene abilitato l'squillo simultaneo e viene impostato un numero di destinazione di squillo simultaneo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /setsimulringdestination:+14255550126 /enablesimulring
```

> [!NOTE]
> Per modificare il numero di destinazione di squillo simultaneo di un utente che ha già abilitato la chiamata simultanea, mantenere il comando con l'opzione /enablesimulring, in caso contrario il numero di destinazione non verrà modificato.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: True
Simul_Ringing to: sip:+14255550126@contoso.com;user=phone
```

#### <a name="disable-simultaneous-ringing"></a>Disabilitare la squillo simultaneo

In questo esempio viene disabilitata la squillo simultaneo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablesimulring
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Simulring enabled: False
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="add-a-team-member-for-team-call-and-set-up-simultaneous-ringing-to-the-team-call-members-group"></a>Aggiungere un membro del team per Team-Call e configurare l'anello simultaneo al gruppo membri Team-Call

In questo esempio viene aggiunto un membro del team al gruppo di chiamate del team di un utente e viene abilitato il squillo simultaneo al gruppo di chiamate del team.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /addteammember:anders@contoso.com /simulringteam
```

> [!NOTE]
> L'aggiunta di un membro al gruppo di chiamate del team di un utente cambierà automaticamente i set di chiamate simultanee degli utenti per chiamare simultaneamente il gruppo di chiamate del team.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Team ringing enabled. Team: sip:anders@contoso.com
```

#### <a name="remove-a-member-from-the-team-call-group"></a>Rimuovere un membro dal gruppo Team-Call

In questo esempio viene rimosso un membro del team del gruppo di chiamate del team di un utente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /removeteammember:anders@contoso.com
```

> [!NOTE]
> Se il membro da rimuovere è l'unico membro del gruppo di chiamate del team, la chiamata simultanea al gruppo di chiamate del team verrà disabilitata automaticamente.

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="set-the-delayed-ring-to-the-team-call-group"></a>Impostare l'anello ritardato sul gruppo di Team-Call

In questo esempio l'anello ritardato viene modificato nell'impostazione dell'ora del gruppo di chiamate del team.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /delayringteam:5
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Delay Ringing Team (delay:5 seconds). Team: sip:anders@contoso.com
```

#### <a name="enable-team-call"></a>Abilitare Team-Call

In questo esempio viene abilitata la chiamata al team per un determinato utente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /simulringteam
```

> [!NOTE]
> Se il gruppo di chiamate del team dell'utente non dispone di membri, la chiamata al team non verrà abilitata.

 **Output**

#### <a name="disable-team-call"></a>Disabilitare Team-Call

In questo esempio viene disabilitata la chiamata al team per un determinato utente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disableteamcall
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
User Ring time: 00:00:30
Call Forward No Answer to: voicemail
```

#### <a name="enable-group-call-pickup-and-assign-a-pickup-group-to-a-user"></a>Abilitare il ritiro delle chiamate di gruppo e assegnare un gruppo di ritiro a un utente

In questo esempio viene assegnato un gruppo di pickup a un utente e viene abilitato il ritiro delle chiamate di gruppo.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /enablegrouppickup:199
```

 **Output**

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
Group Pickup Orbit: sip:199;phone-context=user-default@contoso.com;user=phone
```

#### <a name="disable-group-call-pickup"></a>Disabilitare il ritiro delle chiamate di gruppo

In questo esempio viene disabilitato il ritiro delle chiamate di gruppo per un determinato utente.

```console
SEFAUtil.exe /server:SfBserver.contoso.com sip:katarina@contoso.com /disablegrouppickup
```

> [!NOTE]
> Quando si disabilita il ritiro delle chiamate di gruppo per un utente, il numero di gruppo assegnato all'utente non viene mantenuto. Se successivamente si vuole riabilitare il ritiro delle chiamate di gruppo per l'utente, è necessario assegnare di nuovo il numero di gruppo con l'opzione /enablegrouppickup.

```console
User Aor: sip:katarina@contoso.com
Display Name: Katarina Larsson
UM Enabled: True
```

## <a name="sysprepps1"></a>SYSPrep.ps1
<a name="SYSPrep"> </a>

### <a name="description"></a>Descrizione

SYSPrep.ps1 è uno script Windows PowerShell che installerà i prerequisiti seguenti Skype for Business Server 2015 nel computer del sistema operativo Windows Server 2008.

- Microsoft .NET Framework 4.5

- Microsoft SQL Server Express

- Windows PowerShell versione 3.0

- Visual C++ 2010 Redistributable

- Aggiornamenti di Internet Information Server

- Windows Identity Foundation

- file di base Skype for Business Server 2015

  Anche se il nome dello script è simile allo strumento di preparazione del sistema per i sistemi operativi Microsoft Windows, sono diversi. Questo script installerà solo i prerequisiti necessari per Skype for Business Server 2015. Dopo aver installato questi prerequisiti, è possibile usare lo strumento Windows SYSPrep per creare un'immagine del server.

### <a name="requirements"></a>Requisiti

Prima di eseguire lo script SYSPrep.ps1, è necessario copiare i file dei prerequisiti in una cartella locale nel computer del sistema operativo Windows Server 2008 , ad esempio **D:\Setup**. Questa cartella deve includere anche una copia dei file Skype for Business Server 2015, in particolare **Setup.exe.** I file dei prerequisiti possono essere scaricati dai percorsi seguenti:


| **Prerequisito**                                | **Posizione**                                                            |
|:------------------------------------------------|:------------------------------------------------------------------------|
| Microsoft .NET Framework 4.5  <br/>             | <https://go.microsoft.com/?linkid=9816306>  <br/>                       |
| Microsoft SQL Server Express 2008 R2  <br/>     | <https://www.microsoft.com/download/details.aspx?id=23650>  <br/> |
| Windows PowerShell versione 3.0  <br/>           | <https://www.microsoft.com/download/details.aspx?id=34595>  <br/> |
| Visual C++ 2010 Redistributable  <br/>          | <https://support.microsoft.com/en-us/topic/the-latest-supported-visual-c-downloads-2647da03-1eea-4433-9aff-95f26a218cc0>  <br/>  |
| Aggiornamenti di Internet Information Server  <br/>      | <https://www.microsoft.com/download/details.aspx?id=34869>  <br/> |
| Windows Identity Foundation  <br/>              | <https://www.microsoft.com/download/details.aspx?id=17331>  <br/> |
| Skype for Business Server 2015 Setup.exe  <br/> | Copia da Skype for Business Server supporto 2015  <br/>                   |

### <a name="parameter"></a>Parametro

Il parametro **-SetupFolder** accetta come argomento il percorso della directory dei file dei prerequisiti

### <a name="examples"></a>Esempi

Per eseguire lo script SYSPrep.ps1 e installare i prerequisiti di Skype for Business Server 2015, eseguire il comando seguente da un prompt dei comandi con privilegi elevati:

```console
./SysPrep.PS1 -SetupFolder D:\Setup
```

## <a name="unassigned-number-announcements-migration"></a>Migrazione degli annunci di numeri non assegnati
<a name="UNAM"> </a>

Lo strumento Di migrazione annunci numeri non assegnati consente a un amministratore di Skype for Business Server 2015 di spostare la configurazione dei numeri non assegnati gestita dall'applicazione di annuncio da un Skype for Business Server o un pool di origine a una destinazione Skype for Business Server o pool.

### <a name="description"></a>Descrizione

Lo strumento di migrazione Annunci numeri non assegnati è uno script Windows PowerShell che sposta la configurazione dei numeri non assegnati gestita dall'applicazione di annuncio di un server o pool di origine in un server o un pool diverso.

Quando viene eseguito, lo script di migrazione Annunci numero non assegnato eseguirà le operazioni seguenti:

1. Spostare tutti i file audio usati dagli annunci di numeri non assegnati dell'applicazione di annuncio ospitata nel server o nel pool di origine nell'archivio file del server o del pool di destinazione.

    > [!NOTE]
    > I file audio vengono rimossi dal pool di origine dopo essere stati copiati nel pool di destinazione.

2. Spostare tutti gli annunci di numeri non assegnati configurati per l'applicazione di annuncio ospitata nel server o nel pool di origine nel server o nel pool di destinazione.

3. Riassegnare tutti gli intervalli di numeri non assegnati gestiti dall'applicazione di annuncio ospitata nel server o nel pool di origine al server o al pool di destinazione.

Dopo aver eseguito correttamente lo script, tutti gli intervalli di numeri non assegnati gestiti dall'applicazione di annuncio ospitata nel server o nel pool di origine verranno ora gestiti con la stessa configurazione dal server o dal pool di destinazione.

### <a name="output"></a>Output

Lo script **Move-CsAnnouncementConfiguration** indica nella finestra Skype for Business Server Management Shell da cui viene eseguito l'esito positivo o negativo dell'operazione di migrazione.

Se l'esecuzione dell'operazione viene interrotta da un errore, gli intervalli di numeri non assegnati spostati correttamente nella destinazione rimarranno nella destinazione in una forma operativa e il resto degli intervalli di numeri non assegnati di cui eseguire la migrazione rimarrà nell'origine e in una forma operativa. Per eseguire completamente la migrazione del resto della configurazione, eseguire di nuovo lo script dopo aver affrontato l'errore.

### <a name="purpose"></a>Finalità

Lo script di migrazione Annunci numeri non assegnati può essere usato nei tre scenari seguenti:

- **Migrazione delle impostazioni di configurazione a una nuova versione di Skype for Business Server:** Contoso sta eseguendo la migrazione a Skype for Business Server 2015 e come parte del processo di migrazione il Skype for Business Server  l'amministratore vuole spostare la configurazione dei numeri non assegnati gestita dall'applicazione di annuncio dalla distribuzione di Lync Server 2013 alla nuova distribuzione Skype for Business Server 2015. Per spostare le impostazioni di configurazione, l'amministratore Skype for Business Server usa lo strumento di migrazione Annunci numeri non assegnati.

- **Rollback di una distribuzione da Skype for Business Server 2015 a Lync Server 2013:** a causa di fattori imprevisti, Contoso deve eseguire il rollback della migrazione alla nuova distribuzione Skype for Business Server 2015. Per ridurre al minimo le interruzioni del servizio, l'amministratore Skype for Business Server usa lo strumento migrazione Annunci numeri non assegnati per eseguire il rollback della configurazione dalla distribuzione Skype for Business Server 2015 alla distribuzione di Lync Server 2013.

- **Spostamento di dati tra distribuzioni:** Contoso sta sostituendo tutti i server di un pool con server più recenti. La strategia consiste nel distribuire un nuovo pool di Skype for Business Server 2015, spostare tutti i dati dal vecchio al nuovo pool e quindi deprecato il pool precedente. Dopo aver distribuito il nuovo pool, viene usato lo strumento Migrazione annunci numeri non assegnati per spostare la configurazione dal pool precedente a quello nuovo.

#### <a name="requirements"></a>Requisiti

Di seguito sono riportati i requisiti principali necessari per eseguire correttamente lo strumento:

1. Lo script deve essere eseguito da un computer in cui è installato Skype for Business Server Management Shell.

2. L'applicazione di annuncio deve essere distribuita correttamente nel server o nei pool di origine e di destinazione Skype for Business.

#### <a name="move-csannouncementconfiguration-script"></a>script Move-CsAnnouncementConfiguration

Lo script Move-CsAnnouncementConfiguration richiede i due parametri descritti nella tabella seguente.

![Move-CsAnnouncementConfiguration parametri.](../media/Reskit_2012_Tools_Documentation_Image41.JPG)

### <a name="examples"></a>Esempi

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-lync-server-2013-pool-to-a-skype-for-business-server-2015-pool"></a>Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Lync Server 2013 a un pool di Skype for Business Server 2015

Questo esempio sposta gli annunci di numeri non assegnati dal pool di origine (Lync Server 2013) al pool di destinazione (Skype for Business Server 2015).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source LS2013Pool.contoso.com -Destination SfBS2015Pool.contoso.com
```

#### <a name="moving-the-unassigned-number-announcements-configuration-from-a-skype-for-business-server-2015-pool-to-a-lync-server-2013-pool"></a>Spostamento della configurazione degli annunci di numeri non assegnati da un pool di Skype for Business Server 2015 a un pool di Lync Server 2013

In questo esempio gli annunci di numeri non assegnati vengono spostati dal pool di origine (Skype for Business Server 2015) al pool di destinazione (Lync Server 2013).

```powershell
Move-CsAnnouncementConfiguration.ps1 -Source SfBS2015Pool.contoso.com -Destination LS2013Pool.contoso.com
```

## <a name="web-conf-data"></a>Dati web conf
<a name="WebConfData"> </a>

Web Conf Data Tool consente a un amministratore del software di comunicazione di Skype for Business Server 2015 di avere un maggiore controllo sui dati associati alle conferenze Web di un organizzatore. Gli scenari includono la possibilità di eliminare i dati delle riunioni di un utente specifico in base a criteri di timestamp.

### <a name="description"></a>Descrizione

Questo strumento consente all'amministratore di eseguire le operazioni seguenti:

1. Trovare tutti i dati delle conferenze Web associati a un singolo utente.

2. Eliminare tutti i dati delle conferenze Web associati a un singolo utente.

3. Eliminare tutti i dati delle conferenze Web associati a un singolo utente precedente a una determinata data.

4. Spostare tutti i dati delle conferenze Web associati a un singolo utente quando l'utente viene spostato da un pool a un altro.

  > [!NOTE]
  > Gli strumenti di Resource Kit per Lync Server 2010 supportarono lo spostamento di tutti i dati delle conferenze Web associati a un singolo utente quando l'utente viene spostato da un pool a un altro. Questa funzionalità è ora deprecata da questo strumento a favore del parametro **MoveConferenceData** . Per informazioni dettagliate su questo parametro, vedere il cmdlet [Move-CsUser](/powershell/module/skype/move-csuser?) .

Lo strumento elimina i dati delle riunioni solo per le riunioni inattive. Le riunioni attive (o le riunioni nelle sessioni) non possono essere eliminate.

Questo strumento deve essere eseguito da un computer che si trova nello stesso pool dell'utente di destinazione. L'utente i cui dati del contenuto della riunione vengono gestiti da questo strumento deve essere incluso nello stesso pool di utenti.

### <a name="output"></a>Output

Questo strumento restituisce i risultati di ognuna delle operazioni:

- Se viene eseguita una query, lo strumento restituisce l'elenco di tutte le cartelle di dati delle riunioni inattive con tale utente come organizzatore.

- Se viene eseguita un'eliminazione, lo strumento restituisce l'elenco di tutte le cartelle di dati delle riunioni i cui dati verranno eliminati.

### <a name="requirements"></a>Requisiti

Lo strumento deve essere eseguito nello stesso pool in cui è attualmente ospitata l'organizzatore.

Lo strumento deve essere eseguito usando privilegi di amministratore con accesso all'archivio file di contenuto.

### <a name="examples"></a>Esempi

Nella tabella seguente vengono descritti i parametri, alcuni dei quali vengono usati negli esempi.

![Parametri di Web Conf Data Tool.](../media/Reskit_2012_Tools_Documentation_Image51.JPG)

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:query ""/ExpirationDate:08/09/2010 12:00:00""
```

Nell'esempio precedente viene illustrato il funzionamento di un comando di query. L'output di un comando di questo tipo sarebbe un elenco di tutte le cartelle del contenuto delle riunioni interessate da questo strumento.

```console
WebConfDataTool.exe /User:user0@contoso.com /Action:delete
```

L'esempio precedente è un esempio di comando delete. Il comando delete rimuoverà tutte le cartelle riunione inattive dall'utente.

### <a name="summary"></a>Riepilogo

Questo strumento può essere una risorsa preziosa per gli amministratori che necessitano di un controllo più preciso sui dati delle riunioni di conferenza.
