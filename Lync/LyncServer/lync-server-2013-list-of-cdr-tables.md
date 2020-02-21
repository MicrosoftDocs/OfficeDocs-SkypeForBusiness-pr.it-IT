---
title: 'Lync Server 2013: elenco delle tabelle di registrazione dettagli chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ca9fd0b05eba812730c926685fedb244d60a29e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Elenco delle tabelle di registrazione dettagli chiamata in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-18_

Lo schema del database di registrazione dettagli chiamata (CDR) è costituito dalle tabelle riportate di seguito.

<div>

## <a name="static-tables"></a>Tabelle statiche


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Tabella CallPriorities in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio "emergency" (di emergenza), "urgent" (urgente), "normal" (normale), "non-urgent" (non urgente) e così via.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Tabella ConferenceJoinTimeThresholds in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Tabella DeRegisterType in Lync Server 2013</a></p></td>
<td><p>Archivia l'elenco dei possibili motivi di deregistrazione degli utenti, ad &quot;esempio client avviato&quot; &quot;, registrazione scaduta&quot; &quot;, arresto anomalo&quot; del client e altro ancora.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Tabella media in Lync Server 2013</a></p></td>
<td><p>,</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Tabella PurgeSettings in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate informazioni che specificano se le registrazioni dettagli chiamata obsolete verranno eliminate automaticamente dal database CDR.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Tabella Roles in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei possibili ruoli per le conferenze, ad esempio partecipante e relatore.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Tabella SIPResponseMetaData in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Tabella ClientVersions in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati il tipo e il numero di versione dei singoli client coinvolti in una chiamata con le informazioni acquisite nel database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Tabella ConferenceUris in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco degli URI conferenza utilizzati nelle chiamate relative alle conferenze.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Tabella ContentTypes in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei tipi di contenuto SIP (Session Initiation Protocol) utilizzati sia nelle chiamate peer-to-peer che nelle conferenze telefoniche.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Tabella Devices in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei dispositivi con il relativo produttore, la versione hardware e l'indirizzo MAC.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Tabella Dialogs in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative all'ID dialogo per ogni sessione nel database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Tabella EdgeServers in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei server perimetrali utilizzati per le chiamate esterne.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Tabella Gateways in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei gateway utilizzati per le chiamate VoIP (Voice over Internet Protocol).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Tabella HardwareVersions in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco delle versioni hardware dei dispositivi (telefoni da tavolo).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Tabella Manufacturers in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei produttori dei dispositivi (telefoni da tavolo).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Tabella MCU in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative ai diversi A/V Conferencing Server con i relativi URI.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Tabella MediationServers in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato l'elenco dei Mediation Server utilizzati per le chiamate VoIP.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Tabella Phones in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati tutti i numeri di telefono utilizzati nelle chiamate VoIP che sono state archiviate o di cui sono stati registrati i dettagli.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Tabella Pools in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati i nomi del pool in cui vengono acquisiti i messaggi istantanei.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Tabella Servers in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato il nome dei server coinvolti nelle chiamate.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Tabella Tenants in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati i tenant supportati dalla distribuzione corrente. Vi sono alcuni tenant predefiniti per l'utente Enterprise, l'utente federato, l'utente di connettività di messaggistica istantanea pubblica e gli utenti anonimi.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Tabella UserAgentDef in Lync Server 2013</a></p></td>
<td><p>Questa tabella contiene il mapping degli identificatori degli agenti utente ai nomi descrittivi degli agenti.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Tabella Users in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviati gli URI degli utenti che hanno partecipato alle sessioni registrate o archiviate nel database.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Tabella UserStatistics in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate informazioni sull'uso del sistema da parte di un singolo utente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>Tabelle specifiche dei record CDR per le conferenze


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Tabella Conferences in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative a tutte le conferenze che sono state archiviate o di cui sono stati registrati i dettagli, inclusi l'URI conferenza e la data/ora di inizio e fine.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Tabella ConferenceSessionDetails in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative a tutte le sessioni di conferenza basate su SIP, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e l'ID diagnostica di ogni sessione.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Tabella FocusJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative alle partecipazioni e agli abbandoni delle conferenze, inclusi il ruolo degli utenti e la versione client.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Tabella McuJoinsAndLeaves in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative agli A/V Conferencing Server coinvolti in una conferenza e la data/ora di partecipazione e abbandono degli utenti.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Tabella ConferenceMessageCount in Lync Server 2013</a></p></td>
<td><p>In questa tabella è archiviato, per ogni conferenza di messaggistica istantanea, il numero dei messaggi inviati da ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Tabella IMReportSummary in Lync Server 2013</a></p></td>
<td><p>Questa tabella fornisce un rapporto complessivo sulle sessioni di messaggistica istantanea tenute in un'organizzazione.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Tabella SessionDetails in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative a tutte le sessioni peer-to-peer, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e il numero dei messaggi per ogni utente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Tabella FileTransfers in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative alle sessioni di trasferimento file, inclusi il nome di file e il risultato (accettazione, rifiuto o annullamento).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Tabella multimediale in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative ai diversi tipi di contenuto multimediale coinvolti nelle sessioni peer-to-peer.</p></td>
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
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Tabella VoipDetails in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate, per ogni chiamata VoIP/PSTN tra due parti, le informazioni relative alla chiamata, ad esempio l'ID del telefono VoIP, il gateway utilizzato e la parte che si è disconnessa. Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</p>
<div>

> [!NOTE]  
> Se una parte coinvolta in una chiamata è un utente VoIP o se nella chiamata è coinvolto un Mediation Server, verrà creato un record in questa tabella. Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) sono state acquisite nella <A href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</A>.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>Tabella per il controllo delle chiamate di emergenza


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Tabella Locations in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate, per ogni chiamata di emergenza, le informazioni relative alla località della chiamata. Fa riferimento alla <a href="lync-server-2013-sessiondetails-table.md">tabella SessionDetails in Lync Server 2013</a> per gli orari di inizio e di fine chiamata e il codice di risposta.</p>
<div>

> [!NOTE]  
> In questa tabella è contenuto solo il BLOB della località per la chiamata di emergenza. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate relative alla chiamata.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>Tabella per la risoluzione dei problemi


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Tabella Application in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni sui vari processi all'interno di Lync Server 2013 coinvolti nel routing e nelle connessioni.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Tabella CallType in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative ai tipi di chiamata, ad esempio "audio", "Instant Messaging" (messaggistica istantanea), "audio and video" (audio e video) e "application sharing" (condivisione applicazioni).</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Tabella ErrorCategory in Lync Server 2013</a></p></td>
<td><p>Archivia il nome descrittivo per ogni classificazione diagnostica di Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Tabella ErrorDef in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative ai tipi di errori con le relative definizioni.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Tabella ErrorReport in Lync Server 2013</a></p></td>
<td><p>In questa tabella sono archiviate le informazioni relative agli errori che si sono verificati.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Tabella ProgressReport in Lync Server 2013</a></p></td>
<td><p>Archivia informazioni sui report sullo stato di avanzamento di vari passaggi coinvolti nei processi di Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


Le tabelle nell'elenco seguente vengono utilizzate internamente da Lync Server. I relativi dettagli non vengono illustrati in questo documento.

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Tabelle utilizzate internamente da Lync Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>tavolo</th>
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
<td><p><strong>Tabella Syndicators</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tabella SyndicatorsTenantMap</strong></p></td>
<td><p>Solo per uso interno.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tabella Task</strong></p></td>
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
<td><p>Solo per utilizzo interno.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

