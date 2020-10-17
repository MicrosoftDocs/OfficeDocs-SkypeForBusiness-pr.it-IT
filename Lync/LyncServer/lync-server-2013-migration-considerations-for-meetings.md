---
title: 'Lync Server 2013: considerazioni sulla migrazione per le riunioni'
description: 'Lync Server 2013: considerazioni sulla migrazione per le riunioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e238405acf7bc2a96fd2efd4cca761c1f1f258fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560942"
---
# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a>Considerazioni sulla migrazione per le riunioni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-10_

In questa sezione sono trattati gli argomenti seguenti:

  - Modifiche apportate alle riunioni in Microsoft Lync Server 2013

  - Migrazione degli utenti in base alle esigenze per le conferenze

  - Migrazione di riunioni esistenti e del contenuto delle riunioni

  - Esperienza utente durante la migrazione di Lync Server 2010

  - Esperienza utente durante la migrazione di Office Communications Server 2007 R2

  - Compatibilità di Microsoft Lync 2013 con riunioni nelle versioni precedenti del server

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a>Modifiche apportate alle riunioni in Lync Server 2013

**Funzionalità di Lync Server 2013.**     Lync Server 2013 fornisce nuove funzionalità di conferenza che diventano disponibili per gli utenti dopo lo spostamento degli account in Lync Server 2013 ed eseguono l'accesso con il client Lync 2013. Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**URL riunione.**     Come in Lync Server 2010, tutte le riunioni pianificate di recente in Lync Server 2013 dispongono di un prefisso URL di https://e le riunioni esistenti vengono migrate insieme agli account utente. Tuttavia, Lync Server 2013 non supporta la chiamata di conferenza di Office Communications Server 2007 R2 (prefisso URL conf://) o la conferenza Web (prefisso URL meet://). Per ulteriori informazioni, vedere la sezione relativa alla migrazione di riunioni da Office Communications Server 2007 R2 più avanti in questo argomento.

**Supporto client.**     A differenza di Lync Server 2010, Lync Server 2013 non supporta i client Office Communicator per le conferenze. Non è possibile utilizzare i client seguenti per partecipare a riunioni pianificate tramite il componente aggiuntivo per riunioni online per Lync 2013:

  - Office Communicator 2007 R2

  - Microsoft Office Communications Server 2007 R2 Attendant

  - Office Communicator 2007

  - Office Live Meeting 2007

Durante la migrazione, gli utenti di Office Communicator 2007 R2 devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013 fino a quando non vengono aggiornati i client. Gli utenti di Office Communicator 2007 R2 possono continuare a utilizzare il client esistente con Lync Server 2013 per le funzionalità di messaggistica istantanea e presenza, ma le funzionalità di conferenza non sono supportate.

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a>Migrazione degli utenti in base alle esigenze per le conferenze

**Organizzatori di riunioni frequenti.**     È consigliabile eseguire la migrazione degli organizzatori di riunioni frequenti all'inizio del processo, in modo che possano usufruire delle nuove funzionalità di Lync Server 2013 e Lync 2013 descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

**Utenti di Live Meeting.**     Se si esegue la migrazione da Office Communications Server 2007 R2 e si dispone di utenti che necessitano di funzionalità di Web Conferencing specifiche per Live Meeting, in particolare il supporto per riunioni di grandi dimensioni e le sale di disattivazione, sono disponibili le opzioni seguenti:

  - Consigliare agli organizzatori di utilizzare il servizio Live Meeting, se disponibile nell'organizzazione.

  - Lasciare gli organizzatori ospitati nella versione precedente di Office Communications Server, in modo che possano continuare a pianificare conferenze Web di Live Meeting basate su server.

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a>Migrazione di riunioni esistenti e del contenuto delle riunioni

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a>Migrazione di riunioni da Lync Server 2010

Quando si sposta un utente da Lync Server 2010 a Lync Server 2013, le informazioni seguenti vengono spostate con l'account dell'utente:

  - Le riunioni già pianificate dall'utente. Sono incluse le directory di conferenza e i dati di conferenza.

  - Il PIN dell'utente. Il PIN corrente dell'utente continua a funzionare fino alla scadenza o alla richiesta di un nuovo PIN da parte dell'utente stesso.

Tuttavia, le seguenti informazioni sull'account utente non vengono spostate nel nuovo server:

  - Contenuto delle riunioni, ad esempio presentazioni di PowerPoint, contenuto della lavagna e dati del sondaggio

Per spostare il contenuto condiviso nelle riunioni, utilizzare il parametro MoveMeetingContent del cmdlet Move-CsUser. Per informazioni dettagliate sull'utilizzo di questo cmdlet, vedere [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) nella documentazione relativa ai cmdlet di Lync Server 2013.

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a>Migrazione di riunioni da Office Communications Server 2007 R2

Le riunioni di Office Communications Server 2007 R2 sono chiamate conferenza (prefisso URL conf://) o conferenze Web (prefisso URL meet://). Lync Server 2013 non supporta queste conferenze precedenti di conf://e meet://e non vengono migrate insieme all'account utente. Dopo la migrazione, è necessario indicare agli utenti di aggiornare i collegamenti per eventuali riunioni online pianificate. Dopo l'installazione del client Lync 2013, è possibile eseguire questa operazione dopo l'apertura di un invito a una riunione pianificata, che consente di aggiornare l'URL della riunione e l'invio di un invito ai partecipanti.

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a>Esperienza utente durante la migrazione di Lync Server 2010

In questa sezione viene fornito un riepilogo dell'esperienza Conferencing degli utenti durante la migrazione da Lync 2010. Per ulteriori informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del server e del client, vedere [interoperabilità dei client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a>Partecipazione alle riunioni di Lync Server 2010 con un client Lync 2013

Durante la migrazione da Lync Server 2010, potrebbe esistere un periodo di coesistenza quando gli utenti partecipano alle riunioni di Lync Server 2010 con un client Lync 2013. Questi utenti possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:

  - Nelle opzioni di gestione dei **partecipanti** , che sono accessibili facendo riferimento all'icona persone nella finestra riunione, l'opzione **Nessuna riunione di messaggistica istantanea** non funziona.

  - La visualizzazione raccolta non funziona nelle conferenze video. L'utente visualizza solo l'altoparlante attivo invece di tutti gli altoparlanti. Nell'elenco delle opzioni **Seleziona un layout** , la **visualizzazione raccolta** non è disponibile

  - L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle conferenze video.

  - Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco partecipanti, le opzioni di gestione del **blocco video e del** **pin per la raccolta** non sono disponibili.

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a>Esperienza utente durante la migrazione di Office Communications Server 2007 R2

In questa sezione viene fornito un riepilogo dell'esperienza Conferencing degli utenti durante la migrazione da Office Communications Server 2007 R2, sia prima che dopo l'installazione di Lync 2013. Per ulteriori informazioni sul modo in cui i client di Lync Server 2013 possono coesistere e interagire con le versioni precedenti del server e del client, vedere [interoperabilità dei client in lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a>Dopo la migrazione dell'account utente, prima dell'installazione di Lync 2013

Dopo la migrazione di un utente al server Lync Server 2013, ma prima dell'installazione di nuovi client, gli utenti di Office Communicator 2007 R2 possono continuare a utilizzare il proprio client esistente con Lync Server 2013 per le funzionalità di presenza e messaggistica istantanea, ma le funzionalità di conferenza non sono supportate.

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a>Dopo la migrazione dell'account utente, dopo l'installazione di Lync 2013

Quando un utente migrato installa Lync 2013, viene installato anche il componente aggiuntivo per riunioni online per Lync 2013. I risultati sono i seguenti:

  - Tutte le riunioni pianificate successivamente sono basate sul nuovo formato di riunione, che utilizza un indirizzo https:// anziché l'indirizzo legacy di Live Meeting meet://.

  - In una distribuzione gestita da IT di Lync 2013, l'amministratore ha la possibilità di disinstallare il componente aggiuntivo per conferenze per Microsoft Office Outlook, che viene utilizzato per pianificare riunioni di Live Meeting Server e basati su servizi. Alcuni utenti tuttavia potrebbero dover continuare a pianificare le riunioni basate sul servizio Live Meeting. In questo caso è possibile consentire la coesistenza di entrambi i componenti aggiuntivi.

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a>Riunioni con organizzazioni federate che utilizzano client precedenti

Gli utenti di organizzazioni federative che utilizzano Microsoft Office Communicator 2007 non possono partecipare alle riunioni di Lync Server 2013 nell'organizzazione se tali riunioni sono bloccate dall'organizzatore. È necessario ripianificare queste riunioni in Lync Server 2013 in modo che i partecipanti federati che partecipano alla riunione utilizzando il nuovo URL della riunione di https://possano utilizzare Lync Web App.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

