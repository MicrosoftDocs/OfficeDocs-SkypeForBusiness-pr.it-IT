---
title: 'Lync Server 2013: Linee guida per la distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Questo argomento descrive i prerequisiti e altre linee guida da tenere in considerazione quando si prevede di distribuire Lync Server 2013 e il carico di lavoro VoIP aziendale.

<div>

## <a name="deployment-prerequisites"></a>Prerequisiti per la distribuzione

Per un'esperienza ottimale durante la distribuzione di VoIP aziendale, verificare che l'infrastruttura IT, la rete e i sistemi soddisfino i prerequisiti seguenti:

  - Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante in rete.

  - Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali con Access Edge Services, A/V Edge service, Web Conferencing Edge service e un proxy inverso.

  - Uno o più utenti sono stati creati e abilitati per Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) o ultimo Service Pack o Microsoft Exchange Server 2010 è installato. Uno di questi è necessario per l'integrazione della messaggistica UNIFICAta di Exchange con Lync Server e per la fornitura di notifiche ricche e informazioni sul log delle chiamate agli endpoint client.

  - Un numero di telefono primario univoco è stato designato, normalizzato e copiato nell'attributo **msRTCSIP-line** per ogni utente che deve essere abilitato per VoIP aziendale.
    
    <div>
    

    > [!NOTE]  
    > Lync Server supporta i numeri e. 164 e i numeri DID (non Direct Inward Dialing). I numeri non did possono essere rappresentati nel formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> o come stringa di cifre, con il requisito che l'estensione privata sia univoca in tutta l'organizzazione. Ad esempio, un numero privato di 1001 può essere rappresentato come <STRONG>+ 1425550100; EXT = 1001</STRONG>o come <STRONG>1001</STRONG>. Una volta rappresentato come <STRONG>1001</STRONG>, l'aspettativa è che questo numero privato sia univoco in tutta l'organizzazione.

    
    </div>

  - Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.

  - Office Communicator 2007 viene distribuito con successo. Per usare le nuove caratteristiche di questa versione, viene distribuito Lync 2013.

  - L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata usando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.

  - Ogni computer in cui è installato Mediation Server deve essere:
    
      - Un server membro di un dominio e preparato per servizi di dominio Active Directory. Per le procedure di preparazione dei servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.
    
      - Eseguire uno dei sistemi operativi seguenti:
        
          - <span></span>  
            Versione 64-bit del sistema operativo standard di Windows Server 2008
        
          - <span></span>  
            Versione 64-bit del sistema operativo Windows Server 2008 Enterprise

  - Se la connessione alla rete PSTN (Public Switched Telephone Network) o PBX (Private Branch Exchange) è mediante una connessione TDM (Time Division Multiplexing), è disponibile uno o più gateway PSTN per la distribuzione. Se la connessione è per mezzo di un trunk SIP, non è necessario un gateway PSTN.

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interruzioni del servizio di alimentazione, di rete o telefoniche

In caso di interruzioni, interruzioni o altre degradazioni dei servizi di Power, Network o telefono nella propria posizione, la voce, la messaggistica istantanea, la presenza e altre funzionalità di Lync Server e qualsiasi dispositivo connesso a Lync Server potrebbero non funzionare correttamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise Voice dipende dalla disponibilità del server e dalla funzionalità del client vocale e dell'hardware

Le comunicazioni vocali con Lync Server dipendono dalla disponibilità del software server e dal corretto funzionamento dei client vocali o dei dispositivi telefonici hardware che si connettono al software server.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Mezzi alternativi per accedere ai servizi di emergenza

Per i percorsi in cui si installa un client vocale, ad esempio un PC con un client Lync o un dispositivo Lync Phone Edition, è consigliabile mantenere un'opzione di backup per consentire agli utenti di chiamare i servizi di emergenza (ad esempio, 911 o 999) in caso di interruzione di corrente , degradazione della connettività di rete, interruzione del servizio telefonico o altro problema che potrebbe inibire il funzionamento dei dispositivi Lync Server, Lync o Lync Phone Edition. Queste opzioni alternative potrebbero includere un telefono connesso a una linea di rete telefonica pubblica commutata standard o a un telefono cellulare.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Chiamate di emergenza e sistemi telefonici multilinea

L'uso di un sistema telefonico multilinea (MLTS) può essere soggetto alle leggi statali o federali degli Stati Uniti o alle leggi di altri paesi/aree geografiche che richiedono alla MLTS di specificare il numero di telefono, l'estensione e/o la posizione fisica del chiamante per i servizi di emergenza applicabili quando un chiamante viene inserito in servizi di emergenza, ad esempio quando si digita un 999 911 numero di accesso di In questa versione Lync Server può essere configurato in modo da consentire la posizione fisica del chiamante a un provider di servizi di emergenza, come descritto in [pianificazione per i servizi di emergenza (E9-1-1) in Lync server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). La conformità alle leggi di MLTS è la sola responsabilità dell'acquirente dei dispositivi Lync Server, Lync client e Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

