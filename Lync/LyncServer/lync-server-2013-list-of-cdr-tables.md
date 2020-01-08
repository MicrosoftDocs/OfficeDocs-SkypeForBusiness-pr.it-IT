---
title: 'Lync Server 2013: Elenco di tabelle di registrazione dettagli chiamata (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Elenco di tabelle di registrazione dettagli chiamata (CDR) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-18_

Lo schema di database di registrazione dei dettagli delle chiamate (CDR) è costituito dalle tabelle seguenti.

<div>

## <a name="static-tables"></a>Tabelle statiche


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a></p></td>
<td><p>Archivia l'elenco delle possibili priorità di chiamata, ad esempio emergenza, urgente, normale, non urgente e altro ancora.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</a></p></td>
<td><p>Archivia i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a></p></td>
<td><p>Archivia l'elenco dei possibili motivi di annullamento della registrazione degli utenti, &quot;ad esempio client avviati,&quot; &quot;registrazione&quot; &quot;scaduta, arresto&quot; anomalo del client e altro ancora.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Tabella MediaList in Lync Server 2013</a></p></td>
<td><p>Archivia l'elenco dei tipi di elementi multimediali che possono generare voci nel database, ad esempio messaggistica istantanea, audio, video e trasferimento di file.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Tabella PurgeSettings in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabella Roles in Lync Server 2013</a></p></td>
<td><p>Archivia l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Tabella SIPResponseMetaData in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>Tabelle di supporto


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a></p></td>
<td><p>Archivia i client (sia il tipo di client che il numero di versione) di ogni client coinvolto in una chiamata con le informazioni acquisite in questo database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Tabella ConferenceUris in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di ConferenceURIs usati nelle chiamate correlate alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Tabella ContentTypes in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di tipi di contenuto SIP (Session Initiation Protocol) usati sia in chiamate peer-to-peer che in conferenze telefoniche.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di dispositivi, inclusi il produttore, la versione hardware e l'indirizzo MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Tabella Dialogs in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sull'ID della finestra di dialogo per ogni sessione nel database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Tabella EdgeServers in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di Edge Server usati per le chiamate esterne.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Tabella Gateways in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di gateway usati per le chiamate VoIP (Voice over Internet Protocol).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Tabella HardwareVersions in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di versioni hardware dei dispositivi (telefono da tavolo).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Tabella Manufacturers in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di produttori di dispositivi (telefono da tavolo).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabella Mcus in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sui vari server di conferenza A/V e sui relativi URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a></p></td>
<td><p>Archivia un elenco di server di mediazione usati per le chiamate VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Tabella Phones in Lync Server 2013</a></p></td>
<td><p>Archivia tutti i numeri di telefono usati nelle chiamate VoIP archiviate o i cui dettagli delle chiamate sono stati registrati.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a></p></td>
<td><p>Archivia i nomi del pool in cui vengono acquisiti i messaggi di messaggistica istantanea.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Tabella Servers in Lync Server 2013</a></p></td>
<td><p>Archivia il nome dei server coinvolti nelle chiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabella Tenants in Lync Server 2013</a></p></td>
<td><p>Archivia i tenant supportati dalla distribuzione corrente. Sono presenti alcuni tenant per l'utente aziendale, un utente federato, un utente di connettività per messaggistica istantanea pubblica e utenti anonimi.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a></p></td>
<td><p>Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabella Users in Lync Server 2013</a></p></td>
<td><p>Archivia gli URI utente degli utenti che hanno partecipato a sessioni registrate o archiviate in questo database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Tabella UserStatistics in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sull'uso di un singolo utente del sistema.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tabelle specifiche dei record CDR per conferenze


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Tabella Conferences in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su tutte le conferenze archiviate o i cui dettagli sono stati registrati, inclusi ConferenceURI, e l'ora di inizio e di fine.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Tabella ConferenceSessionDetails in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su ogni sessione di conferenza basata su SIP, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e l'ID di diagnostica per ogni sessione.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabella FocusJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni relative a riunioni e fogli di conferenza, inclusi il ruolo degli utenti e la versione client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabella McuJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sui server di conferenza A/V coinvolti in una conferenza e l'utente partecipa e lascia gli orari.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>Tabelle per i messaggi nelle conferenze di messaggistica istantanea


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Tabella ConferenceMessageCount in Lync Server 2013</a></p></td>
<td><p>Per ogni conferenza di messaggistica istantanea, archivia il numero di messaggi inviati da ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Tabella IMReportSummary in Lync Server 2013</a></p></td>
<td><p>Fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>Tabelle per le sessioni peer-to-peer


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Tabella SessionDetails in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su ogni sessione peer-to-peer, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e il numero di messaggi per ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Tabella FileTransfers in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni sulle sessioni di trasferimento di file, inclusi il nome e il risultato del file (accettato, rifiutato o annullato).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Tabella Media in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sui diversi tipi di elementi multimediali coinvolti nelle sessioni peer-to-peer.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>Tabella per i dettagli delle chiamate VoIP


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Tabella VoipDetails in Lync Server 2013</a></p></td>
<td><p>Per ogni chiamata VoIP/PSTN a due parti, archivia le informazioni sulla chiamata, ad esempio l'ID telefono del telefono VoIP, il gateway usato e il partito disconnesso. Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio/fine delle chiamate e il codice di risposta.</p>
<div>

> [!NOTE]  
> Se una delle parti di una chiamata è un utente VoIP o se è stato coinvolto un Mediation Server nella chiamata, verrà creato un record in questa tabella. Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) vengono acquisite nella <A href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabella per il controllo delle chiamate E9-1-1


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Tabella Locations in Lync Server 2013</a></p></td>
<td><p>Per ogni chiamata di emergenza, ad esempio una chiamata avanzata di 9-1-1 (E9-1-1), memorizza le informazioni sulla posizione sulla chiamata. Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio/fine delle chiamate e il codice di risposta.</p>
<div>

> [!NOTE]  
> Questa tabella contiene solo il BLOB della posizione per la chiamata E9-1-1. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate sulla chiamata.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tabelle per la risoluzione dei problemi


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Tabella Application in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni su vari processi in Lync Server 2013 coinvolti in routing e connessioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Tabella CallType in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni sui tipi di chiamata, ad esempio "audio", "messaggistica istantanea", "audio e video" e "condivisione applicazioni".</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Tabella ErrorCategory in Lync Server 2013</a></p></td>
<td><p>Archivia il nome descrittivo per ogni classificazione di diagnostica di Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Tabella ErrorDef in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni sui tipi di errori e sulle relative definizioni.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sugli errori che si sono verificati.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Tabella ProgressReport in Lync Server 2013</a></p></td>
<td><p>Archivia le informazioni sui rapporti sullo stato di avanzamento di vari passaggi coinvolti nei processi di Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Le tabelle nell'elenco seguente vengono usate internamente da Lync Server. I relativi dettagli non sono descritti in questo documento.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tabelle per l'uso interno da Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabella</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella FrontEnd</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella MSMQProcessing</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella Syndicate</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella SyndicatorsTenantMap</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella delle attività</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

