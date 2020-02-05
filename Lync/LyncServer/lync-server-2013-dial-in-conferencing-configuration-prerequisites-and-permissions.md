---
title: Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-20_

I servizi di conferenza telefonica con accesso esterno sono un componente facoltativo del carico di lavoro delle conferenze di Lync Server 2013. I componenti che è necessario installare prima di poter configurare i servizi di conferenza telefonica con accesso esterno vengono distribuiti quando si usa il generatore di topologie per progettare la topologia e quindi configurare il pool Front-end o il server Standard Edition. Questo argomento descrive le operazioni che è necessario eseguire prima di configurare i servizi di conferenza telefonica con accesso esterno.

In questa sezione si presuppone che siano state lette le sezioni di pianificazione relative al carico di lavoro e ai servizi di conferenza telefonica con accesso esterno in particolare.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Prerequisiti per la configurazione delle conferenze telefoniche con accesso esterno

I servizi di conferenza telefonica con accesso esterno richiedono i seguenti componenti di Lync Server 2013:

  - Unified Communications Application Service (UCAS) (denominato *servizio applicazione*)

  - Applicazione Supervisore conferenza

  - Applicazione per l'annuncio di conferenza

  - Pagina Web delle impostazioni di conferenza telefonica con accesso esterno

  - Almeno un server di mediazione Lync Server 2013 e almeno un gateway PSTN

Questi componenti vengono distribuiti quando si usa il generatore di topologia per definire e pubblicare la topologia e quindi distribuire un pool Front-end o un server Standard Edition. Se si distribuisce VoIP aziendale, è consigliabile distribuirlo prima di configurare i servizi di conferenza telefonica con accesso esterno. Se non si sta distribuendo Enterprise Voice, è possibile distribuire un Mediation Server e un gateway PSTN (Public Switched Telephone Network) quando si distribuisce il pool Front-end o il server Standard Edition.

<div>


> [!NOTE]
> Se si esegue l'aggiornamento da Office Communications Server 2007 R2 a Lync Server 2013, distribuire i servizi di conferenza telefonica con accesso esterno in tutti i pool che si prevede di usare per ospitare le conferenze di Lync Server 2013. Per informazioni dettagliate sulla migrazione dei servizi di conferenza telefonica con accesso esterno, vedere <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">migrazione da Office Communications Server 2007 R2 a Lync Server 2013</A>.



</div>

Questa sezione presuppone che tu abbia eseguito le operazioni seguenti:

  - Se si esegue la migrazione a Lync Server 2013, gli aggiornamenti più recenti vengono applicati all'ambiente Office Communications Server 2007 R2.

  - Generatore di topologia usato per progettare e configurare la topologia. Se specifichi il carico di lavoro per le conferenze, hai selezionato l'opzione conferenza telefonica con accesso esterno. Per informazioni dettagliate sulla definizione della topologia, vedere [definizione e configurazione della topologia in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.

  - Pubblicazione della topologia e configurazione del pool Front-end o del server Standard Edition. Per informazioni dettagliate sulla pubblicazione della topologia e sull'installazione di Lync Server 2013, vedere [distribuzione di Lync server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]
    > Quando si installa la topologia pubblicata, la pagina Web delle impostazioni per i servizi di conferenza telefonica con accesso esterno viene installata nel server front-end o Standard Edition come parte di Internet Services.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Se si modifica il percorso dell'archivio di file in Generatore di topologia dopo la distribuzione di Lync Server 2013, è necessario riavviare l'operatore di conferenza e le applicazioni di annuncio per i servizi di conferenza per usare il nuovo percorso.

    
    </div>

  - Enterprise Voice distribuito. Se non si sta distribuendo VoIP aziendale, è stato collocato un Mediation Server nel server front-end Enterprise Edition o nel server Standard Edition oppure è stato distribuito un server di mediazione autonomo e si è distribuito un gateway PSTN. Per informazioni dettagliate sulla distribuzione di VoIP aziendale, vedere [distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'installazione di un Mediation Server autonomo e di un gateway PSTN, vedere [distribuzione di Mediation Server e definizione di peer in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) nella documentazione relativa alla distribuzione.

Il diagramma di flusso seguente illustra i passaggi che è necessario eseguire prima di configurare i servizi di conferenza telefonica con accesso esterno e i passaggi da eseguire per configurare i servizi di conferenza telefonica con accesso esterno.

**Distribuzione di servizi di conferenza telefonica con accesso esterno**

![Diagramma di flusso per la distribuzione delle conferenze telefoniche con accesso esterno](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagramma di flusso per la distribuzione delle conferenze telefoniche con accesso esterno")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Autorizzazioni per i servizi di conferenza telefonica con accesso esterno

Per configurare i servizi di conferenza telefonica con accesso esterno, è necessario usare gli strumenti di amministrazione seguenti:

  - Pannello di controllo di Lync Server 2013

  - Lync Server Management Shell

Questi strumenti di amministrazione consentono di configurare le impostazioni dei servizi di conferenza telefonica con accesso esterno e i piani di chiamata, i criteri e le altre impostazioni necessarie per i servizi di conferenza telefonica con accesso esterno.

La configurazione delle conferenze telefoniche con accesso esterno richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator**   questo ruolo di amministratore può creare, configurare e gestire le impostazioni e i criteri relativi alla voce.

  - **CsUserAdministrator**   questo ruolo di amministratore può abilitare e disabilitare gli utenti per Lync Server e assegnare i criteri esistenti, ad esempio i criteri di conferenza e i criteri PIN, agli utenti.

  - **CsAdministrator**   questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Distribuzione di VoIP aziendale in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

