---
title: Procedure consigliate per il server Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61b183e442312647222f92a26effd064b2109434
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Procedure consigliate per il server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Quando si creano le categorie e le chat room permanenti e si progetta l'ambito e l'appartenenza, i suggerimenti seguenti possono essere utili per la pianificazione:

  - Se l'azienda non richiede un ethical wall, non restringere l'ambito nell'albero delle categorie. Inserire tutti gli utenti nell'ambito di una categoria e creare tutte le chat room della categoria. Successivamente, utilizzare solo gli elenchi di appartenenze per concedere o limitare l'accesso a ogni chat room.

  - Nella maggior parte dei casi, è necessario consentire agli utenti di creare nuove chat room in modo che le discussioni sui nuovi argomenti possano essere avviate in qualsiasi momento. A tale scopo, è possibile fare in modo che l'elenco dei **creatori** corrisponda a quello dell'elenco **AllowedMembers** . Tuttavia, se si desidera consentire solo a un team di supporto centrale o a utenti designati di creare sale, rendere l'elenco dei **creatori** come il sottoinsieme appropriato.

  - Fornire a ogni chat room un nome completo e un riepilogo della descrizione che descrive la posizione adatta all'organizzazione. Poiché gli utenti non possono visualizzare il nome della categoria quando usano la chat room, non è possibile fare affidamento sul nome della categoria per consentire agli utenti di determinare il forum di discussione previsto per la chat room.

  - Se si dispone di determinate convenzioni di denominazione o altri controlli di accesso o convalide da implementare, potrebbe essere necessario disporre di un flusso di lavoro personalizzato per la creazione di una sala. La configurazione di chat persistente consente di personalizzare **RoomManagementUrl** in un elemento host. Ad esempio, quando gli utenti fanno clic su **Crea una chat room** nel client Lync, possono essere reindirizzati alla soluzione personalizzata.

  - Creare una serie di componenti aggiuntivi utili per migliorare l'esperienza nelle chat room introducendo altri dati business nelle chat room. Gli amministratori devono registrare i componenti aggiuntivi che si desidera consentire nel sistema. I responsabili e i creatori della chat room possono scegliere tra l'elenco dei componenti aggiuntivi consentiti per quelli più rilevanti per le rispettive sale.

<div>

## <a name="see-also"></a>Vedere anche


[Gestione di categorie, chat room e componenti aggiuntivi in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

