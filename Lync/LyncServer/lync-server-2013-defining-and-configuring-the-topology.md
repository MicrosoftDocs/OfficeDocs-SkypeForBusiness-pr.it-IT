---
title: 'Lync Server 2013: definizione e configurazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86f98c5961385bd2f99c0698af1b5f422abe4c60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504543"
---
# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a>Definizione e configurazione della topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-14_

È possibile definire e configurare la topologia tramite Generatore di topologie. In Generatore di topologie non è necessario essere membri del gruppo Administrators locale o di un gruppo di dominio con privilegi, ad esempio Domain Admins. È possibile definire la topologia come utenti standard. All'avvio di Generatore di topologie per il primo utilizzo e le sessioni di modifica successive viene richiesto di specificare la posizione in cui deve essere caricato il documento della configurazione corrente. Le scelte disponibili sono le seguenti:

  - Scarica topologia dalla distribuzione esistente

  - Apri topologia da un file locale

  - Nuova topologia

Se è già stata definita una topologia e l'archivio di gestione centrale è stato definito, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente. Generatore di topologie leggerà il database e recupererà la definizione corrente. Se si dispone di un archivio di gestione centrale esistente, è sempre necessario scegliere questa opzione.

Se non è stato stabilito un archivio di gestione centrale e si desidera modificare una configurazione salvata in precedenza, è necessario scegliere di aprire la topologia da un file locale. Il file che verrà aperto sarà il file di configurazione salvato in una sessione precedente. È possibile utilizzare questa opzione per modificare la topologia salvata in precedenza.

<div>


> [!WARNING]  
> Se è già disponibile una topologia pubblicata, è sconsigliabile caricare un file di configurazione locale, ma è preferibile scegliere di scaricare la topologia da una distribuzione esistente.



</div>

Scegliere di creare una nuova topologia, se si desidera creare una nuova configurazione del generatore di topologie. Una progettazione salvata in precedenza non viene sovrascritta a meno che non si scelga di salvarla nello stesso file creato in una sessione di progettazione precedente.

In ognuna di queste opzioni verrà richiesto un percorso in cui archiviare il file di configurazione del generatore di topologie. Il percorso per il file può essere locale, condiviso in una condivisione file specifica oppure su un supporto rimovibile.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Definire e configurare una topologia in Generatore di topologie per Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [Definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

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

