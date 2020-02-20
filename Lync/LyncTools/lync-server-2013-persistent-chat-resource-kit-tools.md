---
title: Strumenti del Resource Kit di Lync Server 2013 Persistent Chat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 726e6bb537a16ece5c2955f005e91872f11f6a79
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Strumenti del Resource Kit di Lync Server 2013 Persistent Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-24_

Gli strumenti del Resource Kit di chat di Lync Server 2013 Persistent consentono di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono il server di chat persistente di Lync Server 2013. Oltre alle istruzioni per l'installazione, in questo argomento viene descritto lo scopo di ogni strumento e gli esempi di utilizzo.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installazione degli strumenti del Resource Kit

Per installare Lync Server 2013, strumenti del Resource Kit, scaricare **PersistentChatReskit. msi**. Eseguire **PersistentChatReskit. msi** per eseguire un'installazione semplice. Il file con estensione msi installa tutti gli strumenti nel percorso seguente \\: **Program\\ Files Microsoft Lync Server\\2013 Persistent Chat Server Resource Kit**. Gli strumenti che sono eseguibili indipendenti sono presenti in questa cartella. Gli strumenti che dispongono anche di file si trovano nelle rispettive sottocartelle.

<div>


> [!IMPORTANT]  
> Dopo aver installato Lync Server 2013, strumenti del Resource Kit, è necessario installare <STRONG>psexec. exe</STRONG> e copiare <STRONG>psexec. exe</STRONG> nel percorso seguente: \\ <STRONG>file di programma \ Microsoft Lync Server 2013 \ Kit\ChatStressTool delle risorse del server Chat persistente</STRONG>. Se non si copia <STRONG>psexec. exe</STRONG>, lo strumento di stress Persistent Chat genererà un'eccezione di errore e non verrà eseguita correttamente. Prima di eseguire lo strumento, accertarsi di rispettare questo requisito prerequisito. Per informazioni dettagliate sull'installazione di <STRONG>psexec. exe</STRONG>, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.



</div>

</div>

<div>

## <a name="supported-environments"></a>Ambienti supportati

Per ottenere prestazioni ottimali, è consigliabile installare gli strumenti di Lync Server 2013, Resource Kit nello stesso ambiente e con le stesse specifiche richieste per Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Panoramica degli strumenti del Resource Kit

Di seguito sono riportati gli strumenti disponibili nel Resource Kit di Lync Server 2013 Persistent Chat. Nella sezione seguente viene fornita una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio.

  - AffCheck

  - ChatMonitoringSummary

  - Strumento ChatStress

  - ChatUpgradeVerifier

  - ChatUsageReport

  - ScheduleADSyncforPrincipal

</div>

<div>

## <a name="affcheck"></a>AffCheck

<div>

## <a name="description"></a>Descrizione

Lo strumento AffCheck conferma che l'utente del database back-end di chat persistente e i record di affiliazione di gruppo corrispondono a quelli dei servizi di dominio Active Directory.

</div>

<div>

## <a name="requirements"></a>Requisiti

Lo strumento viene installato con il programma di installazione di PersistentChatResKit in un computer aggiunto a un dominio.

L'account utente con cui viene eseguito lo strumento deve disporre dell'accesso in lettura al database back-end della chat persistente e ai servizi di dominio Active Directory.

</div>

<div>

## <a name="usage"></a>Usage

Configurare il file AffCheck. exe. config seguendo le istruzioni riportate nel file di configurazione ed eseguire lo strumento AffCheck senza parametri della riga di comando. Di seguito sono riportati i contenuti del file AffCheck. exe. config predefinito.

**AffCheck. exe. config:**

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a>ChatMonitoringSummary

<div>

## <a name="description"></a>Descrizione

Lo strumento PersistentChatMonitoringSummary sposta le informazioni di monitoraggio della chat persistente dal database di monitoraggio in un file di registro CSV specificato.

Il file CSV conterrà una ripartizione delle sessioni di chat persistente per numero di sessioni totali, sessioni riuscite, errori imprevisti, errori previsti e una ripartizione degli errori imprevisti in base all'ID diagnostica, al numero di errori e alla descrizione dell'errore.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso al database di monitoraggio.

L'account utente utilizzato per eseguire lo strumento deve disporre dell'accesso in lettura al database di monitoraggio.

Il file PersistentChatMonitoringSummary. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database di monitoraggio. Deve inoltre contenere una chiave per la PersistentChatEndpointUri in cui verranno raccolti i dati di monitoraggio e il percorso di un file per il file CSV che verrà generato. Per esempi, fare riferimento al file di configurazione installato. Il file deve trovarsi nella stessa directory dello strumento.

</div>

<div>

## <a name="usage"></a>Usage

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Questi parametri definiscono la selezione dei dati:

**StartDateTime:** Facoltativamente, specifica la data di inizio del periodo di selezione. Valore predefinito: 1/1/1753 12:00:00 AM

**EndDateTime:** Facoltativamente, specifica l'ultima data del periodo di selezione. Valore predefinito: ora

</div>

<div>

## <a name="example"></a>Esempio

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a>Strumento di stress per chat persistente

<div>

## <a name="description"></a>Descrizione

Lo strumento di stress per la chat persistente rappresenta un modo semplice per simulare l'utilizzo di chat persistente per testare le prestazioni del mondo reale, compresi i modelli di utenti diversi per adattarsi meglio agli scenari di utilizzo previsti.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di Persistent Chat su un computer aggiunto a un dominio che ha accesso al database back-end della chat persistente.

Oltre a questo computer *controller* , sono necessari diversi computer di *caricamento* . Per tutti gli utenti di 10K nel modello utente, sarà necessario almeno 4GB di RAM libera su un computer caricatore. Ad esempio, una corsa con gli utenti di 80K richiede circa 32GB di RAM sparsa su tutti i computer del caricatore. È consigliabile disporre di almeno tre macchine del caricatore, indipendentemente dal carico previsto.

I computer del caricatore devono disporre di .NET 4,5 Framework e di Visual C++ 2012 Redistributable installato.

</div>

<div>

## <a name="configuration"></a>Configurazione

Copiare i file di ChatStressTool in una cartella condivisa accessibile da tutti i computer del caricatore.

Creare gli utenti e i canali da utilizzare nell'esecuzione dello sforzo:

  - Creare tutti gli utenti per le chiamate del modello utente, abilitarli per Lync e impostare i criteri di Persistent Chat su abilitato.

  - Creare una categoria per i canali di stress e quindi creare il numero di spazi necessari per tale categoria. La categoria deve disporre di tutti gli utenti di stress nell'elenco **consentiti** (aggiungendo la propria unità organizzativa) e le sale di stress devono avere un'impostazione di privacy **aperta**.

  - Si consiglia di creare sale per la sollecitazione aggiuntive. È possibile creare 50.000 sale con il seguente comando dell'interfaccia della riga di comando di Windows PowerShell:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Modificare i file di configurazione per adattarli alla topologia:

In **LoaderProcess. exe. config**, impostare "controller.contoso.com" sul nome di dominio completo (FQDN) del computer del controller.

In **StressLauncher. exe. config:**

1.  Modificare il valore dell'impostazione "LoaderBinary" nel percorso della cartella condivisa.

2.  Modificare "AdminUser"/"AdminPassword" in credenziali che dispongono dell'accesso di amministratore ai computer del caricatore.

3.  Modificare "ChannelCategory" con il nome della categoria in cui sono stati creati i canali di sollecito.

4.  Modificare "UserNamePattern" e "UserPasswordPattern" in un modello corrispondente alle credenziali utente di stress. {0}viene sostituito con il numero di indice dell'utente.

5.  Modificare "dominio" nel dominio SIP della topologia di test.

6.  Modificare "ConnectionString" in una stringa di connessione per il database back-end della chat persistente.

7.  Impostare "UserIndexStart" sull'indice del primo utente di stress.

8.  Modificare "LyncFQDN" con il nome di dominio completo del pool Front end.

9.  Modificare l'elenco "macchine" per includere i nomi dei computer per tutti i computer del caricatore.

10. Modificare l'baseAddress dell'endpoint del servizio (il valore predefinito è "controller.contoso.com") con il nome di dominio completo del computer del controller.

</div>

<div>

## <a name="usage"></a>Usage

Al termine della configurazione, aprire StressLauncher. exe nel computer del controller. È possibile avviare StressLauncher come qualsiasi utente. Le credenziali in base alle quali vengono avviati i processi del caricatore nei computer del caricatore devono essere specificate nel file di configurazione. È inoltre necessario fornire una stringa di connessione che disponga dell'accesso in lettura al database back-end della chat persistente. Se la stringa di connessione utilizza l'autenticazione integrata di Windows, è necessario avviare StressLauncher come utente che dispone di questo accesso.

Modificare le impostazioni del modello utente in base alle esigenze. Fare clic su **Avvia caricamento** per avviare una corsa. Dopo un minuto o giù di lì, gli utenti inizieranno a essere connessi e la barra di avanzamento inizierà a essere riempita. A questo punto, è possibile che il computer del controller funzioni e esegua misure di prestazioni.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Descrizione

ChatUpgradeVerifier è uno strumento di confronto di database specifico di chat persistente. Lo strumento confronta il database di Group Chat 2007 R2 o Group Chat 2010 (2007/2010Db) al database di Persistent Chat 2013 (2013Db).

Lo strumento controllerà, una per una, ogni categoria, chat room persistente e componente aggiuntivo in 2007/2010Db per vedere se viene visualizzato in 2013Db. Il confronto include la verifica di tutte le impostazioni della categoria, della chat room o del componente aggiuntivo, di qualsiasi entità nell'ambito della categoria e di qualsiasi entità in un ruolo nella categoria o nella chat. Se una categoria o una chat room non viene visualizzata correttamente in 2013Db, le differenze verranno restituite a un file Conflicts. Se dopo che si è verificato l'aggiornamento, il file 2007/2010Db è stato modificato e quindi questo strumento viene eseguito, si verificherà un output delle differenze per i conflitti. Si noti che questa applicazione è solo uno strumento di confronto dei database e non convalida il processo di aggiornamento.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso ai database back-end della chat persistente (versioni precedenti e correnti per la chat persistente).

L'account utente utilizzato per l'esecuzione dello strumento deve disporre dell'accesso in lettura ai database di Persistent Chat.

Il file ChatUpgradeVerifier. exe. config deve contenere il parametro GroupChat2007R2Db o il parametro GroupChat2010Db, con una stringa di connessione al database di chat di gruppo appropriato (GroupChat 2007R2 o 2010). Deve contenere anche un parametro PersistentChat2013Db, con una stringa di connessione al database di Persistent Chat 2013.

</div>

<div>

## <a name="usage"></a>Usage

Eseguire **ChatUpgradeVerifier** senza alcun parametro.

</div>

<div>

## <a name="example"></a>Esempio

![Esecuzione di ChatUpgradeVerifier. exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Esecuzione di ChatUpgradeVerifier. exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Report sull'utilizzo di chat persistente

<div>

## <a name="description"></a>Descrizione

Lo strumento ChatUsageReport genera un rapporto HTML relativo all'utilizzo del servizio chat persistente.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di Persistent Chat in un computer appartenente a un dominio che ha accesso al database back-end della chat persistente.

L'account utente con cui viene eseguito lo strumento deve disporre dell'accesso in lettura al database back-end della chat persistente.

Il file ChatUsageReport. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database back-end della chat persistente. Il contenuto del file di configurazione predefinito è incluso qui, per il riferimento.

</div>

<div>

## <a name="usage"></a>Usage

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Questi parametri definiscono la selezione dei dati:

**StartDate:** Facoltativamente, specifica la data di inizio dell'ora UTC del periodo di selezione. Valore predefinito: data meno recente

**EndDate:** Facoltativamente, specifica la data di fine dell'ora UTC del periodo di selezione. Valore predefinito: ora

Questi parametri definiscono come e quali dati vengono visualizzati:

**TopActiveUsers:** Se si specifica questo valore, il report includerà gli utenti n più attivi in termini di numero di messaggi inviati dall'utente nella chat room per il periodo selezionato. Predefinito: 10

**TopActiveRooms:** Se si specifica questo valore, il report includerà le chat room di n più attive in termini di numero di messaggi inseriti nella sala per il periodo di tempo selezionato. Predefinito: 10

**LeastActiveRooms:** Se si specifica questo valore, il report includerà le chat room n meno attive in termini di numero di messaggi pubblicati nella chat room per il periodo selezionato. Le sale avranno almeno un messaggio inviato. Predefinito: 10

**RoomsInactiveSince:** Se viene specificato, il report includerà un elenco di chat room inattive dopo la data specificata. Valore predefinito: tempo intero

**CartellaOutput:** Cartella in cui verranno posizionate le immagini di ChatUsageReport. html e del grafico. Tale operazione deve essere definita nel file di configurazione o nella riga di comando.

È inoltre possibile specificare tutti i valori dei parametri della riga di comando nel file ChatUsageReport. exe. config che si trova nella stessa directory dello strumento. Se si specifica un valore nel file di configurazione e nella riga di comando, il valore della riga di comando ignorerà il valore del file di configurazione.

</div>

<div>

## <a name="output"></a>Output

Il report includerà sempre l'output seguente:

  - Top n chat room più attive per numero di post di messaggio per il periodo selezionato.

  - Top n gli utenti più attivi per numero di post di messaggio per il periodo selezionato.

  - Top n chat room meno attive per numero di post di messaggio per il periodo selezionato.

  - Chat room inattive per tutta la durata del database o dopo la data specificata.

  - Trend post giornaliero del messaggio per il periodo selezionato.

  - Trend post settimanale dei messaggi per il periodo selezionato.

  - Trend post mensili del messaggio per il periodo selezionato.

  - Totale messaggi di messaggio per il periodo selezionato.

  - Numero totale di chat room abilitate.

</div>

<div>

## <a name="example"></a>Esempio

Nell'esempio seguente viene generato un report di utilizzo per l'intero anno 2001 e il report viene inserito in CartellaOutput specificato nel file ChatUsageReport. exe. config.

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
ChatUsageReport. exe. config:

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a>ScheduleADSyncForPrincipal

<div>

## <a name="description"></a>Descrizione

ScheduleADSyncForPrincipal è uno script di Microsoft SQL Server 2012 che deve essere eseguito direttamente dall'interno di SQL Server Management Studio quando è connesso al database back-end della chat persistente. Questo script consente di forzare la chat persistente a sincronizzare i propri record di un utente con quelli dei servizi di dominio Active Directory, anziché attendere il tempo di sincronizzazione pianificato.

</div>

<div>

## <a name="requirements"></a>Requisiti

L'account utente con cui viene eseguito lo script deve disporre dell'accesso proprietario al database back-end della chat persistente.

</div>

<div>

## <a name="usage"></a>Usage

Di seguito sono riportati i contenuti dello script predefinito:

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

