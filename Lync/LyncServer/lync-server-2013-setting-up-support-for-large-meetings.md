---
title: 'Lync Server 2013: impostazione del supporto per riunioni di grandi dimensioni'
description: 'Lync Server 2013: impostazione del supporto per riunioni di grandi dimensioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up support for large meetings
ms:assetid: 8e22d34b-b395-408d-9d48-8f2a3abe9513
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205074(v=OCS.15)
ms:contentKeyID: 48184763
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb04b4192c6daa9e6ea255b52566dacee1bd2dcd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554212"
---
# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configurazione del supporto per le riunioni di grandi dimensioni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-12_

Il supporto di un gran numero di riunioni fino a 1000 utenti richiede la creazione di una topologia appropriata, il rispetto di prerequisiti hardware e software e la configurazione idonea dell'ambiente.

<div>

## <a name="topology-requirements"></a>Requisiti della topologia

Una singola riunione di grandi dimensioni richiede almeno un front end server e un server back-end. Tuttavia, per garantire una disponibilità elevata, è consigliabile disporre di un pool di due front end server con server back-end con mirroring.

L'account dell'utente che ospita le riunioni di grandi dimensioni deve trovarsi in questo pool. Non è tuttavia consigliabile ospitare altri account utente in questo pool. Usarlo invece solo per le riunioni di grandi dimensioni. È preferibile creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni. Poiché l'impostazione di una riunione di grandi dimensioni è ottimizzata per le prestazioni, utilizzarla come utente normale potrebbe avere problemi come l'impossibilità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.

La gestione di un pool con esattamente due server Front End richiede alcune considerazioni speciali. Per ulteriori informazioni, vedere [topologie e componenti per Front End Server, messaggistica istantanea e presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Inoltre, se si desidera fornire facoltativamente il backup e il failover del ripristino di emergenza per il pool utilizzato per le riunioni di grandi dimensioni, è possibile associarlo a un pool di dati di installazione analogo, in un data center diverso. Per informazioni dettagliate, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configurazione del pool di riunioni di grandi dimensioni](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configurazione del pool di riunioni di grandi dimensioni")

Note aggiuntive sulla topologia:

  - È necessaria una condivisione file per l'archiviazione del contenuto delle riunioni e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione. La condivisione di file può essere dedicata al pool oppure corrispondere a quella usata da un altro pool nello stesso sito di distribuzione. Per informazioni dettagliate sulla configurazione della condivisione file, vedere [Configure file storage for Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - È necessario un server Office Web Apps per abilitare la funzionalità di presentazione di PowerPoint nelle riunioni di grandi dimensioni. Il server Office Web Apps può essere dedicato al pool di riunioni di grandi dimensioni oppure può essere lo stesso server Office Web Apps utilizzato da altri pool nel sito in cui è distribuito il pool dedicato.

  - Il bilanciamento del carico dei Front End Server richiede il bilanciamento del carico hardware per il traffico HTTP (ad esempio, il download del contenuto della riunione). Per il traffico SIP è consigliato il bilanciamento del carico DNS. Per informazioni dettagliate, vedere [requisiti per il bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Se si desidera utilizzare il Monitoring Server per il pool di riunioni di grandi dimensioni dedicato, è consigliabile utilizzare il Monitoring Server e il relativo database condiviso in tutti i pool Front End Server della distribuzione di Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

I requisiti hardware per i server in un pool di riunioni di grandi dimensioni dedicato sono uguali a quelli degli altri server Lync Server 2013. Per informazioni dettagliate sui requisiti hardware, vedere "[piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

I server in un pool di riunioni di grandi dimensioni dedicato devono soddisfare tutti i requisiti software di Lync Server 2013. Per informazioni dettagliate sui requisiti software, vedere la documentazione seguente:

  - [Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Supporto software per database in Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Inoltre, sia Lync Server 2013 sia tutti i client di Lync Server 2013 devono avere gli aggiornamenti più recenti.

</div>

<div>

## <a name="configuration-requirements"></a>Requisiti di configurazione

È consigliabile creare un nuovo criteri di conferenza specifico per le riunioni di grandi dimensioni e quindi assegnare il criterio di conferenza agli utenti ospitati in un pool dedicato a riunioni di grandi dimensioni. Configurare il criterio per conferenze con le impostazioni seguenti:

  - Impostare l'opzione **MaxMeetingSize** su **1000**. Il valore predefinito è **250**.

  - Impostare l'opzione **AllowLargeMeetings** su **True**.

  - Impostare l'opzione **EnableAppDesktopSharing** su **None**.

  - Impostare l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **False**.

  - Impostare l'opzione **AllowSharedNotes** su **False**.

  - Impostare l'opzione **AllowAnnotations** su **False**.

  - Impostare l'opzione **DisablePowerPointAnnotations** su **True**.

  - Impostare l'opzione **AllowMultiview** su **False**.

  - Impostare l'opzione **EnableMultiviewJoin** su **False**.

<div>


> [!NOTE]  
> Il supporto per le riunioni di grandi dimensioni dell'utente 1000 in Lync Server 2013 richiede che l'impostazione <STRONG>AllowLargeMeetings</STRONG> nei criteri di conferenza per l'utilità di pianificazione riunione sia impostata su true. Quando questa impostazione è impostata su true, l'esperienza di Lync sarà ottimizzata per riunioni di grandi dimensioni quando gli utenti partecipano a tale riunione. In particolare, in una riunione di grandi dimensioni, Lync non mostrerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti alla riunione completo, che è un collo di bottiglia delle prestazioni sia per il client che per Lync Server 2013. Lync, invece, visualizzerà solo le informazioni sull'utente e l'elenco dei relatori della riunione. Lync continuerà a visualizzare correttamente il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.



</div>

Ad eccezione dell'impostazione **Dimensione massima riunione**, tutti gli altri criteri di conferenza specificati qui sono necessari per disabilitare le funzionalità di conferenza non necessarie in riunioni di grandi dimensioni.

Inoltre, è necessario configurare il pool di riunioni di grandi dimensioni dedicato in modo che ogni utente di Lync Server 2013 che è ospitato nel pool e responsabile della gestione della pianificazione delle riunioni disponga delle autorizzazioni appropriate. A tale scopo, procedere come segue:

  - Impostare l'opzione **Designa come relatore** a **Nessuno**. In genere, uno o pochi altri utenti tra tutti i partecipanti a una riunione di grandi dimensioni sono relatori, pertanto i partecipanti non devono essere automaticamente ammessi a riunioni di grandi dimensioni come relatori. I relatori dovrebbero invece essere designati in modo esplicito al momento di pianificare la riunione oppure durante la riunione stessa.

  - Accertarsi che la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita** non sia selezionata. Questa impostazione consente di controllare se il componente aggiuntivo per riunioni online per Lync 2013 Pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le riunioni pianificate hanno lo stesso URL di join e le informazioni audio. In scenari di collaborazione di piccoli gruppi, l'assegnazione di un tipo di conferenza funziona bene perché ognuno dispone di una conferenza individuale assegnata e l'URL di accesso e le informazioni audio consentono di agevolare un più rapido accesso alla riunione. Tuttavia, in scenari con riunioni di grandi dimensioni, il personale di queste ultime pianifica le riunioni più grandi con un singolo set di credenziali utente, e quindi offre URL di accesso e informazioni sull'audio al richiedente il meeting. In questo caso, l'uso di un URL diverso per accedere a ogni riunione funziona bene.

  - Accettarsi che la casella di controllo **Consenti utenti anonimi per impostazione predefinita** non è selezionata a meno che non sia necessario. Questa impostazione influisce sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo per riunioni online per Lync 2013 quando non si utilizza una conferenza assegnata. L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione. Se la maggior parte delle riunioni di grandi dimensioni nell'organizzazione è interna, non selezionare questa opzione. Se per la maggior parte delle riunioni di grandi dimensioni è prevista la partecipazione di  utenti esterni, selezionare questa opzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

