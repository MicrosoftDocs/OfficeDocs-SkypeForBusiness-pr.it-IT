---
title: Strumenti del Resource Kit di chat persistenti di Lync Server 2013
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
ms.openlocfilehash: a827892dac61ff88d0527eafb7d94948afa21885
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a>Strumenti del Resource Kit di chat persistenti di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-24_

Gli strumenti di Resource Kit di chat persistenti di Lync Server 2013 consentono di semplificare le attività di routine per gli amministratori IT che distribuiscono e gestiscono il server di chat persistente di Lync Server 2013. Oltre alle istruzioni per l'installazione, questo argomento descrive lo scopo di ogni strumento e gli esempi del relativo utilizzo.

<div>

## <a name="installation-of-the-resource-kit-tools"></a>Installazione degli strumenti del Resource Kit

Per installare Lync Server 2013, strumenti Resource Kit, scaricare **PersistentChatReskit. msi**. Eseguire **PersistentChatReskit. msi** per eseguire un'installazione semplice. Il file \\con estensione msi installa tutti gli strumenti disponibili nel percorso seguente: **programmi Microsoft Lync Server\\2013 Persistent Chat Server Resource Kit.\\ ** Gli strumenti che sono eseguibili indipendenti si trovano in questa cartella. Gli strumenti che includono anche i file sono presenti nelle sottocartelle.

<div>


> [!IMPORTANT]  
> Dopo l'installazione di Lync Server 2013, strumenti Resource Kit, è necessario installare <STRONG>psexec. exe</STRONG> e copiare <STRONG>psexec. exe</STRONG> nel percorso seguente: \\ <STRONG>file di programma \ Microsoft Lync Server 2013 \ Persistent Chat Server Resource Kit\ChatStressTool</STRONG>. Se non si copia <STRONG>psexec. exe</STRONG>, lo strumento di stress della chat persistente genererà un'eccezione di errore e non verrà eseguita correttamente. Verificare di soddisfare questo requisito preliminare prima di eseguire lo strumento. Per informazioni dettagliate sull'installazione di <STRONG>psexec. exe</STRONG>, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=282246">http://go.microsoft.com/fwlink/p/?LinkId=282246</A>.



</div>

</div>

<div>

## <a name="supported-environments"></a>Ambienti supportati

Per ottenere prestazioni ottimali, gli strumenti di Lync Server 2013, Resource Kit devono essere installati nello stesso ambiente e con le stesse specifiche necessarie per Lync Server 2013.

</div>

<div>

## <a name="resource-kit-tools-overview"></a>Panoramica degli strumenti di Resource Kit

Ecco gli strumenti disponibili nel Resource Kit di Lync Server 2013 Persistent Chat. La sezione seguente fornisce una descrizione di ogni strumento, inclusi i requisiti e l'utilizzo di esempio.

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

Lo strumento AffCheck conferma che l'utente del database back-end della chat persistente e i record di affiliazione del gruppo corrispondono a quelli dei servizi di dominio Active Directory.

</div>

<div>

## <a name="requirements"></a>Requisiti

Lo strumento viene installato con il programma di installazione di PersistentChatResKit in un computer unito a un dominio.

L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database back-end della chat persistente e ai servizi di dominio Active Directory.

</div>

<div>

## <a name="usage"></a>L'uso

Configura il file AffCheck. exe. config in base alle istruzioni nel file di configurazione ed Esegui lo strumento AffCheck senza parametri della riga di comando. Di seguito sono riportati i contenuti dell'impostazione predefinita AffCheck. exe. config.

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

Lo strumento PersistentChatMonitoringSummary sposta le informazioni di monitoraggio della chat persistente dal database di monitoraggio in un file di log CSV specificato.

Il file CSV conterrà una ripartizione delle sessioni di chat persistenti in base al numero di sessioni totali, sessioni di successo, errori imprevisti, errori previsti e una ripartizione degli errori imprevisti per ID diagnostica, numero di errori e Descrizione dell'errore.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso al database di monitoraggio.

L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database di monitoraggio.

Il file PersistentChatMonitoringSummary. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database di monitoraggio. Deve inoltre contenere una chiave per il PersistentChatEndpointUri in cui verranno raccolti i dati di monitoraggio e un percorso di file in una posizione per il file CSV che verrà generato. Per gli esempi, vedere il file di configurazione installato. Il file deve trovarsi nella stessa directory dello strumento.

</div>

<div>

## <a name="usage"></a>L'uso

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

Questi parametri definiscono la selezione dei dati:

**StartDateTime:** Facoltativamente, specifica la data di inizio del periodo di selezione. Impostazione predefinita: 1/1/1753 12:00:00 AM

**EndDateTime:** Facoltativamente, specifica l'ultima data del periodo di selezione. Impostazione predefinita: ora

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

## <a name="persistent-chat-stress-tool"></a>Strumento di stress per la chat persistente

<div>

## <a name="description"></a>Descrizione

Lo strumento di stress per la chat persistente offre un modo semplice per simulare l'uso della chat persistente per testare le prestazioni reali, inclusi i vari modelli di utenti per adattarsi meglio agli scenari di utilizzo previsti.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit di chat persistenti in un computer collegato al dominio che abbia accesso al database back-end della chat persistente.

Oltre a questo *controller* , è necessario disporre di diversi computer di *caricamento* . Per tutti gli utenti di 10K nel modello utente, è necessario almeno 4GB di RAM gratuita in un caricatore. Ad esempio, una corsa con gli utenti di 80K richiederà circa 32GB di RAM distribuiti in tutti i computer Loader. È consigliabile disporre di almeno tre computer loader, indipendentemente dal carico previsto.

I computer Loader devono avere il Framework .NET 4,5 e l'installazione di Visual C++ 2012 ridistribuibile.

</div>

<div>

## <a name="configuration"></a>Configurazione

Copiare i file di ChatStressTool in una cartella condivisa accessibile da tutti i computer Loader.

Creare utenti e canali da usare durante l'esecuzione della sollecitazione:

  - Consente di creare il numero di utenti che richiede il modello utente, abilitarli per Lync e impostare i criteri di persistenza della chat su Enabled.

  - Creare una categoria per i canali di stress e quindi creare il numero di sale necessario in tale categoria. La categoria dovrebbe avere tutti gli utenti di stress nell'elenco **consentiti** (tramite l'aggiunta della propria UO) e le sale di stress dovrebbero avere un'impostazione di privacy **aperta**.

  - È consigliabile creare sale di stress extra. È possibile creare sale di 50.000 con il comando di interfaccia della riga di comando di Windows PowerShell seguente:
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

Modificare i file di configurazione per adattarli alla topologia:

In **LoaderProcess. exe. config**modificare "controller.contoso.com" con il nome di dominio completo (FQDN) del computer del controller.

In **StressLauncher. exe. config:**

1.  Modificare il valore dell'impostazione "LoaderBinary" nel percorso della cartella condivisa.

2.  Modificare "AdminUser"/"AdminPassword" in credenziali con accesso amministratore ai computer Loader.

3.  Modificare "ChannelCategory" con il nome della categoria in cui sono stati creati i canali di sollecitazione.

4.  Modificare "UserNamePattern" e "UserPasswordPattern" in un modello che corrisponda alle credenziali utente di stress. {0}viene sostituito con il numero di indice dell'utente.

5.  Modificare "Domain" nel dominio SIP della topologia di test.

6.  Modificare "ConnectionString" in una stringa di connessione per il database back-end della chat persistente.

7.  Modificare "UserIndexStart" con l'indice del primo utente di stress.

8.  Modificare "LyncFQDN" con il nome di dominio completo del pool Front-end.

9.  Modificare l'elenco "macchine" per includere i nomi dei computer per tutti i computer del caricatore.

10. Modificare il baseAddress dell'endpoint del servizio (il valore predefinito è "controller.contoso.com") con il nome di dominio completo del computer del controller.

</div>

<div>

## <a name="usage"></a>L'uso

Al termine della configurazione, aprire StressLauncher. exe nel computer del controller. Puoi avviare StressLauncher come qualsiasi utente. Le credenziali in cui vengono avviati i processi del caricatore nei computer Loader devono essere specificate nel file di configurazione. Devi anche fornire una stringa di connessione che abbia accesso in lettura al database back-end della chat persistente. Se la stringa di connessione usa l'autenticazione integrata di Windows, è necessario avviare StressLauncher come utente con questo accesso.

Modificare le impostazioni del modello utente in base alle esigenze. Fare clic su **Avvia caricamento** per avviare una corsa. Dopo un minuto o giù di lì, gli utenti inizieranno a essere connessi e l'indicatore di stato inizierà a riempirsi. A questo punto, è possibile che la macchina di controllo funzioni e prenda misure di prestazioni.

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a>ChatUpgradeVerifier

<div>

## <a name="description"></a>Descrizione

ChatUpgradeVerifier è uno strumento di confronto di database specifico per la chat persistente. Lo strumento confronta il database di Group Chat 2007 R2 o Group Chat 2010 (2007/2010Db) con il database Persistent Chat 2013 (2013Db).

Lo strumento controllerà, uno alla volta, ogni categoria, chat room persistente e componente aggiuntivo in 2007/2010Db per vedere se viene visualizzato nel 2013Db. Il confronto include il controllo di tutte le impostazioni della categoria, della chat room o del componente aggiuntivo, di tutte le entità nell'ambito della categoria e di qualsiasi entità di un ruolo nella categoria o nella chat room. Se una categoria o una chat room non viene visualizzata correttamente in 2013Db, le differenze verranno restituite a un file Conflicts. Se, dopo l'aggiornamento, il file 2007/2010Db viene modificato e quindi viene eseguito questo strumento, verrà visualizzato un output delle differenze per i conflitti. Tieni presente che questa applicazione è solo uno strumento di confronto di database e non convalida il processo di aggiornamento.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso ai database back-end della chat persistente (versioni precedenti e correnti per la chat persistente).

L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura ai database della chat persistente.

Il file ChatUpgradeVerifier. exe. config deve contenere il parametro GroupChat2007R2Db o il parametro GroupChat2010Db, con una stringa di connessione al database di chat di gruppo appropriato (GroupChat 2007R2 o 2010). Deve inoltre contenere un parametro PersistentChat2013Db, con una stringa di connessione al database della chat persistente di 2013.

</div>

<div>

## <a name="usage"></a>L'uso

Eseguire **ChatUpgradeVerifier** senza parametri.

</div>

<div>

## <a name="example"></a>Esempio

![Esecuzione di ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Esecuzione di ChatUpgradeVerifier.exe.")

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a>Report sull'utilizzo della chat persistente

<div>

## <a name="description"></a>Descrizione

Lo strumento ChatUsageReport genera un report HTML di utilizzo del servizio chat persistente.

</div>

<div>

## <a name="requirements"></a>Requisiti

Installare gli strumenti del Resource Kit della chat persistente in un computer collegato al dominio che abbia accesso al database back-end della chat persistente.

L'account utente in cui viene eseguito lo strumento deve avere accesso in lettura al database back-end della chat persistente.

Il file ChatUsageReport. exe. config deve contenere una \<sezione connectionStrings\> che definisce la stringa di connessione al database back-end della chat persistente. Il contenuto del file di configurazione predefinito è incluso qui, per il riferimento.

</div>

<div>

## <a name="usage"></a>L'uso

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
Questi parametri definiscono la selezione dei dati:

**StartDate:** Facoltativamente, specifica la data di inizio UTC del periodo di selezione. Impostazione predefinita: data meno recente

**EndDate:** Facoltativamente, specifica la data di fine dell'ora UTC del periodo di selezione. Impostazione predefinita: ora

Questi parametri definiscono la modalità e i dati visualizzati:

**TopActiveUsers:** Se specificato, il report includerà l'n utenti più attivi in termini di numero di messaggi pubblicati dall'utente nella chat room per il periodo selezionato. Impostazione predefinita: 10

**TopActiveRooms:** Se specificato, il report includerà la n chat room più attiva in termini di numero di messaggi pubblicati nella sala per il periodo selezionato. Impostazione predefinita: 10

**LeastActiveRooms:** Se specificato, il report includerà le chat room meno attive in termini di numero di messaggi pubblicati nella chat room per il periodo selezionato. Le camere avranno almeno un messaggio pubblicato. Impostazione predefinita: 10

**RoomsInactiveSince:** Se specificato, il report includerà un elenco di chat room inattive a partire dalla data specificata. Impostazione predefinita: tempo intero

**CartellaOutput:** Cartella in cui verranno inserite le immagini ChatUsageReport. html e Graph. Questa operazione deve essere definita nel file di configurazione o nella riga di comando.

Tutti i valori dei parametri della riga di comando possono essere specificati anche nel file ChatUsageReport. exe. config che si trova nella stessa directory dello strumento. Se viene specificato un valore nel file di configurazione e nella riga di comando, il valore della riga di comando sovrascriverà il valore del file di configurazione.

</div>

<div>

## <a name="output"></a>Output

Il report includerà sempre l'output seguente:

  - Prime n chat room più attive per numero di post di messaggio per il periodo selezionato.

  - Primi n utenti più attivi per numero di post di messaggio per periodo selezionato.

  - Principali n meno chat room attive in base al numero di post di messaggio per il periodo selezionato.

  - Chat room inattive per l'intera durata del database o dalla data specificata.

  - Tendenza post giornaliera del messaggio per il periodo selezionato.

  - Tendenza post settimanale del messaggio per il periodo selezionato.

  - Tendenza post mensile per il periodo selezionato.

  - Totale post di messaggio per periodo selezionato.

  - Numero totale di sale abilitate.

</div>

<div>

## <a name="example"></a>Esempio

L'esempio seguente genera un report sull'utilizzo per l'intero anno 2001 e inserisce il report in CartellaOutput specificato in ChatUsageReport. exe. config.

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

ScheduleADSyncForPrincipal è uno script di Microsoft SQL Server 2012 che deve essere eseguito direttamente da SQL Server Management Studio quando è connesso al database back-end della chat persistente. Questo script consente di forzare la chat persistente a sincronizzare i propri record di un utente con quelli dei servizi di dominio Active Directory, invece di attendere il tempo di sincronizzazione programmato.

</div>

<div>

## <a name="requirements"></a>Requisiti

L'account utente in cui viene eseguito lo script deve avere accesso proprietario al database back-end della chat persistente.

</div>

<div>

## <a name="usage"></a>L'uso

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

