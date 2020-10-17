---
title: 'Lync Server 2013: configurare le chat room'
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
ms.openlocfilehash: 4e857bfce6bfbf9736039fc37c3cf57581a9c056
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529153"
---
# <a name="configure-rooms-in-lync-server-2013"></a>Configurare le chat room in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

La configurazione delle chat room permanenti è in genere gestita dagli utenti o da altri team centrali tramite l'interfaccia della riga di comando di Windows PowerShell. un amministratore in genere non gestisce le chat room. Tuttavia, se è necessario creare e gestire le chat room, è possibile utilizzare l'interfaccia della riga di comando di Windows PowerShell oppure aggiungere se stessi come membri di una chat room e utilizzare il client Lync 2013.

Per informazioni dettagliate sulla configurazione delle chat room tramite l'interfaccia della riga di comando di Windows PowerShell, vedere la sezione "gestione sala" in [configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Gestione dei dati nelle chat room

Il server Chat persistente consente agli utenti di collaborare inviando messaggi nelle chat room permanenti. I dati restano sul server, e i membri della chat room possono accedere ai dati, compresi quelli della cronologia. Tuttavia, utenti con ruoli diversi avranno un tipo di accesso diverso ai dati sul server, come illustrato nell'elenco di seguito.

  - Gli amministratori possono eliminare dalla chat room il contenuto meno recente, ad esempio il contenuto pubblicato prima di una certa data, affinché il database non raggiunga dimensioni troppo elevate. Possono inoltre eliminare o spostare messaggi considerati inappropriati per una particolare chat room.

  - Gli utenti finali, compresi gli autori dei messaggi, non possono eliminare il contenuto da una chat room.

  - I gestori di chat room possono disattivare le chat room, ma non eliminarle. Solo gli amministratori possono eliminare una chat room dopo che è stata creata.

Dopo avere eliminato un messaggio, non è possibile annullare l'operazione. Tuttavia, se esiste un backup, è possibile ripristinare i messaggi eliminati. Se un server di conformità di Persistent Chat è abilitato, i messaggi obsoleti vengono salvati nel database di conformità.

<div>


> [!NOTE]  
> L'utilizzo di questo tipo di dati della chat room si applica all'applicazione API del server di chat persistente di Lync Server 2013, ad eccezione del caso in cui è coinvolto il ruolo di amministratore. L'API del server Chat persistente non può essere utilizzata per eseguire le operazioni dell'amministratore. È necessario eseguire queste operazioni in Lync Server Management Shell.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

