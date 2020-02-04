---
title: 'Lync Server 2013: attributi e descrizioni dello schema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema attributes and descriptions
ms:assetid: b009df76-9c22-471d-b57a-bda009a98261
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412841(v=OCS.15)
ms:contentKeyID: 48185083
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72da4adb0f660604dba7f20c9ddc333425086df2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Attributi e descrizioni dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

In questa sezione vengono descritti tutti gli attributi dello schema usati da Lync Server 2013. Per le classi associate agli attributi, vedere [attributi dello schema per classe in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Per un elenco di classi e attributi nuovi in Lync Server 2013, vedere [modifiche allo schema in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Gli attributi con coppie collegate vengono specificati come collegamenti inoltrati o collegamenti indietro. Un attributo che fa riferimento a un altro oggetto è un collegamento in avanti; l'attributo dell'altro oggetto che fa riferimento al primo oggetto è un collegamento a ritroso. I collegamenti inoltrati sono aggiornabili, mentre i collegamenti indietro sono di sola lettura.

Alcuni attributi hanno un valore per la maschera di bit. Per questi attributi, ogni impostazione è rappresentata da un bit e il valore decimale visualizzato rappresenta la posizione di bit. Le posizioni di bit iniziano con il bit 0. Ad esempio, 1 (binario) è un set di bit 0 e 10000 (binario) è un set di bit 4. Ogni bit rappresenta una proprietà. Di seguito sono riportati alcuni esempi:

  - 10000 (binario) ha un valore decimale pari a 16 (ovvero, il bit 4 è impostato).

  - 100 milioni (binario) ha un valore decimale di 256 (ovvero, il bit 8 è impostato).

  - 1100 (binario) ha un valore decimale pari a 12 (ovvero i bit 2 e 3 sono impostati; le proprietà rappresentate da entrambi i bit sono abilitate).

  - 1111000001 (binario) ha un valore decimale di 961 (ovvero i bit 0, 6, 7, 8 e 9 sono impostati; le proprietà di ognuno di questi bit sono abilitate).

<div id="sectionSection0" class="section">

### <a name="schema-attributes-for-lync-server-2013"></a>Attributi dello schema per Lync Server 2013

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo</th>
<th>Descrizione</th>
<th>Commenti</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dnsHostName</p></td>
<td><p>Un attributo esistente in servizi di dominio Active Directory ora associato alle classi <strong>msRTCSIP-Pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> . Questo attributo specifica il nome di dominio completo (FQDN) di un pool o di un server di monitoraggio.</p>
<p>Un valore valido per ogni segmento è di 63 caratteri; un valore valido per l'intero FQDN è di 255 caratteri.</p></td>
<td><p>Novità di Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Questo attributo contiene la rappresentazione di stringa del nome distinto (DN) dell'oggetto in un'altra foresta che corrisponde a questo oggetto. Questo attributo viene usato per l'espansione del gruppo di distribuzione e la presenza automatica. Questo attributo è definito nello schema Active Directory predefinito per Windows Server 2003 R2.</p>
<p>Per evitare di dover eseguire l'aggiornamento di servizi di dominio Active Directory a Windows Server 2003 R2, la preparazione dello schema di Active Web estende lo schema di Windows Server 2003 con questa definizione di attributo.</p></td>
<td><p>Novità di Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Questo attributo multivalore contiene le impostazioni della segreteria telefonica. Questo attributo è condiviso con la messaggistica unificata di Exchange.</p></td>
<td><p>Nuovo in Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente. I criteri di blocco mantengono gli elementi della cassetta postale per l'utente per la durata del blocco. Questo attributo è condiviso con Exchange 2013.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Questo attributo archivia le informazioni del provider di servizi di audioconferenza per un utente.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Questo attributo punta alla voce del servizio attendibile per il contatto dell'applicazione.</p></td>
<td><p>Novità di Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Application</p></td>
<td><p>Questo attributo contiene un elenco di applicazioni ospitate nel server applicazioni.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Questo attributo specifica le opzioni per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Questo attributo contiene la lingua principale per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Questo attributo di più valori contiene le lingue secondarie per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Questo attributo contiene un elenco di server applicazioni che appartengono al pool. Il collegamento in avanti corrispondente a questo attributo back link è <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Questo attributo punta al pool a cui appartiene il server applicazioni. Questo è il collegamento inoltra. Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveDefaultFlags (obsoleto)</p></td>
<td><p>Questo attributo specifica il valore predefinito globale all'interno del limite della foresta per l'archiviazione di tutte le comunicazioni degli utenti. Questa operazione viene applicata dal livello dell'agente di archiviazione. L'intervallo di valori per questo attributo è il seguente:</p>
<ul>
<li><p><strong>True</strong>: archiviare tutti gli utenti</p></li>
<li><p><strong>Falso</strong>: non archiviare tutti gli utenti</p></li>
</ul>
<p>Questo attributo controlla globalmente, all'interno del limite della foresta, la modalità di archiviazione delle comunicazioni degli utenti all'interno di una rete interna.</p>
<p><strong>Comportamento di Live Communications Server 2005 (ora ritirato)</strong></p>
<p>L'intervallo di valori per questo attributo è il seguente:</p>
<ul>
<li><p>0: archiviare il corpo del messaggio [bit 0]</p></li>
<li><p>1: non archiviare il corpo del messaggio [bit 0]</p></li>
</ul>
<p><strong>Comportamento di Office Communications Server 2007</strong></p>
<p>L'intervallo di valori per questo attributo è il seguente:</p>
<ul>
<li><p>0: ArchiveFederationDefaultWithoutBody (ritirato)</p></li>
<li><p>1-2: ArchiveInternalCommunications</p></li>
<li><p>3-4: ArchiveFederatedCommunications</p></li>
<li><p>5: RecordPresenceRegistrations</p></li>
<li><p>6: RecordIMCallDetails</p></li>
<li><p>7: RecordGroupIMCallDetails</p></li>
<li><p>8: RecordFileTransferInstances</p></li>
<li><p>9: RecordAudioCallDetails</p></li>
<li><p>10: RecordVideoCallDetails</p></li>
<li><p>11: RecordRemoteAssistanceCallDetails</p></li>
<li><p>12: RecordApplicationSharingDetails</p></li>
<li><p>13: RecordMeetingInstantiations</p></li>
<li><p>14: RecordMeetingJoins</p></li>
<li><p>15: RecordDataJoins</p></li>
<li><p>16: RecordAVJoins</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchiveFederationDefault (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchiveFederationDefaultFlags (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingEnabled</p></td>
<td><p>Questo attributo è un numero intero usato come campo di bit per controllare se le comunicazioni di un singolo utente devono essere archiviate. Questo controllo viene applicato dal livello dell'agente di archiviazione. È contrassegnata per la replica del catalogo globale.</p>
<p>L'ambito di questo attributo è specifico di un singolo utente o contatto. I valori validi (e le posizioni di bit associate) in Lync Server sono i seguenti:</p>
<ul>
<li><p>0: non archiviare (nessun bit impostato)</p></li>
<li><p>1: ritirato (posizione bit 0)</p></li>
<li><p>2: ritirato (posizione bit 1)</p></li>
<li><p>4: archiviare le comunicazioni interne (posizione bit 2)</p></li>
<li><p>8: archiviare le comunicazioni federate (posizione bit 3)</p></li>
</ul>
<p>I valori precedentemente validi in Live Communications Server 2005 sono i seguenti:</p>
<ul>
<li><p>0: usare il valore predefinito definito da <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation (</strong> in questo ordine di precedenza:</p>
<ul>
<li><p>1: Archivio</p></li>
<li><p>2: non archiviare</p></li>
<li><p>3: archiviare senza il corpo del messaggio</p></li>
</ul></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ArchivingServerData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsoleto)</p></td>
<td><p>Questo attributo definisce la versione del servizio archiviazione. Questo attributo è un tipo Integer a incremento costante che viene incrementato con ogni versione ufficiale del prodotto. I valori validi possibili sono i seguenti:</p>
<ul>
<li><p>Non definito: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-BackEndServer</p></td>
<td><p>Questo attributo specifica il nome di dominio completo del server back-end del pool. Poiché può essere disponibile solo un singolo server back-end per pool, si tratta di un attributo a valore singolo.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Questo attributo contiene l'identificatore del pool che ospita la directory della conferenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Questo attributo contiene l'identificatore di una directory conferenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Questo attributo contiene l'identificatore del pool in cui è stata spostata la directory della conferenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-default</p></td>
<td><p>Questo attributo booleano definisce se l'utilizzo del telefono è un uso predefinito. Se questo attributo è impostato su <strong>true</strong>, l'utilizzo del telefono è un uso predefinito e non può essere eliminato dall'amministratore. Se questo attributo è impostato su <strong>false</strong>, l'utilizzo può essere eliminato.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Questo attributo identifica l'URL di Communicator Web Access per gli utenti esterni all'organizzazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Questo attributo identifica l'URL di Communicator Web Access per gli utenti all'interno dell'organizzazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Questo attributo a valore singolo contiene il nome distinto (DN) di un oggetto della classe del profilo di posizione assegnato.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11036</strong></p>
<p>Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Questo attributo booleano specifica se il criterio è un criterio predefinito. I criteri sono un criterio predefinito quando impostato su <strong>true</strong>.</p></td>
<td><p>Novità di Office Communications Server 2007</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Questo attributo specifica il nome di dominio completo dell'Edge Server che gestisce il servizio Access Edge, se è possibile accedervi direttamente o del servizio di bilanciamento del carico hardware per un pool di server che utilizzano Access Edge Services. Se i server in cui è in esecuzione il servizio Access Edge sono accessibili solo tramite uno o più direttori, questo attributo specifica l'FQDN e, facoltativamente, il numero di porta del direttore o del bilanciamento del carico hardware che serve un pool di Director.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero di porta che deve essere usato per la connessione al server che usa il servizio Access Edge.</p>
<p>Il valore valido è un valore integer che specifica la porta da usare. Il valore predefinito è 5061.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il periodo di timeout della sottoscrizione di presenza predefinito.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout della registrazione predefinita.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout predefinita per l'abbonamento ai dati mobili.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Questo attributo viene usato in una topologia di domini divisi e contiene un nome di dominio completo (FQDN).</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsoleto)</p></td>
<td><p>Questo attributo di stringa UNICODE a valore singolo contiene una descrizione amichevole della regola di normalizzazione o della route del telefono.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Questo attributo rappresenta un dominio configurato per il registrar.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Questo attributo specifica il nome di dominio completo del server che utilizza Access Edge service.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Questo attributo controlla se un server genera una richiesta NOTIFY (notifica) ottimale, invece di una richiesta di notifica, in risposta a una richiesta di sottoscrizione da un client. La notifica è un'estensione che migliora le prestazioni dell'handshake di notifica della sottoscrizione in cui il server genera le richieste di notifica, anziché le normali richieste NOTIFY. Il vantaggio delle prestazioni è che una richiesta di notifica non richiede una risposta di 200 OK dal client come richiesto dalla richiesta di notifica.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 non supporta le richieste di notifica. Per interagire con le applicazioni server scritte con l'API server di Live Communications Server 2003 in esecuzione in Live Communications Server 2005 e i server di terze parti, le richieste di notifica possono essere disabilitate impostando il relativo valore su <STRONG>false</STRONG>. La notifica non fa attualmente parte del processo di standardizzazione SIP IETF (Internet Engineering Task Force).


</div></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Questo attributo è un interruttore globale che gli amministratori IT usano per configurare se gli utenti possono comunicare con utenti di altre organizzazioni. Consente a un amministratore di sovrascrivere l'attributo <strong>FederationEnabled</strong> di un singolo utente. Questo attributo può essere utile per proteggere la rete interna da attacchi Internet che potrebbero essere causati da worm, virus o attacchi mirati alla società.</p>
<p>I valori validi (e le posizioni di bit associate) sono i seguenti:</p>
<ul>
<li><p>1: abilitato per la connettività di messaggistica istantanea pubblica (posizione bit 0)</p></li>
<li><p>2: riservato (posizione bit 1)</p></li>
<li><p>4: riservato (posizione bit 2)</p></li>
<li><p>8: riservato (posizione bit 3)</p></li>
<li><p>16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (consentire agli utenti di invitare utenti anonimi alle riunioni (posizione in bit 6)</p></li>
<li><p>128: UCEnabled (abilitazione degli utenti per le comunicazioni unificate) (posizione bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (abilitare l'utente per la connettività di messaggistica istantanea pubblica) (posizione bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posizione bit 9)</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Questo attributo indica se i servizi aziendali vengono caricati nel server specifico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Questo attributo contiene il codice di chiamata per l'accesso esterno.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Questo attributo controlla se un singolo utente è abilitato per la Federazione. Viene applicata dal livello servizi Enterprise. È contrassegnata per la replica del catalogo globale.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Questo attributo è un elenco multivalore dei nomi di dominio di tutti i server di Enterprise Edition associati a un pool.</p>
<p>Collegamento a ritroso: <strong>Link ID 11023</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento indietro è <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateway (obsoleto)</p></td>
<td><p>Questo attributo di stringa multivalore contiene un elenco di gateway e porte (per gateway).</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Questo attributo archivia le coppie nome: valore. La coppia nome: valore già definita è per l'impostazione <strong>Consenti polling per la presenza</strong> .</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Questo attributo è un identificatore univoco di un gruppo usato per raggruppare le voci della Rubrica.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003 (non usato).</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-HomeServerString (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003.</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeUsers (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003 (non usato).</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Questo attributo controlla se un singolo utente è abilitato per l'accesso degli utenti esterni. Viene applicata dal livello servizi Enterprise. È contrassegnata per la replica del catalogo globale.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Master (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Novità in Live Communications Server 2003</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-line</p></td>
<td><p>Questo attributo a valore singolo contiene l'ID dispositivo (URI SIP o l'URI TEL del telefono usato dai controlli utente) utilizzato da Lync per la telefonia. Questo attributo è contrassegnato per la replica del catalogo globale ed è indicizzato. Se un utente è abilitato per VoIP aziendale, questo attributo archivia la versione normalizzata E. 164 del numero di telefono dell'utente.</p></td>
<td><p>Novità di Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Questo attributo a valore singolo contiene l'URI SIP del server gateway CSTA-SIP. Questo attributo è contrassegnato per la replica del catalogo globale, ma non è indicizzato.</p></td>
<td><p>Novità di Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti di normalizzazione locali associati al profilo della posizione. Il tipo di questo attributo è un file binario DN. Esiste una relazione uno-a-molti tra il profilo della posizione e le regole di normalizzazione locali. L'ordinamento dell'elenco dei DNs di normalizzazione locale deve essere mantenuto nell'ordine specificato dall'amministratore. La conservazione dell'ordine viene mantenuta dalla parte binaria del binario DN, che specifica l'indice dell'ordine.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11034</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-locationProfileBL</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationOptions</p></td>
<td><p>Questo attributo contiene un elenco di opzioni per la regola di normalizzazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationName (obsoleto)</p></td>
<td><p>Questo attributo a valore singolo contiene un nome descrittivo per il profilo posizione che indica la posizione rappresentata dal profilo. Poiché possono essere presenti più profili di posizione, l'amministratore ha bisogno di un modo per distinguere i diversi profili.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti del profilo posizione. Questo attributo specifica il collegamento di nuovo a uno o più profili di posizione.</p>
<p>Collegamento a ritroso: <strong>Link ID 11035</strong></p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Questo attributo contiene le opzioni per il profilo posizione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Questo attributo con più valori contiene un elenco di contatti dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Questo attributo con più valori contiene un elenco di profili di posizione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero massimo di richieste di ricerca in sospeso per server.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</p></td>
<td><p>L'attributo rappresenta il numero massimo di abbonamenti per utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout della sottoscrizione massima.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout registrazioni massime.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout per gli abbonamenti a dati mobili massimo.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Questo attributo è un attributo del punto di controllo del servizio nella classe computer che specifica un collegamento alla Factory di unità di controllo multipoint (MCU) a cui appartiene. Questo punto di controllo del servizio e l'attributo viene creato per ogni MCU Microsoft. Ogni MCU Microsoft deve trovare il server back-end del pool a cui appartiene, per recuperare le impostazioni a livello di pool.</p>
<p>Il valore di questo attributo è il nome distinto (DN) della factory MCU. Si tratta di un attributo a valore singolo e contrassegnato per la replica del catalogo globale.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11026</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Questo è un attributo riservato a più stringhe. Le impostazioni archiviate in questo attributo sono rappresentate come coppie nome = valore. Le coppie nome/valore attualmente definite sono:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Si tratta di un attributo a valore singolo che contiene il nome distinto (DN) di una singola factory MCU associata a un pool.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11024</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Questo attributo è una stringa a valore singolo che specifica il GUID del provider di factory MCU. In base al valore GUID, il processo factory MCU determina se eseguire il servizio di questo tipo di MCU. Se il valore GUID è <strong>{F0810510-424f-46ef-84fe-6CC720DF1791}</strong>, il processo factory MCU (disponibile per impostazione predefinita in Lync Server) lo elaborerà. Per qualsiasi altro valore GUID, il processo factory MCU non servirà al tipo MCU.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Questo attributo è un elenco multivalore di nomi distinti (DN). Questo attributo contiene un elenco di tutti i server MCU dello stesso tipo e fornitore associato a questa factory MCU. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p>
<p>Collegamento a ritroso: Link ID 11027</p>
<p>Il collegamento in avanti corrispondente a questo collegamento indietro è <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Questo attributo è una stringa a valore singolo che specifica il mezzo che può essere gestito da MCU.</p>
<p>I tipi validi supportati sono:</p>
<ul>
<li><p>riunione</p></li>
<li><p>audio-video</p></li>
<li><p>Chat</p></li>
<li><p>telefono-conf</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUVendor</p></td>
<td><p>Questo attributo è una stringa a valore singolo che specifica il nome di un fornitore di MCU. Tutti i Microsoft MCU specificano che questo attributo è <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Questo attributo definisce diverse opzioni di riunione che sono abilitate globalmente per tutti gli utenti o gli oggetti contatto. Questo attributo è un valore della maschera di bit di tipo Integer.</p>
<p>I valori validi (e le posizioni di bit associate) sono i seguenti:</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants è None (non consentire agli utenti di invitare utenti anonimi alle riunioni) (nessun bit impostato)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants è Everyone (Consenti a tutti gli utenti di invitare utenti anonimi alle riunioni) (posizione bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants è UsePerUserSetting (consente agli utenti di invitare utenti anonimi alle riunioni in base alle impostazioni per utente) (posizione bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (i criteri delle riunioni sono definiti per ogni utente) (posizione bit 4)</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Questo attributo specifica il nome distinto (DN) del criterio assegnato dall'amministratore per l'utente come attributo a valore singolo.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout della sottoscrizione di presenza minima.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MinRegistrationTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout della registrazione minima.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout della sottoscrizione di dati roaming minima.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Questo attributo viene usato per archiviare il backend di SQL Server con mirroring usato dal pool Front-end.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Questo attributo contiene opzioni e contrassegni che definiscono le impostazioni di mobilità.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Questo attributo contiene il DN per un oggetto Criteri di mobilità.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero consentito di dispositivi su cui un utente può eseguire la registrazione per le comunicazioni SIP e sottoscrivere la presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Questo attributo specifica le opzioni abilitate per l'utente o l'oggetto contatto. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata da un po'. Questo attributo è contrassegnato per la replica del catalogo globale.</p>
<p>I valori validi (e le posizioni di bit associate) sono i seguenti:</p>
<ul>
<li><p>1: abilitato per la connettività messaggistica istantanea pubblica (posizione bit 0)</p></li>
<li><p>2: riservato (posizione bit 1)</p></li>
<li><p>4: riservato (posizione bit 2)</p></li>
<li><p>8: riservato (posizione bit 3)</p></li>
<li><p>16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (consentire agli utenti di invitare utenti anonimi alle riunioni (posizione in bit 6)</p></li>
<li><p>128: UCEnabled (abilitazione degli utenti per UC) (posizione bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (abilitare l'utente per la connettività di messaggistica istantanea pubblica) (posizione bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posizione bit 9)</p></li>
</ul></td>
<td><p>Novità di Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Questo attributo viene usato nelle topologie della foresta centrale e delle risorse per abilitare Single Sign-on quando un utente ObjectSID dall'account principale di Windows NT Server viene copiato in questo attributo dell'oggetto utente o contatto corrispondente nella foresta di risorse o centrale. Communicator Web Access cerca un utente in servizi di dominio Active Directory usando questo attributo o il ObjectSID dell'utente. Questo attributo è contrassegnato per la replica del catalogo globale.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Questo attributo è l'URN (Uniform Resource Name) del proprietario per un contatto dell'applicazione.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pattern (obsoleto)</p></td>
<td><p>Questo attributo di stringa a valore singolo contiene uno schema usato per la corrispondenza dei numeri di chiamata nel formato E. 164. Se il numero di telefono corrisponde a questo modello, la traduzione viene applicata al numero selezionato.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti per la route telefonica (DN). Questo attributo specifica il collegamento di nuovo a una o più rotte telefoniche.</p>
<p>Collegamento a ritroso: <strong>Link ID 11033</strong></p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsoleto)</p></td>
<td><p>Questo attributo stringa UNICODE a singolo valore specifica il nome descrittivo della route telefonica, quindi può essere facilmente fatto riferimento dall'amministratore.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsoleto)</p></td>
<td><p>Questo attributo è una stringa Unicode a valore singolo. Questo attributo stringa contiene la definizione dei criteri in formato XML. La definizione di XML Schema è comune in diversi tipi di criteri, ma solo le impostazioni sono diverse per ogni tipo di criterio.</p>
<p>La definizione di schema XML (XSD) viene definita come segue:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;xs:schema id=&quot;instance&quot; xmlns=&quot;&quot; xmlns:xs=&quot;http://www.w3.org/2001/XMLSchema&quot; xmlns:msdata=&quot;urn:schemas-microsoft-com:xml-msdata&quot;&gt;
  &lt;xs:element name=&quot;instance&quot; msdata:IsDataSet=&quot;true&quot;&gt;
    &lt;xs:complexType&gt;
      &lt;xs:choice maxOccurs=&quot;unbounded&quot;&gt;
        &lt;xs:element name=&quot;property&quot; nillable=&quot;true&quot;&gt;
          &lt;xs:complexType&gt;
            &lt;xs:simpleContent msdata:ColumnName=&quot;property_Text&quot; msdata:Ordinal=&quot;1&quot;&gt;
              &lt;xs:extension base=&quot;xs:string&quot;&gt;
                &lt;xs:attribute name=&quot;name&quot; type=&quot;xs:string&quot; /&gt;
              &lt;/xs:extension&gt;
            &lt;/xs:simpleContent&gt;
          &lt;/xs:complexType&gt;
        &lt;/xs:element&gt;
      &lt;/xs:choice&gt;
    &lt;/xs:complexType&gt;
  &lt;/xs:element&gt;
&lt;/xs:schema&gt;</code></pre></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PolicyData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsoleto)</p></td>
<td><p>Questo attributo stringa Unicode a valore singolo contiene il tipo di criteri. I tipi di criteri validi sono i seguenti:</p>
<ul>
<li><p>riunione</p></li>
<li><p>telefonia</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Questo attributo specifica un collegamento al pool a cui appartiene un computer. Questo attributo viene impostato indipendentemente dal fatto che il computer esegua l'edizione standard o l'edizione Enterprise di Lync Server. Questo attributo è contrassegnato per la replica del catalogo globale.</p>
<p>Il valore valido è il nome di dominio del pool.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11022</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Si tratta di un attributo multivalore che contiene un elenco dei nomi distinti (DN) dei pool con cui è associata la factory MCU.</p>
<p>Collegamento a ritroso: <strong>Link ID 11025</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento indietro è <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Novità di Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Questo attributo specifica un nome arbitrario per un pool visualizzato dalla console di gestione. Questo nome può essere modificato dall'amministratore.</p>
<p>Il valore valido è una stringa che rappresenta il nome di un pool.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Questo attributo è un valore di stringa a valore singolo. Il valore di questo attributo, se presente, rappresenta il nome di dominio completo del pool se l'amministratore vuole creare un pool Front end con un FQDN che non è conforme alla struttura del dominio Active Directory in cui viene creato il pool Front End, ad esempio un SIP spazio dei nomi disgiunto dallo spazio dei nomi Domain Name System (DNS)).</p>
<p>È consigliabile eseguire il mapping del nome FQDN del dominio del pool Front-end alla parte Domain Name come dominio Active Directory in cui risiede il pool. Di conseguenza, quando non è presente alcun valore in questo attributo, il nome di dominio completo del pool di front end verrà impostato come predefinito nella struttura di Domain Name di Active Directory, come indicato dall'attributo <strong>dNSHostName</strong> .</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Elenco multivalore dei nomi di dominio di tutti i server Lync Server, Enterprise Edition associati a un pool. Questo attributo di tipo Integer definisce se il pool è in grado di messaggistica istantanea e presenza e riunioni.</p>
<p>I tipi di valore validi possibili sono i seguenti:</p>
<ul>
<li><p>Non definito: servizio di messaggistica istantanea e presenza (Live Communications Server 2005 e 2003)</p></li>
<li><p>1: servizio di messaggistica istantanea e presenza (Lync Server)</p></li>
<li><p>2: messaggistica istantanea e servizio di presenza e riunione (Lync Server)</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Questo attributo specifica se un pool di server è in uso in un server standard o in un server Enterprise Edition. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata da un po'.</p>
<p>I valori validi (e le posizioni di bit associate) sono i seguenti:</p>
<ul>
<li><p>1: Server Standard Edition, ospita gli utenti (posizione in bit 0)</p></li>
<li><p>2: Server Enterprise Edition, ospita gli utenti (posizione bit 1)</p></li>
<li><p>4: Server Standard Edition, applicazioni hosts (posizione bit 2)</p></li>
<li><p>8: Server Enterprise Edition, applicazioni hosts (posizione bit 3)</p></li>
</ul>
<p>Poiché Lync Server non supporta i pool che ospitano solo le applicazioni, gli unici valori validi sono i seguenti:</p>
<ul>
<li><p>5: Server Standard Edition, ospita utenti e applicazioni (posizioni in bit 0 e 2)</p></li>
<li><p>10: Server Enterprise Edition, ospita utenti e applicazioni (posizioni in bit 1 e 3)</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Questo attributo definisce la versione del pool. Si tratta di un tipo intero che viene incrementato con ogni versione di prodotto principale.</p>
<p>I tipi di valore validi possibili sono i seguenti:</p>
<ul>
<li><p>0: Live Communications Server 2003</p></li>
<li><p>1: Live Communications Server 2005</p></li>
<li><p>2: Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
</ul></td>
<td><p>Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PresenceFlags</p></td>
<td><p>Questo attributo contiene opzioni e contrassegni che definiscono le impostazioni di presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Questo attributo contiene il DN per un oggetto Criteri di presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Questo attributo Abilita un utente o un contatto per la messaggistica SIP. Viene aggiunta alla classe Contact perché nella topologia di foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</p>
<p>Il valore valido è il DN del server Standard Edition o del pool di front-end di Enterprise Edition in cui è ospitato un utente.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Questo attributo contiene l'indirizzo SIP di un utente specifico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Questo attributo contiene l'ID dispositivo del dispositivo di linea privato.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-instradabile</p></td>
<td><p>Questo attributo è un attributo booleano usato per determinare se Lync Server è autorizzato a eseguire il routing a questo servizio usando il relativo indirizzo GRUU. Se questo valore è impostato su <strong>true</strong>, Lync Server è autorizzato a eseguire il routing a questo servizio. Se questo valore è impostato su <strong>false</strong>, Lync Server non è autorizzato a eseguire il routing a questo servizio.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Questo attributo stringa UNICODE a valore singolo definisce un attributo che qualifica l'utilizzo per una route telefonica. La selezione di una route telefonica viene determinata in base a due elementi: l'attributo Usage assegnato alla route Phone e gli attributi di utilizzo dei criteri consentiti dal chiamante. Viene selezionata la prima route telefonica con un attributo di utilizzo che corrisponde all'utilizzo consentito del chiamante.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Questo attributo di nome distinto (DN) multivalore contiene un elenco di nomi distinti per l'utilizzo della route.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11032</strong></p>
<p>Questo attributo è un collegamento in avanti per il collegamento a ritroso corrispondente <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Questo attributo contiene il DN che punta al pool in cui deve passare tutto il traffico SIP indirizzato a questa MCU o a un servizio attendibile.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Questo attributo stringa UNICODE a valore singolo specifica il nome descrittivo della regola di normalizzazione, quindi può essere facilmente fatto riferimento da un amministratore.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SchemaVersion</p></td>
<td><p>Questo attributo rappresenta la versione dello schema attualmente distribuita nell'organizzazione.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-SearchMaxRequests (obsoleto)</p></td>
<td><p>Questo attributo limita il numero di risultati della ricerca da restituire da una ricerca della directory quando un utente cerca un contatto usando Communicator. Questo attributo sostituirà il valore fornito dal client.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Questo attributo limita il numero di richieste di ricerca restituite.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Questo attributo multivalore è un collegamento a ritroso che contiene un elenco di nomi distinti (DN). Questi DNs puntano a un pool o a un oggetto <strong>TrustedService</strong> .</p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti. Questi nomi distinti sono collegamenti di nuovo che fanno riferimento a altri oggetti server a cui è possibile assegnare un profilo di posizione predefinito.</p>
<p>Collegamento a ritroso: <strong>Link ID 11037</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento indietro è <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Questo attributo back link fa riferimento solo ai pool e ai server di mediazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Questo attributo definisce le informazioni sulla versione del server. Questo numero di versione si applica a tutti i ruoli del server. Si tratta di un numero intero uniformemente crescente che viene incrementato con ogni versione ufficiale del prodotto.</p>
<p>I valori validi possibili sono i seguenti:</p>
<ul>
<li><p>Non definito: Live Communications Server 2003</p>
<p>                 Live Communications Server 2005</p>
<p>                 Live Communications Server 2005 con SP1</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-tipooggettoorigine</p></td>
<td><p>Questo attributo a valore singolo di tipo integer specifica il tipo di oggetto a cui punta <strong>msDS-SourceObjectDN</strong> , come indicato di seguito:</p>
<ul>
<li><p>null | 0x00000001: rappresenta un oggetto utente principale di Windows NT Server da una foresta diversa</p></li>
<li><p>Gli attributi seguenti rappresentano un tipo di gruppo da un'altra foresta per l'espansione del gruppo di distribuzione:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: rappresenta un oggetto di accesso tramite operatore automatico o sottoscrittore della stessa foresta o di un'altra foresta</p></li>
</ul></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SubscriptionAuthRequired (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003.</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetHomeServer</p></td>
<td><p>Questo attributo consente di trasferire un utente o un oggetto contatto da un pool di Lync Server a un altro. Questo attributo viene aggiunto alla classe Contact, perché nella topologia di foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</p>
<p>Il valore valido è il DN del server di destinazione Standard Edition o del pool Front-end a cui deve essere spostato un utente.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Questo attributo di stringa a valore singolo contiene un modello o un intervallo di numeri di telefono da instradare ai gateway specificati definiti in <strong>msRTCSIP-gateway</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Questo attributo archivia le coppie nome/valore per i criteri di destinazione per gli utenti di Lync Server.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ID tenant</p></td>
<td><p>Questo attributo archivia l'identificatore univoco per un tenant.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsoleto)</p></td>
<td><p>Questo attributo viene usato dalla funzionalità vocale di Lync Server e contiene la stringa di traduzione da applicare al numero composto, se viene trovata una corrispondenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo della MCU. Si tratta di un attributo a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo del server che gestisce il server proxy. Questo attributo è a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Questo attributo è un attributo a valore singolo che rappresenta il nome di dominio completo di un server attendibile.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Questo attributo specifica il numero di versione di un server nell'elenco dei server attendibili.</p>
<p>I valori validi possibili sono i seguenti:</p>
<ul>
<li><p>NULL: Live Communications Server 2003</p></li>
<li><p>2: Live Communications Server 2005</p></li>
<li><p>3: Office Communications Server 2007</p></li>
<li><p>4: Office Communications Server 2007 R2</p></li>
<li><p>5: Lync Server 2010</p></li>
<li><p>6: Lync Server 2013</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServiceFlags</p></td>
<td><p>Questo attributo definisce le opzioni abilitate per il servizio attendibile.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceLinks</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti (DN) che fanno riferimento a un oggetto servizio attendibile, ad esempio un servizio di autenticazione a livello di Media Relay. Un servizio di autenticazione di inoltro multimediale (fisicamente collocato nell'Edge Server che gestisce il servizio di conferenza A/V) deve essere associato a un pool per supportare gli scenari audio per gli utenti remoti.</p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Questo attributo è un valore integer che definisce il numero di porta usato per connettersi al servizio GRUU.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Questo attributo è un valore stringa che definisce il tipo di servizio GRUU che rappresenta.</p>
<p>I tipi di servizio GRUU validi sono i seguenti:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Servizio di autenticazione Media Relay (MRA)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo di IIS che gestisce i servizi Web Lync Server. Si tratta di un attributo a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Questo attributo definisce diverse opzioni UC che sono abilitate globalmente a tutti gli oggetti utente o contatto. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata dalla presenza di un bit.</p>
<p>Il valore valido possibile (e la posizione di bit associata) sono i seguenti:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posizione bit 2)</p></li>
</ul>
<p>Quando questo bit è impostato, il criterio UC viene definito per ogni utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Questo attributo a valore singolo contiene il nome distinto (DN) del criterio UC assegnato dall'amministratore per l'utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsoleto)</p></td>
<td><p>Questo attributo fornisce un elenco di tutti i domini in una foresta che ospitano utenti abilitati per SIP. L'impostazione predefinita è un elenco vuoto, che indica che tutti i domini della foresta sono abilitati per SIP.</p>
<p>I valori validi sono più stringhe che rappresentano i nomi di dominio dei singoli domini.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserEnabled</p></td>
<td><p>Questo attributo determina se l'utente è attualmente abilitato per Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserExtension</p></td>
<td><p>Questo attributo multivalore contiene un elenco di coppie nome/valore nel formato &quot;nome = valore. &quot; Questo attributo è contrassegnato per la replica del catalogo globale.</p></td>
<td><p>Novità di Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Questo attributo contiene il nome distinto (DN) che punta a un oggetto profilo posizione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Questo attributo archivia le coppie nome/valore per i criteri utente.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Questo è un attributo multivalore che contiene un elenco di nomi distinti con Binary (DN_WITH_BINARY) che punta a criteri utente globali di tipi diversi. La parte binaria indica il tipo di criteri a cui punta il DN.</p>
<p>I valori binari validi sono i seguenti:</p>
<ul>
<li><p>0x00000001: criteri riunione</p></li>
<li><p>0x00000002: criteri UC</p></li>
<li><p>0x00000005: criteri di presenza</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Questo è l'ID del gruppo di routing SIP. Gli utenti nello stesso gruppo registreranno lo stesso server front-end.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Si tratta di un attributo multivalore. Questo attributo è riservato per un uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Questo attributo a valore singolo punta al pool o al server Standard Edition a cui appartengono i componenti Web.</p>
<p>Collegamento inoltra: <strong>ID collegamento 11028</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo forward link è <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Questo attributo è un elenco multivalore di nomi distinti. Questo attributo contiene un elenco di tutti i server Web associati al pool.</p>
<p>Collegamento a ritroso: <strong>Link ID 11029</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento indietro è <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WMIInstanceId (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003.</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>OtherIPPhone</p></td>
<td><p>Questo attributo Active Directory esistente viene usato dalla telefonia per specificare l'elenco di indirizzi TCP/IP alternativi per un telefono.</p></td>
<td><p>Nuovo sistema operativo Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Questo attributo Active Directory esistente viene usato dai componenti vocali in Lync Server, solo per gli oggetti contatto, allo scopo di instradare le chiamate ai numeri di accesso automatico e abbonato alla messaggistica unificata. L'indirizzo di inoltro di chiamata incondizionato è archiviato in questo attributo multivalore. Questo account viene creato per lo scopo specifico di operatore automatico e accesso sottoscrittore. Gli attributi di questo account non devono essere modificati dagli amministratori.</p></td>
<td><p>Nuovo sistema operativo Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Questo attributo multivalore di Active Directory esistente fa parte dello schema Active Directory di base introdotto in Windows 2000. Questo attributo contiene i vari indirizzi di indirizzi X400, X500 e SMTP della posta elettronica dell'utente. In Live Communications Server 2003 e versioni successive l'URI SIP dell'utente viene aggiunto all'elenco, usando il &quot;Tag SIP:&quot; .</p>
<p>Le applicazioni seguenti ricercano l'URI SIP dell'utente da questo attributo:</p>
<ul>
<li><p>Client di messaggistica e collaborazione di Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Nuovo sistema operativo Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Questo attributo Active Directory esistente contiene il numero di telefono per l'utente.</p></td>
<td><p>Nuovo sistema operativo Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

