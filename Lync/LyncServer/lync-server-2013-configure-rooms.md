---
title: 'Lync Server 2013: Configurare le chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Configurare le chat room in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

La configurazione delle chat room permanenti viene comunemente gestita dagli utenti o da altri team centrali usando l'interfaccia della riga di comando di Windows PowerShell; un amministratore in genere non gestisce le chat room. Tuttavia, se è necessario creare e gestire chat room, è possibile usare l'interfaccia della riga di comando di Windows PowerShell oppure aggiungersi come membro di una chat room e usare il client Lync 2013.

Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere "gestione sala" nella [configurazione del server di chat persistente usando i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gestione dei dati nelle chat room

Il server di chat persistente consente agli utenti di collaborare pubblicando messaggi in chat room permanenti. I dati vengono mantenuti nel server e i membri della sala possono avere accesso ai dati, inclusi i dati cronologici. Tuttavia, gli utenti con ruoli diversi hanno accesso diverso ai dati persistenti, come illustrato nell'elenco seguente.

  - Gli amministratori possono eliminare il contenuto precedente, ad esempio il contenuto postato prima di una determinata data, da qualsiasi chat room per evitare che il database cresca troppo grande. In alternativa, è possibile rimuovere o sostituire i messaggi considerati inappropriati per una particolare chat room.

  - Gli utenti finali, inclusi gli autori dei messaggi, non possono eliminare il contenuto da qualsiasi chat room.

  - I responsabili delle chat room possono disabilitare le camere, ma non possono eliminare le camere. Solo gli amministratori possono eliminare una chat room dopo che è stata creata.

Quando un messaggio viene eliminato, non è possibile annullare l'azione. Tuttavia, i messaggi eliminati possono essere ripristinati se è presente un backup. Se è abilitato un server di conformità della chat persistente, i vecchi messaggi vengono mantenuti nel database di conformità.

<div>


> [!NOTE]  
> L'utilizzo dei dati delle chat room si applica a Lync Server 2013, l'applicazione API del server di chat persistente, fatta eccezione per il caso in cui è coinvolto il ruolo di amministratore. Non è possibile usare l'API del server di chat persistente per eseguire le operazioni dell'amministratore. È necessario eseguire queste operazioni in Lync Server Management Shell.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

