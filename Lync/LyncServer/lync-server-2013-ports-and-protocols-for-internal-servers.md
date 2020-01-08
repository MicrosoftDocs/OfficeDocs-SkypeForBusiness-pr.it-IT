---
title: 'Lync Server 2013: porte e protocolli per i server interni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 026843216e433ebea120384209ed90f38be3437b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Porte e protocolli per i server interni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-04-06_

Questa sezione riepiloga le porte e i protocolli usati dai server, i bilanciatori di carico e i client in una distribuzione di Lync Server.

<div>


> [!IMPORTANT]  
> I client di Lync e Communicator quando sono coinvolti in una comunicazione uno-a-uno, vengono spesso definiti peer-to-peer. Tecnicamente, i due client comunicano in una conversazione uno-a-uno, con l'unità di controllo multipunto di messaggistica istantanea (IMMCU) al centro. IMMCU è un componente del server front-end. L'immissione di IMMCU nel flusso di lavoro di comunicazione richiesto consente la registrazione dei dettagli delle chiamate e altre caratteristiche abilitate dal server front-end. La comunicazione è da una porta di origine dinamica nel client alla porta del server front-end TLS/TCP/5061 (presupponendo l'uso della sicurezza del livello di trasporto consigliato). In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU è attivo e disponibile.



</div>

<div>

## <a name="port-and-protocol-details"></a>Dettagli sulla porta e sul protocollo

<div>


> [!NOTE]  
> Windows Firewall deve essere in corso prima di avviare i servizi Lync Server in un server, perché in questo caso Lync Server apre le porte necessarie nel firewall.



</div>

Per informazioni dettagliate sulla configurazione del firewall per i componenti perimetrali, vedere [determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

La tabella seguente elenca le porte che devono essere aperte in ogni ruolo del server interno.

### <a name="required-server-ports-by-server-role"></a>Porte del server obbligatorie (per ruolo del server)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Ruolo del server</th>
<th>Nome servizio</th>
<th>Porta</th>
<th>Protocollo</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tutti i server</p></td>
<td><p>Browser SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Browser SQL per la copia replicata locale del database di Central Management store.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>È possibile usare facoltativamente i server standard e i server front-end per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato dai server standard e dai pool Front-end per tutte le comunicazioni SIP interne tra server (MTLS), per le comunicazioni SIP tra server e client (TLS) e per le comunicazioni SIP tra server front-end e Mediation Server (MTLS). Usato anche per le comunicazioni con il server di monitoraggio.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Usato per la comunicazione HTTPS tra lo stato attiva (il componente Lync Server che gestisce lo stato conferenza) e i singoli server.</p>
<p>Questa porta viene usata anche per la comunicazione TCP tra gli elettrodomestici Survivable Branch e i server front-end.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>135</p></td>
<td><p>DCOM e chiamata di procedura remota (RPC)</p></td>
<td><p>Usato per operazioni basate su DCOM come lo spostamento di utenti, la sincronizzazione di User Replicator e la sincronizzazione della Rubrica.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio di conferenza telefonica di messaggistica istantanea di Lync Server</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per le conferenze di messaggistica istantanea.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio di conferenza Web di Lync Server</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato per ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio compatibilità con Lync Server Web Conferencing</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Consente di ascoltare le connessioni PSOM (Persistent Shared Object Model) dal client Live Meeting e dalle versioni precedenti di Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio di conferenza audio/video di Lync Server</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per le conferenze audio/video (A/V).</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio di conferenza audio/video di Lync Server</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervallo di porte multimediali usato per i servizi di conferenza video.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio compatibilità Web di Lync Server</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components) quando non viene usato HTTPS.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio compatibilità Web di Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Usato per la comunicazione dai server front-end agli FQDN della Web farm (gli URL usati da IIS Web Components).</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio compatibilità Web di Lync Server</p></td>
<td><p>8080</p></td>
<td><p>TCP e HTTP</p></td>
<td><p>Usato dai componenti Web per l'accesso esterno.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Componente server Web</p></td>
<td><p>4443</p></td>
<td><p>HTTPS</p></td>
<td><p>HTTPS (da proxy inverso) e le comunicazioni inter-pool HTTPS front-end per l'accesso all'individuazione automatica.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Componente server Web</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Componente server Web</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Componente servizi mobili</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Porta SIP usata dai processi interni dei servizi mobili</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Componente servizi mobili</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Porta SIP usata dai processi interni dei servizi mobili</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Componente servizi mobili</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio Assistente conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per i servizi di conferenza telefonica con accesso esterno.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio Assistente conferenza di Lync Server (servizi di conferenza telefonica con accesso esterno)</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per l'operatore (servizi di conferenza telefonica con accesso esterno).</p></td>
</tr>
<tr class="even">
<td><p>Server front-end che eseguono anche un Mediation Server collocato</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Usato dal Mediation Server per le richieste in arrivo dal server front-end al Mediation Server.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end che eseguono anche un Mediation Server collocato</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end che eseguono anche un Mediation Server collocato</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo dal gateway PSTN al Mediation Server.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end che eseguono anche un Mediation Server collocato</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end che eseguono anche un Mediation Server collocato</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato per le richieste SIP in uscita dal server Mediation al gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio di condivisione applicazioni di Lync Server</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste di ascolto SIP in arrivo per la condivisione delle applicazioni.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio di condivisione applicazioni di Lync Server</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>Intervallo di porte multimediali usato per la condivisione delle applicazioni.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio di annuncio di servizi di conferenza di Lync Server</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per il servizio di annuncio di conferenza di Lync Server (ovvero per i servizi di conferenza telefonica con accesso esterno).</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio di parcheggio delle chiamate di Lync Server</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per l'applicazione Call Park.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio test audio di Lync Server</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per il servizio di test audio.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Non applicabile</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>Usato per il gateway avanzato 9-1-1 (E9-1-1) in uscita.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio Response Group di Lync Server</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo per l'applicazione Response Group.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio Response Group di Lync Server</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usato per le richieste SIP in arrivo per l'applicazione Response Group.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end</p></td>
<td><p>Servizio criteri di larghezza di banda di Lync Server</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>Usato per il controllo dell'ammissione tramite chiamata tramite il servizio criteri di larghezza di banda per il traffico a/V Edge TURN.</p></td>
</tr>
<tr class="even">
<td><p>Server front-end</p></td>
<td><p>Servizio criteri di larghezza di banda di Lync Server</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Usato per il controllo dell'ammissione tramite chiamata dal servizio criteri di larghezza di banda di Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>Server front-end in cui risiede l'Central Management store</p></td>
<td><p>Servizio agente Master Replicator di Lync Server</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>Usato per spingere i dati di configurazione dall'Central Management store ai server che usano Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Tutti i server</p></td>
<td><p>Browser SQL</p></td>
<td><p>1434</p></td>
<td><p>UDP</p></td>
<td><p>Browser SQL per la copia replicata locale dei dati di Central Management store nell'istanza di SQL Server locale</p></td>
</tr>
<tr class="odd">
<td><p>Tutti i server interni</p></td>
<td><p>Vari</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervallo di porte multimediali usato per i servizi di audioconferenza in tutti i server interni. Usato da tutti i server che interrompono l'audio: Front End Server (per il servizio di conferenza telefonica di Lync Server, servizio di annuncio di Lync Server e servizi di conferenza audio/video di Lync Server) e Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p>Server di Office Web Apps</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>Usato da Lync Server 2013 per connettersi al server di Office Web Apps.</p></td>
</tr>
<tr class="odd">
<td><p>Consiglio</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>Facoltativamente usato per le route statiche a servizi attendibili, ad esempio i server di controllo delle chiamate remote.</p></td>
</tr>
<tr class="even">
<td><p>Consiglio</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p>
<p>TCP</p></td>
<td><p>Comunicazioni tra server tra front-end e Director. Inoltre, la pubblicazione del certificato client (per i server front-end) o la convalida se il certificato client è già stato pubblicato.</p></td>
</tr>
<tr class="odd">
<td><p>Consiglio</p></td>
<td><p>Servizio compatibilità Web di Lync Server</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>Usato per la comunicazione iniziale da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components). In funzionamento normale si passa al traffico HTTPS usando la porta 443 e il protocollo TCP.</p></td>
</tr>
<tr class="even">
<td><p>Consiglio</p></td>
<td><p>Servizio compatibilità Web di Lync Server</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
<td><p>Usato per la comunicazione da Directors agli FQDN della Web farm (gli URL usati da IIS Web Components).</p></td>
</tr>
<tr class="odd">
<td><p>Consiglio</p></td>
<td><p>Servizio front-end di Lync Server</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le comunicazioni interne tra i server e per le connessioni client.</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>Usato dal Mediation Server per le richieste in arrivo dal server front-end.</p></td>
</tr>
<tr class="odd">
<td><p>Mediation Server</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato per le richieste SIP in arrivo dal gateway PSTN.</p></td>
</tr>
<tr class="even">
<td><p>Mediation Server</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>Usato per le richieste SIP in arrivo dal gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>Mediation Server</p></td>
<td><p>Servizio di mediazione Lync Server</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usato per le richieste SIP provenienti dai server front-end.</p></td>
</tr>
<tr class="even">
<td><p>Server front end di chat persistente</p></td>
<td><p>SIP chat persistente</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Server front end di chat persistente</p></td>
<td><p>Chat persistente Windows Communication Foundation (WCF)</p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) e TCP (MTLS)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Server front end di chat persistente</p></td>
<td><p>Servizio di trasferimento file Chat persistente</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Alcuni scenari di controllo delle chiamate remote richiedono una connessione TCP tra il server front-end o il Director e il PBX. Anche se Lync Server non usa più la porta TCP 5060, durante la distribuzione del controllo delle chiamate remote si crea una configurazione del server attendibile, che associa il nome di dominio completo del server RCC line alla porta TCP che il server front end o il direttore utilizzerà per la connessione al sistema PBX. Per informazioni dettagliate, vedere il cmdlet <STRONG>CsTrustedApplicationComputer</STRONG> nella documentazione di Lync Server Management Shell.



</div>

Per i pool che usano solo il bilanciamento del carico hardware (non il bilanciamento del carico DNS), la tabella seguente mostra le porte che devono aprire i dispositivi di bilanciamento del carico hardware.

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>Porte di bilanciamento del carico hardware se si usa solo il bilanciamento del carico hardware

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Bilanciamento del carico</th>
<th>Porta</th>
<th>Protocollo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS)</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>135</p></td>
<td><p>DCOM e chiamata di procedura remota (RPC)</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>8080</p></td>
<td><p>TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (da proxy inverso)</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico di Mediation Server</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end (se il pool esegue anche Mediation Server)</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>444</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (da proxy inverso)</p></td>
</tr>
</tbody>
</table>


I pool di front end e i pool di direttori che usano il bilanciamento del carico DNS devono essere distribuiti anche da un dispositivo di bilanciamento del carico hardware. La tabella seguente mostra le porte che devono essere aperte in questi dispositivi di bilanciamento del carico hardware.

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>Porte di bilanciamento del carico hardware se si usa il bilanciamento del carico DNS

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Bilanciamento del carico</th>
<th>Porta</th>
<th>Protocollo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>8080</p></td>
<td><p>TCP-client e recupero di dispositivi del certificato radice dal server front-end-client e dispositivi autenticati da NTLM</p></td>
</tr>
<tr class="even">
<td><p>Bilanciamento del carico del server front-end</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (da proxy inverso)</p></td>
</tr>
<tr class="odd">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>443</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Direttore di bilanciamento del carico</p></td>
<td><p>4443</p></td>
<td><p>HTTPS (da proxy inverso)</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>Porte client richieste

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Porta</th>
<th>Protocollo</th>
<th>Note</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Client</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Usato da Lync Server per trovare il nome di dominio completo del registrar, ovvero se DNS SRV non riesce e le impostazioni manuali non sono configurate.</p></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS)</p></td>
<td><p>Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS)</p></td>
<td><p>Usato per l'accesso degli utenti esterni alle sessioni di conferenza Web.</p></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN)</p></td>
<td><p>Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (TCP)</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN)</p></td>
<td><p>Usato per l'accesso degli utenti esterni alle sessioni A/V e agli elementi multimediali (UDP)</p></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS)</p></td>
<td><p>Usato per il traffico SIP da client a server per l'accesso degli utenti esterni.</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>Usato per il trasferimento di file tra client Lync e client precedenti (client di Microsoft Office Communications Server 2007 R2, Microsoft Office Communications Server 2007 e Live Communications Server 2005).</p></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervallo di porte audio (minimo 20 porte necessarie)</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>Intervallo di porte video (è necessario un minimo di 20 porte).</p></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Trasferimento di file peer-to-peer (per il trasferimento di file di conferenza, i client usano PSOM).</p></td>
</tr>
<tr class="odd">
<td><p>Client</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>Condivisione applicazioni.</p></td>
</tr>
<tr class="even">
<td><p>Telefono per area comune Aastra 6721ip</p>
<p>Telefono da tavolo Aastra 6725ip</p>
<p>Telefono IP HP 4110 (telefono area comune)</p>
<p>Telefono IP HP 4120 (telefono da tavolo)</p>
<p>Telefono per area comune IP di Polycom CX500</p>
<p>Telefono da tavolo IP Polycom CX600</p>
<p>Telefono da tavolo IP Polycom CX700</p>
<p>Telefono per conferenze IP di Polycom CX3000</p></td>
<td><p>67/68</p></td>
<td><p>DHCP</p></td>
<td><p>Usato dai dispositivi elencati per trovare il certificato di Lync Server, il nome di dominio completo e il nome di dominio completo del registrar.</p></td>
</tr>
</tbody>
</table>


**\*** Per configurare porte specifiche per questi tipi di elementi multimediali, usare il cmdlet CsConferencingConfiguration (ClientMediaPortRangeEnabled, ClientMediaPort e ClientMediaPortRange Parameters).

<div>


> [!NOTE]  
> I programmi set per i client Lync creano automaticamente le eccezioni del firewall di sistema operativo necessarie nel computer client.



</div>

<div>


> [!NOTE]  
> Le porte usate per l'accesso degli utenti esterni sono necessarie per qualsiasi scenario in cui il client deve attraversare il firewall dell'organizzazione, ad esempio le comunicazioni esterne o le riunioni ospitate da altre organizzazioni.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

