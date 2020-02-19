---
title: Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dfadd1f0b38244dbe7f2f742106e9a7b6a51024
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-28_

I server perimetrali possono essere configurati in modo da consentire agli utenti interni ed esterni di accedere ai contatti in organizzazioni o servizi partner. Le federazioni, ovvero questi accordi tra partner, possono rendere disponibile qualsiasi contatto dell'organizzazione alla federazione partner e viceversa:

  - Messaggistica istantanea e presenza

  - Collaborazione e servizi di conferenza, ad esempio Web Conferencing

  - Conferenze audio, video o entrambe

In alcuni casi, la comunicazione, ad esempio la messaggistica istantanea e la presenza tra un contatto Microsoft Lync Server 2013 e un protocollo XMPP (Extensible Messaging and Presence Protocol), è solo di supporto peer-to-peer-che supporta solo l'utente e il contatto a livello federato. partner. In altri casi, ad esempio Lync Server, Lync Server 2010 alla federazione Lync Server 2013, è possibile invitare più partecipanti a partecipare alla conversazione.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Federazione di Lync Server e Office Communications Server

La Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server supporta le comunicazioni peer-to-peer e multi-party. È possibile effettuare l'escalation delle conversazioni peer-to-peer a conversazioni tra più parti, consentendo l'esecuzione di riunioni ad hoc. Le riunioni, che possono essere conferenze Web o conferenze audio/video, possono essere pianificate in modo da includere contatti all'interno dell'organizzazione e contatti partner con cui si attua la federazione.

La Federazione è stata introdotta per la prima volta in Microsoft Office Live Communications Server 2005 e ha supportato un tipo di federazione, Direct Federation. Direct Federation richiede di conoscere il dominio SIP (Session Initiation Protocol) del partner federativo e il nome di dominio completo (FQDN) del server perimetrale del partner. In Live Communications Server 2005 con SP1 sono stati introdotti altri tipi di federazione, tutti i quali sono necessari record SRV DNS (Domain Name System) che devono essere pubblicati dal partner federato per individuare il server perimetrale. La terminologia relativa a tale versione è stata la seguente:

  - *Aprire Federazione avanzata*: accettare qualsiasi nome di dominio SIP e utilizzare DNS SRV per individuare il server perimetrale partner

  - *Federazione avanzata*: configurare il nome di dominio SIP del partner come partner federativo per l'organizzazione e utilizzare DNS SRV per trovare il server perimetrale del partner

  - *Federazione diretta*: configurare il nome di dominio SIP del partner e l'FQDN nel server perimetrale del partner

  - *Elenco Consenti server*: accettare qualsiasi dominio, utilizzare DNS SRV per individuare il server perimetrale di un provider di hosting o di un provider di connettività per la messaggistica istantanea pubblica

Microsoft Office Communications Server 2007 ha introdotto la denominazione aggiornata per i tipi di federazione per definire meglio ciò che ogni tipo di Federazione ha effettivamente ottenuto:

  - La federazione avanzata aperta è stata denominata *dominio individuato del partner*.

  - La federazione avanzata è stata denominata *dominio partner consentito*.

  - La federazione diretta è stata denominata *server partner consentito*.

  - L'elenco dei server consentiti è stato denominato *provider di hosting* e *provider di servizi di messaggistica istantanea pubblica*.

Microsoft Lync Server 2010 ha introdotto una definizione più restrittiva del provider di hosting in conformità con Microsoft Lync Online 2010 e Microsoft Office 365 e ha anche reso soggetto allo stesso elenco consentito definito dal tipo di Federazione del dominio del partner consentito.

L'abilitazione della Federazione tra Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server utilizza i server perimetrali e i proxy inversi per applicare le regole e i domini partner consentiti definiti. Da un punto di vista della pianificazione, la Federazione con altri Lync Server, Office Communications Server richiede quanto segue:

  - Abilitare la federazione in Generatore di topologie. Per informazioni dettagliate, vedere la sezione relativa alla distribuzione di [federazione SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Determinare i propri requisiti per l'individuazione del dominio federato:
    
      - <span></span>  
        Per la configurazione manuale della Federazione, è necessario disporre del nome di dominio completo (FQDN) del server perimetrale e del nome di dominio del partner oppure del nome di dominio online, immesso nel pannello di controllo di Lync Server, nella **Federazione e nell'accesso esterno**, ovvero nei **domini federati SIP**. Creare nuovi criteri facendo clic su **Nuovo** oppure modificare criteri esistenti facendo clic su **Modifica** in modo da consentire o bloccare i domini in base all'FQDN.
        
        <div>
        

        > [!WARNING]
        > La configurazione manuale del server perimetrale di un partner federativo è soggetta a un errore nel caso in cui il partner modifichi l'indirizzo IP del server perimetrale.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Per i <STRONG>nuovi domini federati SIP</STRONG>, è necessario fornire il <STRONG>nome di dominio (o FQDN)</STRONG> per Microsoft Lync Online, Microsoft Office 365. Per Microsoft Lync Server 2013, Lync Server 2010 e Office Communications Server è inoltre necessario fornire un <STRONG>servizio Access Edge (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        Per la Federazione partner individuata, in cui i partner possono individuare il server perimetrale, è necessario creare un record \_SRV nel DNS esterno-sipfederationtls. \_TCP.contoso.com – che punta alla porta 5061 e al record host (A) del server perimetrale
        
        <div>
        

        > [!IMPORTANT]
        > Se si supportano client Microsoft Lync Mobile su Windows Phone o Apple iPhone, iPad o altri dispositivi Apple e si utilizza il servizio di notifica push o di notifica push, è necessario pianificare _sipfederationtls. _tcp. &lt;Record SRV&gt; di dominio SIP per ogni dominio SIP di cui si dispone di client mobili di Lync. Android e Nokia Symbian Lync mobile non utilizzano la notifica push e non sono soggetti a questo requisito.

        
        </div>

  - Configurare criteri di accesso utenti esterni per il supporto dei domini federati.

  - Aprire le porte del firewall per il protocollo SIP (Session Initiation Protocol), le conferenze Web e le conferenze audio/video per supportare la federazione o i contatti abilitati. Per informazioni dettagliate, vedere: [determinare i requisiti di porte e firewall a/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Le informazioni seguenti consentono di definire il certificato, il protocollo e i requisiti DNS per la Federazione con Microsoft Lync Server 2013 e Lync Server 2010.

La pianificazione per i certificati, i requisiti del firewall e del protocollo di trasporto e i requisiti DNS è in genere un processo diretto se sono stati pianificati o distribuiti i server perimetrali di Microsoft Lync Server 2013. Poiché la Federazione è una funzionalità aggiuntiva che utilizza il server perimetrale esistente, i requisiti di pianificazione vengono in genere soddisfatti dalla pianificazione e dalla distribuzione del server perimetrale. È consigliabile utilizzare le tabelle seguenti per verificare che i requisiti vengano soddisfatti e apportare eventuali modifiche a porte/protocolli e DNS in base alle esigenze.

<div>


> [!IMPORTANT]
> Se si dispone di un pool di server perimetrali e si esegue la Federazione con i partner di Lync Server 2013 o Lync Server 2010, è possibile utilizzare il bilanciamento del carico DNS o i dispositivi di bilanciamento del carico hardware sui lati interni ed esterni dei server perimetrali. Se si sta effettuando la Federazione con Office Communications Server 2007 o Office Communications Server 2007 R2, il bilanciamento del carico hardware fornirà supporto per il failover nel caso di un server perimetrale. Office Communications Server 2007 e Office Communications Server 2007 R2 non sono compatibili con il bilanciamento del carico DNS. I server perimetrali partner stabiliranno la comunicazione con il primo server perimetrale del pool che risponde. Se il server perimetrale ha esito negativo, la comunicazione non esegue automaticamente il failover.



</div>

I requisiti dei certificati vengono in genere soddisfatti tramite la pianificazione di certificati per il server perimetrale o il piano server perimetrale scelto.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Connettività per messaggistica istantanea pubblica

La connettività per la messaggistica istantanea pubblica è una classe di federazione ed è configurata per consentire agli utenti interni ed esterni di Lync Server 2013 di aggiungere contatti da uno dei seguenti elementi:

  - Contatti di Messenger

  - Yahoo\! contatti

  - Contatti di AOL (America Online)

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio (la data esatta deve ancora essere decisa, ma non prima del giugno 2013).</P>
> <LI>
> <P>Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</P></LI></UL>



</div>

Per questa classe di federazione è necessario tenere conto delle considerazioni seguenti per la pianificazione:

  - Gli utenti di Windows Live Messenger possono avere comunicazioni audio/visive peer-to-peer con gli utenti di Lync Server 2013, oltre alla messaggistica istantanea. I server perimetrali devono soddisfare requisiti specifici per le porte e i protocolli. Per informazioni dettagliate, vedere [Determine External a/V firewall and Port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - La messaggistica istantanea Yahoo non ha requisiti univoci, oltre a quelli utilizzati in genere nella pianificazione e nella distribuzione del server perimetrale tipico che fornisce la Federazione.

  - America Online richiede che il certificato del server perimetrale assegnato al servizio Access Edge disponga di un utilizzo chiave avanzato (EKU, client Enhanced Key Usage).

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Federazione del protocollo XMPP (Extensible Messaging and Presence Protocol)

Le versioni precedenti di Lync Server e Office Communications Server fornivano un gateway XMPP (Extensible Messaging and Presence Protocol) che potrebbe essere distribuito come ruolo server separato per consentire la Federazione con le distribuzioni XMPP. In Microsoft Lync Server 2013, la funzionalità XMPP può essere distribuita come caratteristica. La funzionalità XMPP è installata in due parti: un proxy XMPP che viene eseguito nel server perimetrale e il gateway XMPP che viene eseguito nei Front End Server.

La distribuzione e la configurazione di XMPP sono descritte in [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) si prevede di supportare XMPP nell'organizzazione definendo le regole relative alle porte e ai protocolli del firewall, alla configurazione dei certificati e all'aggiunta di record DNS. Negli argomenti seguenti di questa sezione vengono riepilogate le informazioni necessarie per pianificare correttamente la Federazione XMPP per la distribuzione.

<div>


> [!IMPORTANT]
> La funzionalità XMPP di Lync Server 2013 è testata e supportata da Microsoft per la federazione di messaggistica istantanea con Google Talk. Per altri sistemi XMPP, contattare il fornitore di terze parti per verificare l'eventuale supporto della federazione con Lync Server 2013 e per indicazioni per la distribuzione o la risoluzione dei problemi.



</div>

<div>


> [!IMPORTANT]
> La Federazione XMPP non è supportata per gli utenti ospitati in Survivable Branch Appliance. Ciò vale sia per la visualizzazione delle informazioni sulla presenza che per lo scambio di messaggi di messaggistica istantanea.



</div>

</div>

<div id="sectionSection3" class="section">

Negli argomenti seguenti vengono fornite indicazioni per la definizione dei certificati, delle porte del firewall e delle voci DNS per i tipi di scenari di federazione supportati.

  - <span></span>  
    [Riepilogo del certificato-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Riepilogo delle porte-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurare criteri per controllare l'accesso degli utenti federati in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Scenari per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Determinare i requisiti di porte e firewall A/V esterni per Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Gestire la configurazione di Access Edge per l'organizzazione in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Gestire i domini federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gestire i provider federati SIP per l'organizzazione in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

