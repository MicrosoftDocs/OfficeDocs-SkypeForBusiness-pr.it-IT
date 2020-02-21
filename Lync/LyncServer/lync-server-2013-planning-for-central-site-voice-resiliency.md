---
title: 'Lync Server 2013: pianificazione della resilienza vocale del sito centrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a61a07ae14f004b406aa38ef783a1c873f2128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Pianificazione della resilienza vocale del sito centrale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-30_

Le aziende dispongono sempre più spesso di diversi siti sparsi in tutto il mondo. La gestione dei servizi di emergenza, l'accesso al supporto tecnico e la possibilità di svolgere attività aziendali critiche quando un sito centrale è fuori servizio è essenziale per qualsiasi soluzione di resilienza VoIP aziendale. Quando un sito centrale diventa non disponibile, devono essere soddisfatte le condizioni seguenti:

  - Deve essere predisposto il failover dei servizi vocali.

  - Gli utenti che normalmente si iscrivono al pool Front End nel sito centrale devono essere in grado di registrarsi con un pool Front End alternativo. A tale scopo, è possibile creare più record SRV DNS, ognuno dei quali viene risolto in un pool di server Director o in un pool Front end in ognuno dei siti centrali. È possibile modificare la priorità e i pesi dei record SRV in modo che gli utenti serviti da tale sito centrale ottengano il server Director e il pool Front end corrispondenti rispetto a quelli presenti in altri record SRV.

  - Le chiamate verso e da utenti in altri siti devono essere reindirizzate al PSTN.

Questo argomento descrive la soluzione consigliata per la protezione della resilienza dei servizi vocali del sito centrale.

<div>

## <a name="architecture-and-topology"></a>Architettura e topologia

La pianificazione della resilienza vocale in un sito centrale richiede una conoscenza di base del ruolo centrale svolto dal registrar di Lync Server 2013 per abilitare il failover vocale. Il servizio di registrazione di Lync Server è un ruolo del server che consente la registrazione e l'autenticazione dei client e fornisce servizi di routing. Esso risiede insieme ad altri componenti di un server Standard Edition, Front End Server, Director o Survivable Branch Appliance. Un pool di registrazione è costituito da servizi di registrazione in esecuzione nel pool Front end e risiede nello stesso sito. Il pool Front end deve essere bilanciamento del carico. È consigliabile usare il bilanciamento del carico DNS, ma una soluzione di bilanciamento del carico hardware è comunque accettabile. Un client Lync individua il pool Front end tramite il meccanismo di individuazione seguente:

1.  Record SRV DNS

2.  Servizio Web di individuazione automatica (nuovo in Lync Server 2013)

3.  Opzione DHCP 120

Dopo la connessione del client Lync al pool Front End, il bilanciamento del carico viene indirizzato a uno dei front end server nel pool. Il front end server, a sua sua scelta, reindirizza il client a un registrar preferito nel pool.

Ogni utente abilitato per VoIP aziendale viene assegnato a un pool di registrazione specifico, che diventa il pool di registrazione principale di tale utente. In ogni sito, un singolo pool di registrazione principale è solitamente condiviso da centinaia o migliaia di utenti. Per pianificare il consumo delle risorse del sito centrale da parte di eventuali utenti di siti di succursale che si basano sul sito centrale per i servizi di presenza, conferenza o failover, è consigliabile considerare ogni utente di sito di succursale come se fosse un utente registrato nel sito centrale. Al momento non sono presenti limiti al numero di utenti di siti di succursale, compresi gli utenti registrati con un Survivable Branch Appliance.

Per garantire la resilienza dei servizi vocali in caso di errore del sito centrale, per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup designato in un altro sito. Il backup può essere configurato utilizzando le impostazioni di resilienza del generatore di topologie. Presupponendo l'esistenza di un collegamento WAN resiliente tra due siti, gli utenti per cui non è più disponibile il pool di registrazione principale verranno reindirizzati automaticamente al pool di registrazione di backup.

I passaggi seguenti descrivono il processo di individuazione e registrazione dei client:

1.  Un client individua Lync Server tramite record DNS SRV. In Lync Server 2013, i record DNS SRV possono essere configurati in modo da restituire più FQDN alla query DNS SRV. Ad esempio, se l'azienda Contoso dispone di tre siti centrali (Nord America, Europa e Asia-Pacifico) e un pool di server Director in ogni sito centrale, i record DNS SRV possono puntare ai nomi FQDN del pool di server Director in ognuna delle tre posizioni. Fintanto che il pool di server Director in uno dei percorsi è disponibile, il client può connettersi al primo server Lync hop.
    
    <div>
    

    > [!NOTE]  
    > L'utilizzo di un pool di server Director è facoltativo. È invece possibile utilizzare un pool Front end.

    
    </div>

2.  Il pool di server Director informa il client Lync del pool di registrazione principale e del pool di registrazione di backup dell'utente.

3.  Il client Lync tenta innanzitutto di connettersi al pool di registrazione principale dell'utente. Se è disponibile, la registrazione viene accettata. Se il pool di registrazione principale non è disponibile, il client Lync tenta di connettersi al pool di registrazione di backup. Se questo è disponibile e ha verificato la non disponibilità del pool principale (rilevando la mancanza di un heartbeat per un intervallo di failover specificato), il pool di registrazione di backup accetta la registrazione dell'utente. Dopo che il registrar di backup ha rilevato che il servizio di registrazione primario è di nuovo disponibile, il pool di registrazione di backup reindirizza i client Lync di failover al pool primario.

Nella figura seguente viene illustrata la topologia consigliata per garantire la resilienza del sito centrale. I due siti sono connessi tramite un collegamento WAN resiliente. Se il sito centrale diventa non disponibile, gli utenti assegnati a tale pool vengono indirizzati al sito di backup per la registrazione.

**Topologia consigliata per la resilienza dei servizi vocali del sito centrale**

![Topologia per la resilienza vocale del sito centrale](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologia per la resilienza vocale del sito centrale")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Requisiti e raccomandazioni

I requisiti e le raccomandazioni seguenti per l'implementazione della resilienza dei servizi vocali del sito centrale sono appropriati per la maggior parte delle organizzazioni:

  - I siti in cui risiedono i pool di registrazione principale e di backup dovrebbero essere connessi tramite un collegamento WAN resiliente.

  - Ogni sito centrale deve contenere un pool di registrazione composto da una o più funzioni di registrazione.

  - Per ogni pool di registrazione è necessario utilizzare il bilanciamento del carico DNS, il bilanciamento del carico hardware o entrambi. Per informazioni dettagliate sulla pianificazione della configurazione del bilanciamento del carico, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Ogni utente deve essere assegnato a un pool di registrazione principale utilizzando il cmdlet **Set-CsUser** di Lync Server Management Shell o il pannello di controllo di Lync Server.

  - Per il pool di registrazione principale deve esistere un singolo pool di registrazione di backup posizionato in un diverso sito centrale.

  - Il pool di registrazione principale deve essere configurato per il failover sul pool di registrazione di backup. Per impostazione predefinita, il pool principale è impostato per eseguire il failover sul pool di back dopo un intervallo di 300 secondi. È possibile modificare questo intervallo utilizzando il generatore di topologie di Lync Server 2013.

  - Configurare una route di failover, come descritto nell'argomento "[configurazione di una route di failover in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" nella documentazione relativa alla pianificazione. Durante la configurazione della route specificare un gateway posizionato in un sito diverso da quello del gateway impostato nella route principale.

  - Se il sito centrale ospita il server di gestione principale ed è probabile che il sito rimanga inattivo per un lungo periodo, sarà necessario reinstallare gli strumenti di gestione nel sito di backup. In caso contrario, non sarà possibile apportare alcuna modifica alle impostazioni di gestione.

</div>

<div>

## <a name="dependencies"></a>Dipendenze

Lync Server dipende dai seguenti componenti di infrastruttura e software per garantire la resilienza vocale:


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
<td><p>Risoluzione dei record SRV e A per la connettività tra server e tra server e client</p></td>
</tr>
<tr class="odd">
<td><p>Exchange e Servizi Web Exchange</p></td>
<td><p>Archiviazione dei contatti; dati del calendario</p></td>
</tr>
<tr class="even">
<td><p>Messaggistica unificata di Exchange e Servizi Web Exchange</p></td>
<td><p>Registri chiamate, segreteria telefonica e messaggi di segreteria telefonica</p></td>
</tr>
<tr class="odd">
<td><p>Opzione DHCP 120</p></td>
<td><p>Se non sono disponibili record DNS SRV, il client tenterà di utilizzare l'opzione DHCP 120 per individuare la funzione di registrazione. Affinché ciò funzioni, è necessario configurare un server DHCP oppure è necessario abilitare il protocollo DHCP di Lync Server 2013. Per informazioni dettagliate, vedere Requisiti hardware e software per la resilienza dei siti di succursale in <a href="lync-server-2013-branch-site-resiliency-requirements.md">requisiti di resilienza dei siti di succursale per Lync Server 2013</a> sezione.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Funzionalità vocali disponibili

Se si implementano i requisiti e le raccomandazioni precedenti, il pool di registrazione di backup renderà disponibili le funzionalità vocali seguenti:

  - Chiamate PSTN in uscita

  - Chiamate PSTN in entrata, se il provider di servizi di telefonia supporta il failover su un sito di backup.

  - Chiamate Enterprise tra utenti dello stesso sito e di due siti diversi

  - Gestione di base delle chiamate inclusi la messa in attesa, il recupero e il trasferimento

  - Messaggistica istantanea tra due parti e condivisione di audio e video tra utenti nello stesso sito

  - Inoltro di chiamata, squillo simultaneo degli endpoint, delega delle chiamate e servizi di intercettazione team, ma solo se entrambe le parti della delega, oppure tutti i membri del team, sono configurati nello stesso sito

  - I telefoni ei client esistenti continuano a funzionare.

  - Registrazione dettagli chiamata (CDR)

  - Autenticazione e autorizzazione

A seconda della modalità di configurazione, le funzionalità vocali seguenti potrebbero o meno funzionare quando un sito centrale principale è fuori servizio:

  - Recapito e recupero di messaggi di segreteria telefonica
    
    Se si desidera rendere disponibile la messaggistica unificata di Exchange quando il sito centrale principale è fuori servizio, è necessario eseguire una delle operazioni seguenti:
    
      - Modificare i record DNS SRV in modo che i server di messaggistica unificata di Exchange nel sito centrale puntino ai server di messaggistica unificata di Exchange di backup in un altro sito.
    
      - Configurare il dial plan di messaggistica unificata di Exchange di ogni utente per includere i server di messaggistica unificata di Exchange sia nel sito centrale che nel sito di backup, ma designare i server di messaggistica unificata di Exchange come disabilitati. Se il sito principale diventa non disponibile, l'amministratore di Exchange deve contrassegnare i server di messaggistica unificata di Exchange nel sito di backup come abilitato.
    
    Se nessuna delle soluzioni precedenti è possibile, la messaggistica unificata di Exchange non sarà disponibile nel caso in cui il sito centrale diventerà non disponibile.

  - Conferenze di tutti i tipi
    
    Un utente reindirizzato su un sito di backup per il failover può partecipare a una conferenza creata e ospitata da un organizzatore assegnato a un pool disponibile, ma non può creare o ospitare una conferenza nel suo pool principale, che non è più disponibile. In modo analogo, altri utenti non potranno partecipare alle conferenze ospitate nel pool principale dell'utente interessato dal problema.

Le funzionalità vocali seguenti non sono disponibili quando un sito centrale principale è fuori servizio:

  - Operatore Conferenza

  - Routing basato su DNS e basato sulla presenza

  - Aggiornamento delle impostazioni di inoltro di chiamata.

  - Response Group Service e parcheggio di chiamata

  - Provisioning di nuovi telefoni e client

  - Ricerca Web nella Rubrica

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

