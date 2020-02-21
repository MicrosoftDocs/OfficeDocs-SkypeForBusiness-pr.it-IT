---
title: 'Lync Server 2013: linee guida per la distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 688cf48c7f716047f0d7412c34ce84006a5a9348
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

In questo argomento vengono descritti i prerequisiti e altre linee guida da prendere in considerazione quando si pianifica la distribuzione di Lync Server 2013 e del carico di lavoro VoIP aziendale.

<div>

## <a name="deployment-prerequisites"></a>Prerequisiti per la distribuzione

Per un'esperienza ottimale quando si distribuisce VoIP aziendale, verificare che l'infrastruttura IT, la rete e i sistemi soddisfino i prerequisiti seguenti:

  - Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante nella rete.

  - Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali con il servizio Access Edge, il servizio A/V Edge, il servizio Web Conferencing Edge e un proxy inverso.

  - Uno o più utenti sono stati creati e abilitati per Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) o Service Pack più recente o Microsoft Exchange Server 2010 è installato. Uno di questi è necessario per l'integrazione della messaggistica unificata di Exchange con Lync Server e per fornire notifiche ricche e informazioni sui registri di chiamata agli endpoint client.

  - Un numero di telefono primario univoco è stato designato, normalizzato e copiato nell'attributo **msRTCSIP-line** per ogni utente che deve essere abilitato per VoIP aziendale.
    
    <div>
    

    > [!NOTE]  
    > Lync Server supporta i numeri e. 164 e i numeri DID (non Direct Inward Dialing). I numeri non did possono essere rappresentati nel formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> o come stringa di cifre, con il requisito che l'interno privato sia univoco all'interno dell'organizzazione. Un numero privato 1001 può ad esempio essere rappresentato come <STRONG>+1425550100;ext=1001</STRONG> o come <STRONG>1001</STRONG>. Quando rappresentato come <STRONG>1001</STRONG>, tale numero deve essere univoco nell'organizzazione.

    
    </div>

  - Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.

  - Come minimo, Office Communicator 2007 è stato distribuito correttamente. Per utilizzare le funzionalità nuove di questa versione, Lync 2013 è distribuito.

  - L'infrastruttura MKI (Managed Key Infrastructure) è distribuita e configurata mediante un'infrastruttura Microsoft o di un'Autorità di certificazione (CA, Certification Authority) di terze parti.

  - Ogni computer in cui si installa Mediation Server deve avere le caratteristiche seguenti:
    
      - Un server membro di un dominio e preparato per i servizi di dominio Active Directory. Per le procedure di preparazione di servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.
    
      - Eseguire uno dei sistemi operativi seguenti:
        
          - <span></span>  
            Windows Server 2008 Standard a 64 bit
        
          - <span></span>  
            Windows Server 2008 Enterprise a 64 bit

  - Se la connessione alla rete PSTN o al sistema PBX viene eseguita tramite una connessione TDM (Time Division Multiplexing), sono disponibili uno o più gateway PSTN per la distribuzione. Se la connessione avviene tramite un trunk SIP, non è necessario un gateway PSTN.

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>Interruzioni dell'alimentazione, della rete o del servizio telefonico

Se si verifica un'interruzione, un disturbo o un degrado di altro tipo dei servizi di alimentazione, rete o telefono in una posizione, la voce, la messaggistica istantanea, la presenza e altre caratteristiche di Lync Server e qualsiasi dispositivo connesso a Lync Server potrebbero non funzionare correttamente.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>VoIP aziendale dipende dalla disponibilità del server e dall'operatività hardware e dei client vocali

Le comunicazioni vocali con Lync Server dipendono dalla disponibilità del software del server e dal corretto funzionamento dei client vocali o dei dispositivi telefonici hardware che si connettono al software del server.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>Metodi alternativi di accesso ai servizi di emergenza

Per le posizioni in cui si installa un client vocale, ad esempio un PC che esegue Lync client o un dispositivo Lync Phone Edition, si consiglia di mantenere un'opzione di backup per consentire agli utenti di chiamare i servizi di emergenza (ad esempio, 911 o 999) in caso di errore di alimentazione , riduzione della connettività di rete, interruzione del servizio telefonico o altro problema che può inibire il funzionamento dei dispositivi Lync Server, Lync o Lync Phone Edition. Tali opzioni alternative possono includere un telefono connesso a una linea PSTN (Public Switched Telephone Network) standard o un telefono cellulare.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>Chiamate di emergenza e sistemi telefonici multilinea

L'utilizzo di un sistema telefonico multilinea (MTLS, Multiline Telephone System) può essere soggetto alle leggi statali e/o federali degli Stati Uniti e di altri paesi che obbligano a mostrare in chiaro ai servizi di emergenza il numero di telefono, l'interno e/o la località del chiamante quando quest'ultimo effettua una chiamata di emergenza (ad esempio, il 113). In questa versione, Lync Server può essere configurato in modo da fornire la posizione fisica del chiamante a un provider di servizi di emergenza, come descritto in [Planning for Emergency Services (E9-1-1) in Lync server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). La conformità con le leggi di MLTS è l'unica responsabilità dell'acquirente dei dispositivi Lync Server, Lync client e Lync Phone Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

