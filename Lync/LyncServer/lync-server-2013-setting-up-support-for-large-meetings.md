---
title: 'Lync Server 2013: configurazione del supporto per riunioni di grandi dimensioni'
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
ms.openlocfilehash: 0e8331c28d5bd06e6a3f7d9dab2fba7db334cd00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-support-for-large-meetings-in-lync-server-2013"></a>Configurazione del supporto per riunioni di grandi dimensioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-12_

Il supporto di riunioni di grandi dimensioni per gli utenti fino a 1000 richiede la creazione di una topologia appropriata, la riunione dei prerequisiti hardware e software e la configurazione appropriata dell'ambiente.

<div>

## <a name="topology-requirements"></a>Requisiti di topologia

Una singola riunione di grandi dimensioni richiede almeno un server front-end e un server back-end. Tuttavia, per ottenere una disponibilità elevata, è consigliabile un pool di due front end server con server back-end con mirroring.

L'utente che ospita le riunioni di grandi dimensioni deve avere il proprio account utente ospitato in questo pool. Tuttavia, non è consigliabile ospitare altri account utente in questo pool. Usalo invece solo per le riunioni di grandi dimensioni. La procedura consigliata consiste nel creare un account utente speciale in questo pool da usare solo per ospitare riunioni di grandi dimensioni. Dato che l'impostazione di grande riunione è ottimizzata per le prestazioni, l'uso di un utente normale può avere problemi come l'incapacità di promuovere una sessione P2P a una riunione quando è coinvolto un endpoint PSTN.

La gestione di un pool con esattamente due server front-end richiede alcune considerazioni particolari. Per altre informazioni, vedere [topologie e componenti per i server front-end, la messaggistica istantanea e la presenza in Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

Inoltre, se si vuole specificare facoltativamente il backup e il failover del ripristino di emergenza per il pool usato per riunioni di grandi dimensioni, è possibile associarlo a un pool di dati in un altro Data Center. Per informazioni dettagliate, vedere [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

![Configurazione di pool per riunioni di grandi dimensioni](images/JJ205074.ee00e1c0-c3b2-464d-aa89-a1e877cd034d(OCS.15).jpg "Configurazione di pool per riunioni di grandi dimensioni")

Altre note sulla topologia includono:

  - È necessaria una condivisione file per archiviare il contenuto della riunione e, se il server di archiviazione è distribuito e abilitato, per l'archiviazione dei file di archiviazione. La condivisione file può essere dedicata al pool o può essere la stessa condivisione di file usata da un altro pool nel sito in cui è distribuito il pool. Per informazioni dettagliate sulla configurazione della condivisione file, vedere [configurare l'archiviazione dei file per Lync Server 2013](lync-server-2013-configure-dfs-file-storage.md).

  - È necessario un server Office Web Apps per abilitare la funzionalità presentazione di PowerPoint in riunioni di grandi dimensioni. Il server Office Web Apps può essere dedicato al grande pool di riunioni oppure può essere lo stesso server di Office Web Apps usato da altri pool nel sito in cui è distribuito il pool dedicato.

  - Il bilanciamento del carico dei server front-end richiede il bilanciamento del carico hardware per il traffico HTTP, ad esempio il download del contenuto della riunione. Il bilanciamento del carico DNS è consigliato per il traffico SIP. Per informazioni dettagliate, vedere [requisiti di bilanciamento del carico per Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Se si vuole usare il server di monitoraggio per il pool di grandi riunioni dedicato, è consigliabile usare il server di monitoraggio e il relativo database condivisi in tutti i pool di server front-end della distribuzione di Lync Server.

</div>

<div>

## <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

I requisiti hardware per i server in un pool di grandi riunioni dedicato sono gli stessi per gli altri server di Lync Server 2013. Per informazioni dettagliate sui requisiti hardware, vedere "[piattaforme hardware server per Lync server 2013](lync-server-2013-server-hardware-platforms.md).

I server in un pool di grandi riunioni dedicato devono soddisfare tutti i requisiti software di Lync Server 2013. Per informazioni dettagliate sui requisiti software, vedere la documentazione seguente:

  - [Supporto del sistema operativo per server e strumenti in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Supporto per il software di database in Lync Server 2013](lync-server-2013-database-software-support.md)

  - [Requisiti software aggiuntivi per Lync Server 2013](lync-server-2013-additional-software-requirements.md)

Inoltre, sia Lync Server 2013 che tutti i client Lync Server 2013 devono avere gli aggiornamenti più recenti.

</div>

<div>

## <a name="configuration-requirements"></a>Requisiti di configurazione

È consigliabile creare un nuovo criterio di conferenza in modo specifico per riunioni di grandi dimensioni e quindi assegnare i criteri per i servizi di conferenza agli utenti residenti nel pool di grandi riunioni dedicato. Configurare i criteri di conferenza con le impostazioni seguenti:

  - Impostare l'opzione **MaxMeetingSize** su **1000**. (Il valore predefinito è **250**).

  - Imposta l'opzione **AllowLargeMeetings** su **true**.

  - Impostare l'opzione **EnableAppDesktopSharing** su **None**.

  - Imposta l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **false**.

  - Imposta l'opzione **AllowSharedNotes** su **false**.

  - Imposta l'opzione **AllowAnnotations** su **false**.

  - Imposta l'opzione **DisablePowerPointAnnotations** su **true**.

  - Imposta l'opzione **AllowMultiview** su **false**.

  - Imposta l'opzione **EnableMultiviewJoin** su **false**.

<div>


> [!NOTE]  
> Il supporto per le riunioni di grandi dimensioni dell'utente di 1000 in Lync Server 2013 richiede l'impostazione di <STRONG>AllowLargeMeetings</STRONG> nei criteri di conferenza per l'utilità di pianificazione della riunione per essere impostata su true. Quando questa impostazione è impostata su true, l'esperienza di Lync sarà ottimizzata per riunioni extra di grandi dimensioni quando gli utenti partecipano a tale riunione. In particolare, in una riunione di grandi dimensioni, Lync non visualizzerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti a una riunione completa, ovvero un collo di bottiglia delle prestazioni sia per il client che per Lync Server 2013. Lync visualizzerà invece solo le informazioni sull'utente e l'elenco di relatori della riunione. Lync mostrerà ancora correttamente il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.



</div>

Fatta eccezione per le **dimensioni massime della riunione** , tutte le altre impostazioni dei criteri di conferenza specificate in questo articolo sono necessarie per disabilitare le funzionalità di conferenza che non sono necessarie in riunioni di grandi dimensioni.

Inoltre, è necessario configurare il pool di grandi riunioni dedicato in modo che ogni utente di Lync Server 2013 ospitato nel pool e responsabile della gestione della pianificazione della riunione disponga delle autorizzazioni appropriate. Per eseguire questa operazione, eseguire le operazioni seguenti:

  - Impostare l'opzione **designa come relatore** su **nessuno**. In genere, uno o pochi utenti di tutti i partecipanti a una riunione di grandi dimensioni sono relatori, quindi i partecipanti non devono essere ammessi automaticamente alle riunioni di grandi dimensioni come relatori. Al contrario, i relatori devono essere designati in modo esplicito al momento della riunione o essere promossi esplicitamente durante la riunione di grandi dimensioni.

  - Verificare che la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** non sia selezionata. Questa impostazione controlla se il componente aggiuntivo riunione online per Lync 2013 Pianifica sempre le conferenze con la conferenza assegnata dell'organizzatore, in modo che le riunioni pianificate abbiano lo stesso URL di join e le informazioni audio. Negli scenari di collaborazione in piccoli gruppi, il tipo di conferenza assegnata funziona bene perché ognuno ha una propria conferenza assegnata individualmente e l'URL di join costante e le informazioni audio contribuiscono a facilitare l'Unione delle riunioni. Nello scenario della riunione di grandi dimensioni, tuttavia, il personale di supporto per le riunioni di grandi dimensioni pianifica le riunioni di grandi dimensioni con un singolo set di credenziali utente e quindi fornisce URL di join e informazioni audio ai richiedenti della riunione. In questo caso, l'uso di un URL diverso per partecipare a una riunione funziona meglio.

  - Verificare che la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** non sia selezionata, a meno che non sia obbligatoria. Questa impostazione ha effetto sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo riunione online per Lync 2013 quando non si usa una conferenza assegnata. L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione. Se la maggior parte delle riunioni di grandi dimensioni per l'organizzazione è riunioni interne, non selezionare questa opzione. Se la maggior parte delle riunioni di grandi dimensioni richiede che gli utenti esterni possano partecipare, selezionare questa opzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

