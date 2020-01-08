---
title: 'Lync Server 2013: Pianificazione della resilienza vocale del sito centrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Pianificazione della resilienza vocale del sito centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-30_

Sempre più spesso, le aziende hanno più siti distribuiti in tutto il mondo. La gestione dei servizi di emergenza, l'accesso al supporto tecnico e la possibilità di svolgere attività commerciali critiche quando un sito centrale è fuori servizio sono essenziali per qualsiasi soluzione di resilienza vocale aziendale. Quando un sito centrale diventa non disponibile, è necessario che siano soddisfatte le condizioni seguenti:

  - Il failover vocale deve essere specificato.

  - Gli utenti che normalmente si iscrivono con il pool Front-end presso il sito centrale devono essere in grado di eseguire la registrazione con un pool di front end alternativo. Questa operazione può essere eseguita creando più record SRV DNS, ognuno dei quali viene risolto in un pool di Director o in un pool di front-end in ognuno dei siti centrali. È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il relativo Director e il pool Front end prima di quelli presenti in altri record SRV.

  - Le chiamate da e verso gli utenti che si trovano in altri siti devono essere reinstradate alla rete PSTN.

Questo argomento descrive la soluzione consigliata per la protezione della resilienza vocale del sito centrale.

<div>

## <a name="architecture-and-topology"></a>Architettura e topologia

La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dal registrar di Lync Server 2013 per abilitare il failover vocale. Il registrar di Lync Server è un ruolo del server che consente la registrazione e l'autenticazione del client e fornisce servizi di routing. Si trova insieme ad altri componenti in un server standard, Front End Server, Director o Survivable Branch Appliance. Un pool di registrar è costituito da servizi di registrazione eseguiti nel pool Front-end e residenti nello stesso sito. Il pool Front-end deve essere in bilanciamento del carico. È consigliabile il bilanciamento del carico DNS, ma il bilanciamento del carico hardware è accettabile. Un client Lync individua il pool Front-end tramite il meccanismo di individuazione seguente:

1.  Record SRV DNS

2.  Servizio Web AutoDiscovery (nuovo in Lync Server 2013)

3.  Opzione DHCP 120

Dopo che il client Lync si connette al pool Front-End, viene indirizzato dal bilanciamento del carico a uno dei server front-end nel pool. Il server front-end, a sua volta, reindirizza il client a un registrar preferito nel pool.

Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrar specifico, che diventa il pool di registrar principale dell'utente. In un sito specifico, centinaia o migliaia di utenti condividono in genere un singolo pool di registrar principale. Per tenere conto del consumo di risorse del sito centrale da parte di tutti gli utenti del sito della filiale che si basano sul sito centrale per presenza, conferenza o failover, è consigliabile considerare ogni utente del sito filiale come se l'utente fosse un utente registrato nel sito centrale. Attualmente non esistono limiti al numero di utenti del sito succursale, inclusi gli utenti registrati con un Survivable Branch Appliance.

Per garantire la resilienza vocale in caso di errore di un sito centrale, il pool di registrar principale deve avere un unico pool di registrar di backup designato situato in un altro sito. Il backup può essere configurato usando le impostazioni di resilienza del generatore di topologia. Supponendo che un collegamento WAN resiliente tra i due siti, gli utenti il cui pool di registrar principale non è più disponibile vengano automaticamente indirizzati al pool di registrar di backup.

I passaggi seguenti descrivono il processo di individuazione e registrazione del client:

1.  Un client individua Lync Server tramite i record SRV DNS. In Lync Server 2013 i record SRV DNS possono essere configurati in grado di restituire più di un FQDN alla query SRV DNS. Ad esempio, se Enterprise Contoso ha tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di Director in ogni sito centrale, i record SRV DNS possono puntare agli FQDN del pool di Director in ognuna delle tre posizioni. Purché il pool di Director in una delle posizioni sia disponibile, il client può connettersi al primo server Lync hop.
    
    <div>
    

    > [!NOTE]  
    > L'uso di un pool di Director è facoltativo. È invece possibile usare un pool Front-end.

    
    </div>

2.  Il pool di Director informa il client Lync sul pool di registrar principale dell'utente e sul pool di registrar di backup.

3.  Il client Lync tenta innanzitutto di connettersi al pool di registrar principale dell'utente. Se il pool di registrar principale è disponibile, il registrar accetta la registrazione. Se il pool di registrar principale non è disponibile, il client Lync tenterà di connettersi al pool di registrazione di backup. Se il pool di registrar di backup è disponibile e ha determinato che il pool di registrar principale dell'utente non è disponibile (rilevando una mancanza di heartbeat per un intervallo di failover specificato), il pool di registrar accetta la registrazione dell'utente. Dopo che il registrar di backup rileva che il registrar principale è di nuovo disponibile, il pool di registrazione backup reindirizza i client Lync di failover nel pool principale.

La figura seguente mostra la topologia consigliata per garantire la resilienza del sito centrale. I due siti sono collegati da un collegamento WAN resiliente. Se il sito centrale diventa non disponibile, gli utenti assegnati a tale pool vengono indirizzati al sito di backup per la registrazione.

**Topologia consigliata per la resilienza vocale del sito centrale**

![Topologia per la topologia Voice resliency sito centrale](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "per la resliency vocale del sito centrale")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisiti e suggerimenti

I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza vocale del sito centrale sono appropriati per la maggior parte delle organizzazioni:

  - I siti in cui risiedono i pool di registrar primari e di backup devono essere connessi da un collegamento WAN resiliente.

  - Ogni sito centrale deve contenere un pool di registrar costituito da uno o più registrar.

  - Ogni pool di registrar deve essere bilanciato tramite bilanciamento del carico DNS, bilanciamento del carico hardware o entrambi. Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Ogni utente deve essere assegnato a un pool di registrar principale usando il cmdlet **Set-CsUser** di Lync Server Management Shell o il pannello di controllo di Lync Server.

  - Il pool di registrar principale deve avere un singolo pool di registrar di backup situato in un sito centrale diverso.

  - Il pool di registrar principale deve essere configurato per il failover nel pool di registrazione di backup. Per impostazione predefinita, il registrar principale è impostato per il failover nel pool di registrar di backup dopo un intervallo di 300 secondi. Puoi modificare questo intervallo usando il generatore di topologia di Lync Server 2013.

  - Configurare una route di failover, come descritto nella sezione "[configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" nella documentazione relativa alla pianificazione. Quando si configura la route, specificare un gateway che si trova in un sito diverso dal gateway specificato nella route principale.

  - Se il sito centrale conteneva il server di gestione principale e probabilmente il sito è in calo per un periodo prolungato, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. in caso contrario, non sarà possibile modificare le impostazioni di gestione.

</div>

<div>

## <a name="dependencies"></a>Dipendenze

Lync Server dipende dai componenti di infrastruttura e software seguenti per assicurare la resilienza vocale:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Componente</strong></p></td>
<td><p><strong>Funzionale</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Risoluzione di record SRV e record per la connettività server-server e client-server</p></td>
</tr>
<tr class="odd">
<td><p>Servizi Web Exchange e Exchange (EWS)</p></td>
<td><p>Archiviazione contatti; dati del calendario</p></td>
</tr>
<tr class="even">
<td><p>Servizi Web di Exchange e messaggistica unificata</p></td>
<td><p>Registri delle chiamate, elenco della segreteria telefonica, casella vocale</p></td>
</tr>
<tr class="odd">
<td><p>Opzioni DHCP 120</p></td>
<td><p>Se DNS SRV non è disponibile, il client tenterà di usare l'opzione DHCP 120 per individuare il registrar. Affinché questo funzioni, è necessario configurare un server DHCP o abilitare il protocollo DHCP di Lync Server 2013. Per informazioni dettagliate, vedere Requisiti hardware e software per la resilienza dei siti di succursale in <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di filiale per la sezione Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Funzionalità vocali Survivable

Se sono stati implementati i requisiti e le raccomandazioni precedenti, le funzionalità vocali seguenti verranno fornite dal pool di registrazione di backup:

  - Chiamate PSTN in uscita

  - Chiamate PSTN in ingresso, se il provider del servizio di telefonia supporta la possibilità di eseguire il failover in un sito di backup

  - Chiamate aziendali tra utenti sia nello stesso sito che tra due siti diversi

  - Gestione delle chiamate di base, incluso il blocco delle chiamate, il recupero e il trasferimento

  - Messaggistica istantanea con due parti e condivisione di audio e video tra utenti nello stesso sito

  - Inoltro di chiamata, squillo simultaneo di endpoint, delegazione delle chiamate e servizi di chiamata del team, ma solo se entrambe le parti per chiamare delegazione o tutti i membri del team sono configurate nello stesso sito.

  - I telefoni e i client esistenti continuano a funzionare.

  - Registrazione dettagli chiamata (CDR)

  - Autenticazione e autorizzazione

A seconda del modo in cui sono configurate, le funzionalità vocali seguenti potrebbero non funzionare quando un sito centrale principale non è più in servizio:

  - Deposito e recupero della segreteria telefonica
    
    Se si vuole rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale non è in servizio, è necessario eseguire una delle operazioni seguenti:
    
      - Modificare i record SRV DNS in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange in un altro sito.
    
      - Configurare il dial plan di messaggistica unificata di Exchange di ogni utente per includere i server di messaggistica unificata di Exchange sia nel sito centrale che nel sito di backup, ma designa i server di messaggistica unificata di Exchange come disabilitati. Se il sito principale diventa non disponibile, l'amministratore di Exchange deve contrassegnare i server di messaggistica unificata di Exchange nel sito di backup come abilitato.
    
    Se nessuna delle soluzioni precedenti è possibile, la messaggistica unificata di Exchange non sarà disponibile in caso il sito centrale diventi non disponibile.

  - Conferenze di tutti i tipi
    
    Un utente che ha eseguito il failover in un sito di backup può partecipare a una conferenza creata o ospitata da un organizzatore il cui pool è disponibile, ma non può creare o ospitare una conferenza nel proprio pool principale, che non è più disponibile. Analogamente, altri utenti non possono partecipare a conferenze ospitate nel pool principale dell'utente interessato.

Le funzionalità vocali seguenti non funzionano quando un sito centrale principale non è più in servizio:

  - Operatore automatico conferenza

  - Presenza e routing basato su DND

  - Aggiornamento delle impostazioni di inoltro di chiamata

  - Servizio Response Group e parcheggio delle chiamate

  - Provisioning di nuovi telefoni e client

  - Ricerca Web Rubrica

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione della resilienza vocale del sito di succursale in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

