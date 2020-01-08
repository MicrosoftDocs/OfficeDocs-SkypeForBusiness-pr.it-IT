---
title: 'Lync Server 2013: Definizione e configurazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definizione e configurazione della topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-14_

Puoi definire e configurare la topologia usando generatore di topologie. Generatore di topologie non richiede di essere un membro del gruppo Administrators locale o di un gruppo di domini privilegiati, ad esempio Domain Admins. Puoi definire la topologia come utente standard. Quando si avvia il generatore di topologia al primo utilizzo e alle successive sessioni di modifica, viene richiesto il percorso in cui si vuole che il generatore di topologia carichi il documento di configurazione corrente. Le opzioni disponibili sono le seguenti:

  - Scarica topologia dalla distribuzione esistente

  - Aprire la topologia da un file locale

  - Nuova topologia

Se è già stata definita una topologia e si è stabilita l'Central Management store, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente. Generatore di topologia leggerà il database e recupererà la definizione corrente. Se si ha un Central Management store esistente, è sempre consigliabile scegliere questa opzione.

Se non è stato stabilito un Central Management store e si vuole modificare una configurazione salvata in precedenza, è consigliabile scegliere di aprire la topologia da un file locale. Il file che verrà aperto sarà il file di configurazione salvato in una sessione precedente. Puoi usare questa opzione per modificare la topologia salvata in precedenza.

<div>


> [!WARNING]  
> Se si dispone già di una topologia pubblicata, non è necessario caricare un file di configurazione locale. È consigliabile scegliere di scaricare la topologia da una distribuzione esistente.



</div>

Scegliere per creare una nuova topologia, se si vuole creare una nuova configurazione di generatore di topologia. Una struttura salvata in precedenza non viene sovrascritta a meno che non si scelga di salvarla come lo stesso file creato in una sessione di progettazione precedente.

In ognuna di queste opzioni verrà richiesto un percorso in cui archiviare il file di configurazione del generatore di topologia. La posizione del file può essere una posizione locale, una posizione condivisa in una condivisione file stabilita o un elemento multimediale rimovibile.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definire e configurare un pool Front End o un server Standard Edition in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [Modificare o configurare URL semplici in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md)

  - [Selezionare il server di gestione centrale in Lync Server 2013](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

