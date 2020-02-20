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
ms.openlocfilehash: 40bceea093ff5ffc99f941b27cfc13f2b4eff589
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Prerequisiti e autorizzazioni per la configurazione delle conferenze telefoniche con accesso esterno in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Le conferenze telefoniche con accesso esterno sono un componente facoltativo del carico di lavoro Lync Server 2013 Conferencing. I componenti che è necessario installare prima di poter configurare le conferenze telefoniche con accesso esterno vengono distribuiti quando si utilizza il generatore di topologie per progettare la topologia e quindi configurare il pool Front end o il server Standard Edition. In questo argomento vengono descritte le operazioni necessarie prima di poter configurare le conferenze telefoniche con accesso esterno.

In questa sezione si presuppone che siano state lette le sezioni di pianificazione relative al carico di lavoro per le conferenze e alle conferenze telefoniche con accesso esterno in particolare.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>Prerequisiti per la configurazione delle conferenze telefoniche con accesso esterno

Per le conferenze telefoniche con accesso esterno sono necessari i componenti di Lync Server 2013 seguenti:

  - Unified Communications Application Service (unificate) (denominato *servizio applicazione*)

  - Applicazione Operatore Conferenza

  - Applicazione Annuncio conferenza

  - Pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno

  - Almeno un Mediation Server Lync Server 2013 e almeno un gateway PSTN

Questi componenti vengono distribuiti quando si utilizza il generatore di topologie per definire e pubblicare la topologia e quindi distribuire un pool Front end o un server Standard Edition. Se si sta distribuendo VoIP aziendale, è consigliabile distribuirlo prima di configurare le conferenze telefoniche con accesso esterno. Se non si sta distribuendo VoIP aziendale, è possibile distribuire un Mediation Server e un gateway PSTN (Public Switched Telephone Network) quando si distribuisce il pool Front end o il server Standard Edition.

<div>


> [!NOTE]
> Se si esegue l'aggiornamento da Office Communications Server 2007 R2 a Lync Server 2013, distribuire le conferenze telefoniche con accesso esterno in ogni pool che si intende utilizzare per ospitare le conferenze di Lync Server 2013. Per informazioni dettagliate sulla migrazione delle conferenze telefoniche con accesso esterno, vedere <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration from Office Communications Server 2007 R2 to Lync Server 2013</A>.



</div>

In questa sezione si presuppone che siano state eseguite le operazioni seguenti:

  - Applicati gli aggiornamenti più recenti all'ambiente Office Communications Server 2007 R2, se si esegue la migrazione a Lync Server 2013.

  - Utilizzato generatore di topologie per progettare e configurare la topologia. Durante la specifica del carico di lavoro per le conferenze, è stata selezionata l'opzione conferenza telefonica con accesso esterno. Per informazioni dettagliate sulla definizione della topologia, vedere [define and Configuring the topologie in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) nella documentazione relativa alla distribuzione.

  - Pubblicazione della topologia e configurazione del pool Front end o del server Standard Edition. Per informazioni dettagliate sulla pubblicazione della topologia e sull'installazione di Lync Server 2013, vedere [Deploying Lync server 2013](lync-server-2013-deploying-lync-server.md) nella documentazione relativa alla distribuzione.
    
    <div>
    

    > [!NOTE]
    > Quando si installa la topologia pubblicata, la pagina Web delle impostazioni per le conferenze telefoniche con accesso esterno è installata nel server front end server o Standard Edition come parte dei servizi Internet.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Se si modifica il percorso dell'archivio file in Generatore di topologie dopo la distribuzione di Lync Server 2013, è necessario riavviare l'operatore conferenza e le applicazioni di annuncio per le conferenze per utilizzare il nuovo percorso.

    
    </div>

  - Distribuzione di VoIP aziendale. Se non si sta distribuendo VoIP aziendale, è stato collocato un Mediation Server nel server Enterprise Edition front end o nel server Standard Edition oppure è stato distribuito un Mediation Server autonomo ed è stato distribuito un gateway PSTN. Per informazioni dettagliate sulla distribuzione di VoIP aziendale, vedere [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) nella documentazione relativa alla distribuzione. Per informazioni dettagliate sull'installazione di un Mediation Server autonomo e di un gateway PSTN, vedere [Deploying Mediation Servers and define Peers in Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) nella documentazione relativa alla distribuzione.

Nel diagramma di flusso seguente sono illustrati i passaggi che è necessario eseguire prima di poter configurare le conferenze telefoniche con accesso esterno e i passaggi da eseguire per configurare le conferenze telefoniche con accesso esterno.

**Distribuzione di servizi di conferenza telefonica con accesso esterno**

![Diagramma di flusso di distribuzione delle conferenze telefoniche con accesso esterno](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "Diagramma di flusso di distribuzione delle conferenze telefoniche con accesso esterno")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>Autorizzazioni per le conferenze telefoniche con accesso esterno

Per configurare le conferenze telefoniche con accesso esterno, è necessario utilizzare gli strumenti di amministrazione seguenti:

  - Pannello di controllo di Lync Server 2013

  - Lync Server Management Shell

È possibile utilizzare questi strumenti di amministrazione per configurare le impostazioni delle conferenze telefoniche con accesso esterno e i dial plan, i criteri e le altre impostazioni necessarie per le conferenze telefoniche con accesso esterno.

La configurazione delle conferenze telefoniche con accesso esterno richiede uno dei ruoli amministrativi seguenti, a seconda dell'attività:

  - **CsVoiceAdministrator**   questo ruolo di amministratore è in grado di creare, configurare e gestire le impostazioni e i criteri vocali.

  - **CsUserAdministrator**   questo ruolo di amministratore può abilitare e disabilitare gli utenti per Lync Server e assegnare criteri esistenti, ad esempio i criteri di conferenza e i criteri PIN, agli utenti.

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

