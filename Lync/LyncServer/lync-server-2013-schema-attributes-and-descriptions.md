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
ms.openlocfilehash: cc1d6f5041564c1b865e49ef73a539f3addb75dd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-attributes-and-descriptions-in-lync-server-2013"></a>Attributi e descrizioni dello schema in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

In questa sezione vengono descritti tutti gli attributi dello schema utilizzati da Lync Server 2013. Per le classi associate agli attributi, vedere [schema Attributes by Class in Lync Server 2013](lync-server-2013-schema-attributes-by-class.md). Per un elenco di classi e attributi nuovi in Lync Server 2013, vedere [modifiche dello schema in Lync server 2013](lync-server-2013-schema-changes-in-lync-server-2013.md).

Gli attributi che sono coppie collegate sono specificati come collegamenti inoltrati o collegamenti indietro. Un attributo che fa riferimento a un altro oggetto è un collegamento in avanti. l'attributo dell'altro oggetto che fa riferimento al primo oggetto è un collegamento a ritroso. I collegamenti inoltrati sono aggiornabili, mentre i collegamenti indietro sono di sola lettura.

Alcuni attributi hanno un valore di maschera di bit. Per questi attributi, ogni impostazione è rappresentata da un bit e il valore decimale visualizzato rappresenta la posizione del bit. Le posizioni dei bit iniziano con il bit 0. Ad esempio, 1 (binario) è il bit 0 set e 10000 (binario) è bit 4 set. Ogni bit rappresenta una proprietà. Di seguito sono riportati alcuni esempi:

  - 10000 (binario) ha un valore decimale pari a 16, ovvero il bit 4 è impostato.

  - 100 milioni (binario) ha un valore decimale pari a 256 (ovvero il bit 8 è impostato).

  - 1100 (binario) ha un valore decimale pari a 12 (ovvero i bit 2 e 3 sono impostati, le proprietà rappresentate da entrambi i bit sono abilitate).

  - 1111000001 (binario) ha un valore decimale di 961 (ovvero i bit 0, 6, 7, 8 e 9 sono impostati, le proprietà per ognuno di questi bit sono abilitate).

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
<td><p>Un attributo esistente nei servizi di dominio Active Directory che ora è associato alle classi <strong>msRTCSIP-Pool</strong> e <strong>msRTCSIP-MonitoringServer</strong> . Questo attributo consente di specificare il nome di dominio completo (FQDN) di un pool o di un Monitoring Server.</p>
<p>Un valore valido per ogni segmento è di 63 caratteri; un valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Microsoft Office Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msDS-SourceObjectDN</p></td>
<td><p>Questo attributo contiene la rappresentazione di stringa del nome distinto (DN) dell'oggetto in un'altra foresta corrispondente a questo oggetto. Questo attributo viene utilizzato per l'espansione del gruppo di distribuzione e la frequenza automatica. Questo attributo è definito nello schema predefinito di Active Directory per Windows Server 2003 R2.</p>
<p>Per evitare di richiedere un aggiornamento di AD DS a Windows Server 2003 R2, la preparazione dello schema di Active Directory estende lo schema di Windows Server 2003 con questa definizione di attributo.</p></td>
<td><p>Nuovo in Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msExchUCVoiceMailSettings</p></td>
<td><p>Questo attributo multivalore contiene le impostazioni della segreteria telefonica. Questo attributo è condiviso con la messaggistica unificata di Exchange.</p></td>
<td><p>Nuovo in Microsoft Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>Questo attributo multivalore contiene gli identificatori per i criteri di blocco che si applicano all'utente. I criteri di conservazione conservano gli elementi della cassetta postale per l'utente per tutta la durata del blocco. Questo attributo è condiviso con Exchange 2013.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-AcpInfo</p></td>
<td><p>Questo attributo archivia le informazioni relative ai provider di servizi di audioconferenza per un utente.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationDestination</p></td>
<td><p>Questo attributo punta alla voce del servizio attendibile per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Application</p></td>
<td><p>Questo attributo contiene un elenco delle applicazioni ospitate nel server applicazioni.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationOptions</p></td>
<td><p>Questo attributo consente di specificare le opzioni per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationPrimaryLanguage</p></td>
<td><p>Questo attributo contiene la lingua principale per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationSecondaryLanguages</p></td>
<td><p>Questo attributo multivalore contiene le lingue secondarie per il contatto dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerBL</p></td>
<td><p>Questo attributo contiene un elenco di server applicazioni appartenenti al pool. Il collegamento in avanti corrispondente a questo attributo di collegamento a ritroso è <strong>msRTCSIP-ApplicationServerPoolLink</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerPoolLink</p></td>
<td><p>Questo attributo punta al pool a cui appartiene il server applicazioni. Si tratta del collegamento in avanti. Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ApplicationServerBL</strong>.</p></td>
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
<td><p>Questo attributo specifica l'impostazione predefinita globale all'interno del limite della foresta per l'archiviazione di tutte le comunicazioni degli utenti. Questo viene applicato dal livello dell'agente di archiviazione. L'intervallo di valori per questo attributo è il seguente:</p>
<ul>
<li><p><strong>True</strong>: archivia tutti gli utenti</p></li>
<li><p><strong>False</strong>: non archiviare tutti gli utenti</p></li>
</ul>
<p>Questo attributo controlla globalmente, all'interno del limite della foresta, la modalità di archiviazione delle comunicazioni degli utenti all'interno di una rete interna.</p>
<p><strong>Comportamento di Live Communications Server 2005 (ora ritirato)</strong></p>
<p>L'intervallo di valori per questo attributo è il seguente:</p>
<ul>
<li><p>0: archivia il corpo del messaggio [bit 0]</p></li>
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
<td><p>Questo attributo è un numero intero utilizzato come campo di bit per controllare se le comunicazioni di un singolo utente devono essere archiviate. Questo controllo viene applicato dal livello dell'agente di archiviazione. È contrassegnata per la replica del catalogo globale.</p>
<p>L'ambito di questo attributo è specifico di un singolo utente o di un contatto. Di seguito sono riportati i valori validi (e le posizioni dei bit associati) in Lync Server:</p>
<ul>
<li><p>0: non archiviare (nessun bit impostato)</p></li>
<li><p>1: ritirato (posizione bit 0)</p></li>
<li><p>2: ritirato (posizione bit 1)</p></li>
<li><p>4: archiviazione delle comunicazioni interne (posizione bit 2)</p></li>
<li><p>8: archiviare le comunicazioni federate (posizione bit 3)</p></li>
</ul>
<p>I valori precedentemente validi in Live Communications Server 2005 sono i seguenti:</p>
<ul>
<li><p>0: utilizzare il valore predefinito definito da <strong>msRTCSIP-ArchiveDefault</strong> e <strong>msRTCSIP-ArchiveFederation (</strong> nell'ordine di precedenza:</p>
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
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServerVersion (obsoleto)</p></td>
<td><p>Questo attributo definisce la versione del servizio di archiviazione. Questo attributo è un tipo di valore integer con incremento monotona che si incrementa con ogni versione ufficiale del prodotto. I valori validi possibili sono i seguenti:</p>
<ul>
<li><p>Indefinito: Live Communications Server 2003</p>
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
<td><p>Questo attributo consente di specificare il nome di dominio completo del server back-end del pool. Poiché può essere presente un solo server back-end per pool, si tratta di un attributo a valore singolo.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryHomePool</p></td>
<td><p>Questo attributo contiene l'identificatore del pool che ospita la directory conferenze.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectoryId</p></td>
<td><p>Questo attributo contiene l'identificatore di una directory conferenze.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectoryTargetPool</p></td>
<td><p>Questo attributo contiene l'identificatore del pool in cui viene spostata la directory conferenze.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-default</p></td>
<td><p>Questo attributo booleano definisce se l'utilizzo del telefono è un utilizzo predefinito. Se questo attributo è impostato su <strong>true</strong>, l'utilizzo del telefono è un utilizzo predefinito e non può essere eliminato dall'amministratore. Se questo attributo è impostato su <strong>false</strong>, l'utilizzo può essere eliminato.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWAExternalURL</p></td>
<td><p>Questo attributo identifica l'URL di Communicator Web Access per gli utenti esterni all'organizzazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultCWAInternalURL</p></td>
<td><p>Questo attributo identifica l'URL di Communicator Web Access per gli utenti che si trovano all'interno dell'organizzazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultLocationProfileLink (obsoleto)</p></td>
<td><p>Questo attributo a valore singolo contiene il nome distinto (DN) di un oggetto classe del profilo percorso assegnato.</p>
<p>Collegamento in avanti: <strong>Link ID 11036</strong></p>
<p>Il collegamento a ritroso corrispondente è <strong>msRTCSIP-ServerReferenceBL</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultPolicy (obsoleto)</p></td>
<td><p>Questo attributo booleano specifica se il criterio è un criterio predefinito. Il criterio è un criterio predefinito quando è impostato su <strong>true</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultRouteToEdgeProxy (obsoleto)</p></td>
<td><p>Questo attributo specifica il nome di dominio completo del server perimetrale che esegue il servizio Access Edge, se è possibile accedervi direttamente oppure del dispositivo di bilanciamento del carico hardware per un pool di server che eseguono il servizio Access Edge. Se è possibile accedere ai server che eseguono il servizio Access Edge solo tramite uno o più amministratori, questo attributo specifica il nome di dominio completo e, facoltativamente, il numero di porta del Director o del dispositivo di bilanciamento del carico hardware che serve un pool di server Director.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefaultRouteToEdgeProxyPort (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero di porta da utilizzare per la connessione al server che esegue il servizio Access Edge.</p>
<p>Il valore valido è un valore intero che specifica la porta da utilizzare. Il valore predefinito è 5061.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il periodo di timeout della sottoscrizione di presenza predefinita.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DefRegistrationTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout predefinita per la registrazione.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout predefinita per la sottoscrizione dei dati di roaming.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DeploymentLocator</p></td>
<td><p>Questo attributo viene utilizzato in una topologia di domini divisi e contiene un nome di dominio completo (FQDN).</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Description (obsoleto)</p></td>
<td><p>Questo attributo di stringa UNICODE a valore singolo contiene una descrizione descrittiva della regola di normalizzazione o della linea telefonica.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-DomainData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DomainName</p></td>
<td><p>Questo attributo rappresenta un dominio configurato per il servizio di registrazione.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EdgeProxyData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxyFQDN</p></td>
<td><p>Questo attributo consente di specificare il nome di dominio completo del server che esegue il servizio Access Edge.</p>
<p>Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnableBestEffortNotify (obsoleto)</p></td>
<td><p>Questo attributo consente di controllare se un server genera una richiesta di notifica per i migliori tentativi, anziché una richiesta di notifica, in risposta a una richiesta di sottoscrizione da un client. La notifica è un'estensione per l'ottimizzazione delle prestazioni per l'handshake delle notifiche di sottoscrizione in cui il server genera le richieste di notifica, anziché le richieste di notifica normali. Il vantaggio delle prestazioni è che una richiesta di notifica non richiede una risposta di 200 OK da parte del client come richiesto dalla richiesta NOTIFY.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p>
<div>

> [!NOTE]  
> Live Communications Server 2003 non supporta le richieste di notifica. Per interagire con le applicazioni server scritte con l'API del server Live Communications Server 2003 in esecuzione su Live Communications Server 2005 e server di terze parti, è possibile disabilitare le richieste di notifica impostando il relativo valore su <STRONG>false</STRONG>. La notifica non è attualmente parte del processo di standardizzazione SIP di IETF (Internet Engineering Task Force).


</div></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnableFederation (obsoleto)</p></td>
<td><p>Questo attributo è un'opzione globale che gli amministratori IT utilizzano per configurare se gli utenti sono autorizzati a comunicare con utenti di altre organizzazioni. Consente a un amministratore di sovrascrivere l'attributo <strong>FederationEnabled</strong> di un singolo utente. Questo attributo può essere utile per proteggere la rete interna da attacchi Internet che possono essere causati da worm, virus o attacchi mirati per la società.</p>
<p>Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</p>
<ul>
<li><p>1: abilitato per la connettività per la messaggistica istantanea pubblica (posizione bit 0)</p></li>
<li><p>2: riservato (posizione bit 1)</p></li>
<li><p>4: riservato (posizione bit 2)</p></li>
<li><p>8: riservato (posizione bit 3)</p></li>
<li><p>16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</p></li>
<li><p>128: UCEnabled (abilitare gli utenti per le comunicazioni unificate) (posizione bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posizione bit 9)</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServices</p></td>
<td><p>Questo attributo indica se i servizi Enterprise sono caricati sul server specificato.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ExtensionData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ExternalAccessCode</p></td>
<td><p>Questo attributo contiene il codice di chiamata per l'accesso esterno.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-FederationEnabled</p></td>
<td><p>Questo attributo consente di controllare se un singolo utente è abilitato per la Federazione. Viene applicato dal livello Enterprise Services. È contrassegnata per la replica del catalogo globale.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-FrontEndServers</p></td>
<td><p>Questo attributo è un elenco multivalore dei nomi di dominio di tutti i server Enterprise Edition associati a un pool.</p>
<p>Collegamento a ritroso: <strong>Link ID 11023</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-PoolAddress</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Gateways (obsoleto)</p></td>
<td><p>Questo attributo di stringa multivalore contiene un elenco di gateway e porte (per gateway).</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalSettingsData (obsoleto)</p></td>
<td><p>Questo attributo archivia le coppie nome: valore. La coppia nome-valore già definita è per l'impostazione <strong>Consenti polling per la presenza</strong> .</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GroupingID</p></td>
<td><p>Questo attributo è un identificatore univoco di un gruppo utilizzato per raggruppare le voci della Rubrica.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-HomeServer (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003 (non utilizzato).</p>
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
<td><p>Nuovo in Live Communications Server 2003 (non utilizzato).</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-InternetAccessEnabled</p></td>
<td><p>Questo attributo consente di controllare se un singolo utente è abilitato per l'accesso utente esterno. Viene applicato dal livello Enterprise Services. È contrassegnata per la replica del catalogo globale.</p>
<p>I valori validi sono <strong>true</strong> o <strong>false</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Master (obsoleto)</p></td>
<td><p>-</p></td>
<td><p>Nuovo in Live Communications Server 2003</p>
<p>Obsoleto in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-line</p></td>
<td><p>Questo attributo a valore singolo contiene l'ID del dispositivo, ovvero l'URI SIP o l'URI TEL del telefono utilizzato dai controlli utente, utilizzati da Lync per la telefonia. Questo attributo è contrassegnato per la replica del catalogo globale ed è indicizzato. Se un utente è abilitato per VoIP aziendale, questo attributo archivia la versione normalizzata E. 164 del numero di telefono dell'utente.</p></td>
<td><p>Nuovo in Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LineServer</p></td>
<td><p>Questo attributo a valore singolo contiene l'URI SIP del server gateway CSTA-SIP. Questo attributo è contrassegnato per la replica del catalogo globale ma non è indicizzato.</p></td>
<td><p>Nuovo in Microsoft Office Live Communications Server 2005 con SP1</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizationData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalizationLinks (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti (DN) di normalizzazione locali associati a questo profilo località. Il tipo di questo attributo è un file binario DN. Esiste una relazione uno-a-molti tra il profilo percorso e le regole di normalizzazione locali. L'ordinamento dell'elenco dei DNs di normalizzazione locale deve essere mantenuto nell'ordine specificato dall'amministratore. La conservazione dell'ordine viene mantenuta dalla parte binaria del file binario DN, che specifica l'indice dell'ordine.</p>
<p>Collegamento in avanti: <strong>Link ID 11034</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-locationProfileBL</strong>.</p></td>
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
<td><p>Questo attributo a valore singolo contiene un nome descrittivo per il profilo percorso che indica la posizione rappresentata dal profilo. Poiché è possibile disporre di più profili percorso, l'amministratore deve disporre di un modo per distinguere i diversi profili.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-locationProfileBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco dei nomi distinti del profilo percorso. Questo attributo consente di specificare il collegamento a ritroso a uno o più profili percorso.</p>
<p>Collegamento a ritroso: <strong>Link ID 11035</strong></p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-LocalNormalizationLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfileData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfileOptions</p></td>
<td><p>Questo attributo contiene le opzioni per il profilo località.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MappingContact</p></td>
<td><p>Questo attributo multivalore contiene un elenco di contatti dell'applicazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MappingLocation</p></td>
<td><p>Questo attributo multivalore contiene un elenco di profili località.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxNumOutstandingSearchPerServer (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero massimo di richieste di ricerca in sospeso per ogni server.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxNumSubscriptionsPerUser (obsoleto)</p></td>
<td><p>L'attributo rappresenta il numero massimo di sottoscrizioni per utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxPresenceSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout massima per la sottoscrizione.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MaxRegistrationsTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout massima per le registrazioni.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MaxRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout massima per le sottoscrizioni dei dati di roaming.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryAddress</p></td>
<td><p>Questo attributo è un attributo del punto di controllo del servizio nella classe computer che specifica un collegamento alla Factory di unità di controllo multipunto a cui appartiene. Questo punto di controllo del servizio e l'attributo viene creato per ogni MCU Microsoft. Ogni MCU Microsoft deve individuare il server back-end del pool a cui appartiene, per poter recuperare le impostazioni a livello di pool.</p>
<p>Il valore di questo attributo è il nome distinto (DN) della factory MCU. Si tratta di un attributo a valore singolo e contrassegnato per la replica del catalogo globale.</p>
<p>Collegamento in avanti: <strong>Link ID 11026</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-MCUServers</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryData</p></td>
<td><p>Si tratta di un attributo riservato a più stringhe. Le impostazioni archiviate in questo attributo sono rappresentate come coppie nome = valore. Le coppie nome/valore attualmente definite sono le seguenti:</p>
<ul>
<li><p>FactoryURL = &lt;URL&gt;</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactoryPath</p></td>
<td><p>Si tratta di un attributo a valore singolo che contiene il nome distinto (DN) di una singola factory MCU associata a un pool.</p>
<p>Collegamento in avanti: <strong>Link ID 11024</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-PoolAddresses</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryProviderID</p></td>
<td><p>Questo attributo è una stringa a valore singolo che specifica il GUID del provider di factory MCU. In base al valore GUID, il processo di factory MCU determina se si desidera eseguire il servizio di questo tipo di MCU. Se il valore GUID è <strong>{F0810510-424f-46ef-84fe-6CC720DF1791}</strong>, il processo factory MCU (disponibile per impostazione predefinita in Lync Server) lo elaborerà. Per qualsiasi altro valore GUID, il processo di factory MCU non servirà il tipo di MCU.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUServers</p></td>
<td><p>Questo attributo è un elenco multivalore di nomi distinti (DN). Questo attributo contiene un elenco di tutti i server MCU dello stesso tipo e fornitore associato a questa factory MCU. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p>
<p>Collegamento a ritroso: Link ID 11027</p>
<p>Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryAddress</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUType</p></td>
<td><p>Questo attributo è una stringa a valore singolo che specifica il supporto che può essere gestito dalla MCU.</p>
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
<td><p>Questo attributo è una stringa a valore singolo che specifica il nome di un fornitore di MCU. Tutti i MCU di Microsoft specificano questo attributo come <strong>Microsoft Corporation</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MeetingFlags (obsoleto)</p></td>
<td><p>Questo attributo definisce diverse opzioni di riunione che sono abilitate a livello globale per tutti gli utenti o gli oggetti contatto. Questo attributo è un valore della maschera di bit di tipo Integer.</p>
<p>Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</p>
<ul>
<li><p>0: AllowOrganizeMeetingWithAnonymousParticipants è None (non consentire agli utenti di invitare utenti anonimi alle riunioni) (nessun bit impostato)</p></li>
<li><p>4: AllowOrganizeMeetingWithAnonymousParticipants è Everyone (Consenti a tutti gli utenti di invitare utenti anonimi alle riunioni) (posizione bit 2)</p></li>
<li><p>8: AllowOrganizeMeetingWithAnonymousParticipants è UsePerUserSetting (consente agli utenti di invitare utenti anonimi alle riunioni in base all'impostazione per utente) (posizione bit 3)</p></li>
<li><p>16: UserPerUserMeetingPolicy (il criterio di riunione è definito per utente) (posizione bit 4)</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MeetingPolicy (obsoleto)</p></td>
<td><p>Questo attributo specifica il nome distinto (DN) del criterio che l'amministratore ha assegnato per l'utente come attributo a valore singolo.</p></td>
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
<td><p>Questo attributo rappresenta la finestra di timeout minima per la registrazione.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MinRoamingDataSubscriptionTimeout (obsoleto)</p></td>
<td><p>Questo attributo rappresenta la finestra di timeout minima per la sottoscrizione dei dati di roaming.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>Questo attributo viene utilizzato per archiviare il backend di SQL Server con mirroring utilizzato dal pool Front end.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MobilityFlags</p></td>
<td><p>Questo attributo contiene le opzioni e i flag che definiscono le impostazioni per i dispositivi mobili.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MobilityPolicy</p></td>
<td><p>Questo attributo contiene il nome distinto per un oggetto dei criteri per dispositivi mobili.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-NumDevicesPerUser (obsoleto)</p></td>
<td><p>Questo attributo rappresenta il numero consentito di dispositivi in cui un utente può registrarsi per le comunicazioni SIP e sottoscrivere la presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OptionFlags</p></td>
<td><p>Questo attributo consente di specificare le opzioni abilitate per l'utente o l'oggetto contatto. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata da un bit. Questo attributo è contrassegnato per la replica del catalogo globale.</p>
<p>Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</p>
<ul>
<li><p>1: abilitato per la connettività di messaggistica istantanea pubblica (posizione bit 0)</p></li>
<li><p>2: riservato (posizione bit 1)</p></li>
<li><p>4: riservato (posizione bit 2)</p></li>
<li><p>8: riservato (posizione bit 3)</p></li>
<li><p>16: controllo delle chiamate remote abilitato [telefonia] (posizione bit 4)</p></li>
<li><p>64: AllowOrganizeMeetingWithAnonymousParticipants (Consenti agli utenti di invitare utenti anonimi alle riunioni (posizione bit 6)</p></li>
<li><p>128: UCEnabled (Abilita gli utenti per UC) (posizione bit 7)</p></li>
<li><p>256: EnabledForEnhancedPresence (abilitare l'utente per la connettività per la messaggistica istantanea pubblica) (posizione bit 8)</p></li>
<li><p>512: RemoteCallControlDualMode (posizione bit 9)</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-OriginatorSID</p></td>
<td><p>Questo attributo viene utilizzato nelle topologie a foresta centrale e a risorse per abilitare l'accesso Single Sign-on quando un utente di attributo objectSID dall'account principale di Windows NT viene copiato in questo attributo dell'oggetto utente o contatto corrispondente nella foresta di risorse o nel bosco centrale. Communicator Web Access esegue la ricerca di un utente in servizi di dominio Active Directory utilizzando questo attributo o l'attributo objectSid dell'utente. Questo attributo è contrassegnato per la replica del catalogo globale.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-OwnerUrn</p></td>
<td><p>Questo attributo è il nome dell'URN (Uniform Resource Name) del proprietario per un contatto dell'applicazione.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-pattern (obsoleto)</p></td>
<td><p>Questo attributo di stringa a valore singolo contiene un modello utilizzato per la corrispondenza dei numeri di composizione nel formato E. 164. Se il numero di composizione corrisponde a questo modello, la conversione viene applicata al numero composto.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti (DN) della route telefonica. Questo attributo consente di specificare il collegamento a ritroso a una o più route telefoniche.</p>
<p>Collegamento a ritroso: <strong>Link ID 11033</strong></p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-RouteUsageLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRouteData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRouteName (obsoleto)</p></td>
<td><p>Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della route telefonica, in modo che sia possibile fare riferimento facilmente all'amministratore.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneUsageData (obsoleto)</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyContent (obsoleto)</p></td>
<td><p>Questo attributo è una stringa Unicode a valore singolo. Questo attributo stringa contiene la definizione dei criteri in formato XML. La definizione dello schema XML è comune nei diversi tipi di criteri, solo le impostazioni sono diverse per ogni tipo di criterio.</p>
<p>La definizione dello schema XML (XSD) è definita nel modo seguente:</p>
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
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PolicyType (obsoleto)</p></td>
<td><p>Questo attributo di stringa Unicode a valore singolo contiene il tipo di criterio. I tipi di criteri validi sono i seguenti:</p>
<ul>
<li><p>riunione</p></li>
<li><p>telefonia</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolAddress</p></td>
<td><p>Questo attributo consente di specificare un collegamento al pool a cui appartiene un computer. Questo attributo è impostato indipendentemente dal fatto che il computer esegua la versione Standard Edition o Enterprise Edition di Lync Server. Questo attributo è contrassegnato per la replica del catalogo globale.</p>
<p>Il valore valido è il nome di dominio del pool.</p>
<p>Collegamento in avanti: <strong>Link ID 11022</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-FrontEndServers</strong>.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolAddresses</p></td>
<td><p>Questo attributo multivalore contiene un elenco dei nomi distinti (DN) dei pool a cui è associata la factory MCU.</p>
<p>Collegamento a ritroso: <strong>Link ID 11025</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-MCUFactoryPath</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolDisplayName</p></td>
<td><p>Questo attributo consente di specificare un nome arbitrario per un pool visualizzato dalla console di gestione. Questo nome può essere modificato dall'amministratore.</p>
<p>Il valore valido è una stringa che rappresenta il nome di un pool.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolDomainFQDN</p></td>
<td><p>Questo attributo è un valore stringa a valore singolo. Il valore di questo attributo, se presente, rappresenta il nome di dominio completo del pool se l'amministratore vuole creare un pool Front end con un FQDN non conforme alla struttura di dominio Active Directory in cui è stato creato il pool Front End, ad esempio un SIP spazio dei nomi disgiunto dallo spazio dei nomi DNS (Domain Name System)).</p>
<p>È consigliabile mappare l'FQDN del dominio del pool Front end alla porzione del nome di dominio come dominio Active Directory in cui risiede il pool. Pertanto, quando nell'attributo non è presente alcun valore, il nome di dominio completo del pool Front End verrà impostato come predefinito per la struttura di domini di Active Directory, come indicato dall'attributo <strong>dNSHostName</strong> .</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolFunctionality</p></td>
<td><p>Un elenco multivalore dei nomi di dominio di tutti i server Lync Server, Enterprise Edition associati a un pool. Questo attributo di tipo Integer definisce se il pool è in grado di messaggistica istantanea e presenza e riunioni.</p>
<p>I possibili tipi di valore validi sono i seguenti:</p>
<ul>
<li><p>Indefinito: servizio di messaggistica istantanea e presenza (Live Communications Server 2005 e 2003)</p></li>
<li><p>1: servizio di messaggistica istantanea e presenza (Lync Server)</p></li>
<li><p>2: servizio di messaggistica istantanea e presenza e riunione (Lync Server)</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolType</p></td>
<td><p>Questo attributo specifica se in un pool di server è in esecuzione il server Standard Edition o il server Enterprise Edition. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata da un bit.</p>
<p>Di seguito sono riportati i valori validi (e le posizioni dei bit associati):</p>
<ul>
<li><p>1: Server Standard Edition, utenti host (posizione bit 0)</p></li>
<li><p>2: Server Enterprise Edition, utenti host (posizione bit 1)</p></li>
<li><p>4: Server Standard Edition, applicazioni host (posizione bit 2)</p></li>
<li><p>8: Server Enterprise Edition, applicazioni host (posizione bit 3)</p></li>
</ul>
<p>Poiché Lync Server non supporta i pool che ospitano solo le applicazioni, gli unici valori validi sono i seguenti:</p>
<ul>
<li><p>5: Server Standard Edition, ospita utenti e applicazioni (posizioni di bit 0 e 2)</p></li>
<li><p>10: Server Enterprise Edition, ospita utenti e applicazioni (posizioni di bit 1 e 3)</p></li>
</ul></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PoolVersion</p></td>
<td><p>Questo attributo definisce la versione del pool. Si tratta di un tipo intero che viene incrementato con ogni versione di prodotto principale.</p>
<p>I possibili tipi di valore validi sono i seguenti:</p>
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
<td><p>Questo attributo contiene le opzioni e i flag che definiscono le impostazioni di presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PresencePolicy</p></td>
<td><p>Questo attributo contiene il nome distinto per un oggetto criterio di presenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrimaryHomeServer</p></td>
<td><p>Questo attributo consente a un utente o a un contatto per la messaggistica SIP. Viene aggiunto alla classe Contact perché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</p>
<p>Il valore valido è il nome distinto del server Standard Edition o del pool Enterprise Edition front end in cui è ospitato un utente.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>Questo attributo contiene l'indirizzo SIP di un utente specificato.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PrivateLine</p></td>
<td><p>Questo attributo contiene l'ID del dispositivo della linea privata.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-instradabile</p></td>
<td><p>Questo attributo è un attributo booleano utilizzato per determinare se Lync Server è autorizzato a eseguire il routing a questo servizio utilizzando il relativo indirizzo GRUU. Se questo valore è impostato su <strong>true</strong>, Lync Server è autorizzato a eseguire il routing a questo servizio. Se questo valore è impostato su <strong>false</strong>, Lync Server non è autorizzato a eseguire il routing a questo servizio.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsageAttribute (obsoleto)</p></td>
<td><p>Questo attributo di stringa UNICODE a valore singolo definisce un attributo che qualifica l'utilizzo di una route telefonica. La selezione di una route telefonica è determinata in base a due elementi: l'attributo Usage assegnato alla route Phone e gli attributi di utilizzo dei criteri consentiti dal chiamante. Viene selezionata la prima route telefonica con un attributo di utilizzo che corrisponde all'utilizzo consentito del chiamante.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsageLinks (obsoleto)</p></td>
<td><p>Questo attributo con nome distinto (DN) multivalore contiene un elenco di nomi distinti per l'utilizzo delle route.</p>
<p>Collegamento in avanti: <strong>Link ID 11032</strong></p>
<p>Questo attributo è un collegamento in avanti per il collegamento a ritroso corrispondente <strong>msRTCSIP-PhoneRouteBL</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RoutingPoolDN</p></td>
<td><p>Questo attributo contiene il nome distinto che punta al pool che tutto il traffico SIP indirizzato a questa MCU o a un servizio attendibile deve passare attraverso.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RuleName (obsoleto)</p></td>
<td><p>Questo attributo di stringa UNICODE a valore singolo specifica il nome descrittivo della regola di normalizzazione, in modo che possa essere facilmente referenziato da un amministratore.</p></td>
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
<td><p>Questo attributo consente di limitare il numero di risultati di ricerca da restituire da una ricerca di directory quando un utente cerca un contatto tramite Communicator. Questo attributo ignorerà il valore fornito dal client.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-SearchMaxResults (obsoleto)</p></td>
<td><p>Questo attributo limita il numero di richieste di ricerca restituite.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerBL</p></td>
<td><p>Questo attributo multivalore è un collegamento a ritroso contenente un elenco di nomi distinti (DN). Tali DNs puntano a un oggetto pool o <strong>TrustedService</strong> .</p>
<p>Questo attributo corrisponde al collegamento in avanti <strong>msRTCSIP-TrustedServiceLinks</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ServerReferenceBL (obsoleto)</p></td>
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti. Questi nomi distinti sono collegamenti indietro che fanno riferimento ad altri oggetti server a cui è possibile assegnare un profilo percorso predefinito.</p>
<p>Collegamento a ritroso: <strong>Link ID 11037</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-DefaultLocationProfileLink</strong>.</p>
<p>Questo attributo di collegamento a ritroso fa riferimento solo ai pool e ai Mediation Server.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ServerVersion</p></td>
<td><p>Questo attributo definisce le informazioni sulla versione del server. Questo numero di versione si applica a tutti i ruoli del server. Si tratta di un numero intero monotonamente crescente che si incrementi con ogni versione del prodotto ufficiale.</p>
<p>I possibili valori validi sono i seguenti:</p>
<ul>
<li><p>Indefinito: Live Communications Server 2003</p>
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
<li><p>Gli attributi seguenti rappresentano un tipo di gruppo proveniente da una foresta diversa per l'espansione del gruppo di distribuzione:</p>
<ul>
<li><p>0x00000002: ADS_GROUP_TYPE_GLOBAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_DOMAIN_LOCAL_GROUP</p></li>
<li><p>0x00000004: ADS_GROUP_TYPE_LOCAL_GROUP</p></li>
<li><p>0x00000008: ADS_GROUP_TYPE_UNIVERSAL_GROUP</p></li>
<li><p>0x80000000: ADS_GROUP_TYPE_SECURITY_ENABLED</p></li>
<li><p>0x90000000: rappresenta un oggetto di accesso sottoscrittore o operatore automatico dalla stessa foresta o da una foresta diversa</p></li>
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
<td><p>Questo attributo consente di spostare un utente o un oggetto contatto da un pool di Lync Server a un altro. Questo attributo viene aggiunto alla classe Contact, poiché nella topologia della foresta centrale gli oggetti contatto, non gli oggetti utente, sono abilitati per SIP.</p>
<p>Il valore valido è il nome distinto del server di destinazione Standard Edition o del pool Front end a cui deve essere spostato un utente.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TargetPhoneNumber (obsoleto)</p></td>
<td><p>Questo attributo di stringa a valore singolo contiene un modello o un intervallo di numeri di telefono da instradare ai gateway specificati definiti in <strong>msRTCSIP-Gateways</strong>.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TargetUserPolicies</p></td>
<td><p>Questo attributo archivia le coppie nome/valore per i criteri di destinazione per gli utenti di Lync Server.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TenantId</p></td>
<td><p>Questo attributo archivia l'identificatore univoco per un tenant.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Translation (obsoleto)</p></td>
<td><p>Questo attributo viene utilizzato dalla funzionalità vocale di Lync Server e contiene la stringa di conversione da applicare al numero composto, se viene trovata una corrispondenza.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p>
<p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCUData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo dell'MCU. Si tratta di un attributo a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxyData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxyFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo del server che esegue il server proxy. Questo attributo è a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServerFQDN</p></td>
<td><p>Questo attributo è un attributo a valore singolo che rappresenta il nome di dominio completo di un server attendibile.</p></td>
<td><p>Nuovo in Live Communications Server 2005.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServerVersion</p></td>
<td><p>Questo attributo consente di specificare il numero di versione di un server nell'elenco dei server attendibili.</p>
<p>I possibili valori validi sono i seguenti:</p>
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
<td><p>Questo attributo multivalore contiene un elenco di nomi distinti (DN) che fanno riferimento a un oggetto servizio attendibile, ad esempio un servizio di autenticazione di inoltro multimediale. Un servizio di autenticazione di inoltro multimediale (collocato fisicamente nel server perimetrale che esegue il servizio A/V Conferencing) deve essere associato a un pool per il supporto degli scenari audio per gli utenti remoti.</p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-ServerBL</strong>.</p></td>
<td><p>UC</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedServicePort</p></td>
<td><p>Questo attributo è un valore integer che definisce il numero di porta utilizzato per la connessione al servizio di GRUU.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServiceType</p></td>
<td><p>Questo attributo è un valore stringa che definisce il tipo di servizio di GRUU che rappresenta.</p>
<p>I tipi di servizio GRUU validi sono i seguenti:</p>
<ul>
<li><p>MediationServer</p></li>
<li><p>Gateway</p></li>
<li><p>Servizio di autenticazione di MRAS (Media Relay Authentication Service)</p></li>
<li><p>QoSM</p></li>
<li><p>msRTCSIP-UserExtension CWA</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServerData</p></td>
<td><p>Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServerFQDN</p></td>
<td><p>Questo attributo è un valore stringa che contiene il nome di dominio completo di IIS in cui sono in esecuzione i servizi Web di Lync Server. Si tratta di un attributo a valore singolo. Il valore valido per ogni segmento è di 63 caratteri; il valore valido per l'intero FQDN è 255 caratteri.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UCFlags (obsoleto)</p></td>
<td><p>Questo attributo definisce diverse opzioni UC che sono abilitate a livello globale a tutti gli oggetti utente o contatti. Questo attributo è un valore della maschera di bit di tipo Integer. Ogni opzione è rappresentata dalla presenza di un bit.</p>
<p>Il valore possibile valido (e la posizione bit associata) è il seguente:</p>
<ul>
<li><p>4: UsePerUserUCPolicy (posizione bit 2)</p></li>
</ul>
<p>Quando questo bit è impostato, il criterio UC è definito per ogni utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UCPolicy (obsoleto)</p></td>
<td><p>Questo attributo a valore singolo contiene il nome distinto (DN) del criterio UC che l'amministratore ha assegnato per l'utente.</p></td>
<td><p>Obsoleto in Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserDomainList (obsoleto)</p></td>
<td><p>Questo attributo fornisce un elenco di tutti i domini in una foresta che ospitano gli utenti abilitati per SIP. L'impostazione predefinita è un elenco vuoto che indica che tutti i domini nella foresta sono abilitati per SIP.</p>
<p>I valori validi sono più stringhe che rappresentano i nomi di dominio di singoli domini.</p></td>
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
<td><p>Nuovo in Live Communications Server 2005 con SP1.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserLocationProfile</p></td>
<td><p>Questo attributo contiene il nome distinto (DN) che punta a un oggetto profilo percorso.</p></td>
<td><p>Nuovo in Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserPolicies</p></td>
<td><p>Questo attributo archivia le coppie nome/valore per i criteri utente.</p></td>
<td><p>Nuovo in Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-UserPolicy</p></td>
<td><p>Si tratta di un attributo multivalore contenente un elenco di nomi distinti con Binary (DN_WITH_BINARY) che puntano ai criteri utente globali di tipi diversi. La parte binaria indica il tipo di criterio a cui fa riferimento la parte DN.</p>
<p>I valori binari validi sono i seguenti:</p>
<ul>
<li><p>0x00000001: criteri per le riunioni</p></li>
<li><p>0x00000002: criteri UC</p></li>
<li><p>0x00000005: criteri di presenza</p></li>
</ul></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>Questo è l'ID del gruppo di routing SIP. Gli utenti dello stesso gruppo registreranno lo stesso front end server.</p></td>
<td><p>Nuovo in Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsData</p></td>
<td><p>Si tratta di un attributo multivalore. Questo attributo è riservato per uso futuro.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsPoolAddress</p></td>
<td><p>Questo attributo a valore singolo punta al pool o al server Standard Edition a cui appartengono i componenti Web.</p>
<p>Collegamento in avanti: <strong>Link ID 11028</strong></p>
<p>Il collegamento a ritroso corrispondente a questo attributo di collegamento in avanti è <strong>msRTCSIP-WebComponentsServers</strong>.</p></td>
<td><p>Nuovo in Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentsServers</p></td>
<td><p>Questo attributo è un elenco multivalore di nomi distinti. Questo attributo contiene un elenco di tutti i server Web associati al pool.</p>
<p>Collegamento a ritroso: <strong>Link ID 11029</strong></p>
<p>Il collegamento in avanti corrispondente a questo collegamento a ritroso è <strong>msRTCSIP-WebComponentsPoolAddress</strong>.</p></td>
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
<td><p>Questo attributo esistente di Active Directory viene utilizzato dalla telefonia per specificare l'elenco di indirizzi TCP/IP alternativi per un telefono.</p></td>
<td><p>Nuovo sistema operativo Windows Server 2008.</p></td>
</tr>
<tr class="even">
<td><p>PhoneOfficeOther</p></td>
<td><p>Questo attributo esistente di Active Directory viene utilizzato dai componenti vocali in Lync Server, solo per gli oggetti contatto, allo scopo di eseguire il routing delle chiamate ai numeri di accesso del Sottoscrittore e dell'operatore automatico di messaggistica unificata. L'indirizzo di inoltro di chiamata incondizionato è memorizzato in questo attributo multivalore. Questo account viene creato per lo scopo specifico dell'operatore automatico e dell'accesso sottoscrittore. Gli attributi di questo account non devono essere modificati dagli amministratori.</p></td>
<td><p>Nuovo nel sistema operativo Windows 2000.</p></td>
</tr>
<tr class="odd">
<td><p>ProxyAddresses</p></td>
<td><p>Questo attributo multivalore di Active Directory esistente fa parte dello schema di base di Active Directory introdotto in Windows 2000. Questo attributo contiene i vari indirizzi X400, X500 e SMTP del messaggio di posta elettronica dell'utente. In Live Communications Server 2003 e versioni successive, l'URI SIP dell'utente viene aggiunto all'elenco, utilizzando il &quot;Tag SIP&quot; :.</p>
<p>Le applicazioni seguenti cercano l'URI SIP dell'utente da questo attributo:</p>
<ul>
<li><p>Client di messaggistica e collaborazione di Microsoft Office Outlook 2003</p></li>
<li><p>Microsoft Office SharePoint Server 2007</p></li>
</ul></td>
<td><p>Nuovo nel sistema operativo Windows 2000.</p></td>
</tr>
<tr class="even">
<td><p>TelephoneNumber</p></td>
<td><p>Questo attributo esistente di Active Directory contiene il numero di telefono per l'utente.</p></td>
<td><p>Nuovo nel sistema operativo Windows 2000.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

