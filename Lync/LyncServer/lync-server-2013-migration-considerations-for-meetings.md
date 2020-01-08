---
title: 'Lync Server 2013: considerazioni sulla migrazione per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67816dd8f2b9d8be3862994c735040c703bd2231
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Considerazioni sulla migrazione per le riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-10_

In questa sezione sono illustrati gli argomenti seguenti:

  - Modifiche alle riunioni in Microsoft Lync Server 2013

  - Migrazione degli utenti in base alle esigenze di conferenza

  - Migrazione di riunioni e contenuto delle riunioni esistenti

  - Esperienza utente durante la migrazione a Lync Server 2010

  - Esperienza utente durante la migrazione a Office Communications Server 2007 R2

  - Compatibilità di Microsoft Lync 2013 con le riunioni nelle versioni precedenti del server

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Modifiche alle riunioni in Lync Server 2013

**Caratteristiche di Lync Server 2013.**    Lync Server 2013 offre nuove caratteristiche di conferenza che diventano disponibili agli utenti dopo lo spostamento degli account in lync Server 2013 e l'accesso con il client Lync 2013. Le nuove caratteristiche sono descritte in [nuove caratteristiche di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL della riunione.**    Come in lync Server 2010, tutte le riunioni pianificate di recente in lync Server 2013 hanno un prefisso URL di https://e le riunioni esistenti migrano insieme agli account utente. Lync Server 2013 non supporta tuttavia la conferenza telefonica di Office Communications Server 2007 R2 (conf://URL prefix) o Web Conference (prefisso URL meet://). Per altre informazioni, vedere "migrazione delle riunioni da Office Communications Server 2007 R2" più avanti in questo argomento.

**Supporto client.**    A differenza di lync Server 2010, lync Server 2013 non supporta i client di Office Communicator per le conferenze. Non è possibile usare i client seguenti per partecipare alle riunioni pianificate tramite il componente aggiuntivo riunione online per Lync 2013:

  - Office Communicator 2007 R2

  - Assistente di Microsoft Office Communications Server 2007 R2

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante la migrazione, gli utenti di Office Communicator 2007 R2 devono usare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013 finché i client non vengono aggiornati. Tieni presente che gli utenti di Office Communicator 2007 R2 possono continuare a usare il client esistente in Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma le funzionalità di conferenza non sono supportate.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrazione degli utenti in base alle esigenze di conferenza

**Frequenti organizzatori della riunione.**    È consigliabile eseguire la migrazione delle riunioni frequenti degli organizzatori della riunione in modo che possano sfruttare le nuove funzionalità di lync Server 2013 e Lync 2013 descritte in [nuove funzionalità di conferenza in Lync Server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Utenti di Live Meeting.**    Se si esegue la migrazione da Office Communications Server 2007 R2 e si hanno gli utenti che hanno bisogno di funzionalità di conferenza Web specifiche per Live Meeting, in particolare il supporto per riunioni di grandi dimensioni e camere di break-out, sono disponibili le opzioni seguenti:

  - Consigliare agli organizzatori di usare il servizio Live Meeting, se disponibile nell'organizzazione.

  - Abbandonare gli organizzatori nella versione precedente di Office Communications Server, in modo che possano continuare a pianificare conferenze Web Live Meeting basate sul server.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrazione di riunioni e contenuto delle riunioni esistenti

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrazione di riunioni da Lync Server 2010

Quando si sposta un utente da Lync Server 2010 a Lync Server 2013, le informazioni seguenti si spostano con l'account dell'utente:

  - Riunioni già programmate dall'utente. Sono incluse le Conferencing Directories e i dati di conferenza.

  - PIN (Personal Identification Number) dell'utente. Il PIN corrente dell'utente continuerà a funzionare finché non scade o l'utente richiede un nuovo PIN.

Le informazioni dell'account utente seguenti, tuttavia, non vengono spostati nel nuovo server:

  - Contenuto della riunione, ad esempio presentazioni di PowerPoint, contenuto della lavagna e dati del sondaggio

Per trasferire il contenuto condiviso in riunioni, usa il parametro MoveMeetingContent del cmdlet Move-CsUser. Per informazioni dettagliate sull'uso di questo cmdlet, vedere [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) nella documentazione dei cmdlet di Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrazione di riunioni da Office Communications Server 2007 R2

Le riunioni di Office Communications Server 2007 R2 sono chiamate conferenza (prefisso URL conf://) o conferenze Web (prefisso URL meet://). Lync Server 2013 non supporta queste conferenze precedenti di conf://e meet://e non vengono migrate insieme all'account utente. Dopo la migrazione, è consigliabile indicare agli utenti di aggiornare i collegamenti per tutte le riunioni online che hanno programmato. Questa operazione può essere eseguita dopo l'installazione del client Lync 2013 aprendo un invito a una riunione pianificata, che aggiorna l'URL della riunione, e invia nuovamente l'invito ai partecipanti.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Esperienza utente durante la migrazione a Lync Server 2010

Questa sezione fornisce un riepilogo dell'esperienza di conferenza degli utenti quando si esegue la migrazione da Lync 2010. Per altre informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del client e del server, vedere [interoperabilità client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Partecipare a riunioni di Lync Server 2010 con un client Lync 2013

Durante la migrazione da Lync Server 2010 può esistere un periodo di coesistenza quando gli utenti partecipano a riunioni Lync Server 2010 con un client Lync 2013. Questi utenti possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:

  - Nelle opzioni di gestione dei **partecipanti** , che sono accessibili puntando l'icona persone nella finestra della riunione, l'opzione **Nessuna messaggistica istantanea** non funziona.

  - La visualizzazione raccolta non funziona nelle conferenze video. L'utente vede solo l'altoparlante attivo invece di tutti gli altoparlanti. Nell'elenco delle opzioni **Scegli un layout** la **visualizzazione raccolta** non è disponibile

  - L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle videoconferenze.

  - Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco dei partecipanti, le opzioni **di** gestione del **riflettore e del PIN delle** raccolte sono non disponibili.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Esperienza utente durante la migrazione a Office Communications Server 2007 R2

Questa sezione fornisce un riepilogo dell'esperienza di conferenza degli utenti quando si esegue la migrazione da Office Communications Server 2007 R2, sia prima che dopo l'installazione di Lync 2013. Per altre informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del client e del server, vedere [interoperabilità client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Dopo la migrazione dell'account utente, prima dell'installazione di Lync 2013

Dopo la migrazione di un utente al server Lync Server 2013, ma prima dell'installazione di nuovi client, gli utenti di Office Communicator 2007 R2 possono continuare a usare il client esistente in Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma le funzionalità di conferenza non sono supportati.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Dopo la migrazione dell'account utente, dopo l'installazione di Lync 2013

Quando un utente migrato installa Lync 2013, viene installato anche il componente aggiuntivo riunione online per Lync 2013. Gli effetti sono i seguenti:

  - Tutte le riunioni pianificate in seguito usano il nuovo formato della riunione, che usa un indirizzo https://anziché l'indirizzo di riunione Live di meet://Legacy.

  - In una distribuzione gestita da IT di Lync 2013, l'amministratore ha la possibilità di disinstallare il componente aggiuntivo per le conferenze per Microsoft Office Outlook, usato per pianificare riunioni Live Meeting Server e basate su servizi. Potrebbe tuttavia essere necessario che gli utenti continuino a pianificare le riunioni del servizio Live Meeting. In questo caso, puoi consentire a entrambi i componenti aggiuntivi di coesistere.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Riunioni con organizzazioni federate che usano client precedenti

Gli utenti delle organizzazioni federate che usano Microsoft Office Communicator 2007 non possono partecipare alle riunioni di Lync Server 2013 nell'organizzazione se tali riunioni sono bloccate dall'organizzatore. È necessario ripianificare queste riunioni in Lync Server 2013 in modo che quando i partecipanti federati partecipano alla riunione usando il nuovo URL della riunione https://, possono usare Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

