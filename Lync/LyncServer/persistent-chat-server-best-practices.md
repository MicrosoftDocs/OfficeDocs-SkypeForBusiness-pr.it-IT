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
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Procedure consigliate per il server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Man mano che crei le categorie e le chat room permanenti e progetti l'ambito e l'appartenenza, i suggerimenti seguenti possono essere utili per la pianificazione:

  - Se l'azienda non richiede un muro etico, non restringere l'ambito nell'albero delle categorie. Inserire tutti gli utenti nell'ambito di una categoria e creare tutte le chat room della categoria. In seguito, USA solo gli elenchi di appartenenza per concedere o limitare l'accesso a ogni chat room.

  - Nella maggior parte dei casi è consigliabile consentire agli utenti di creare nuove chat room in modo che le discussioni sui nuovi argomenti possano essere avviate in qualsiasi momento. Per eseguire questa operazione, è possibile rendere l'elenco dei **creatori** lo stesso dell'elenco **AllowedMembers** . Tuttavia, se vuoi consentire solo a un team di supporto centrale o agli utenti designati di creare sale, imposta l'elenco dei **creatori** come sottoinsieme appropriato.

  - Assegnare a ogni chat room un nome completo e un riepilogo della descrizione che descrivano la posizione in cui si inserisce l'organizzazione. Poiché gli utenti non possono visualizzare il nome della categoria quando usano la chat room, non puoi fare affidamento sul nome della categoria per consentire agli utenti di determinare il forum di discussione previsto per la chat room.

  - Se si hanno determinate convenzioni di denominazione o altri controlli di accesso o convalide da implementare, è consigliabile avere un flusso di lavoro personalizzato per la creazione di una sala. La configurazione della chat persistente consente di personalizzare **RoomManagementUrl** in qualcosa che si ospita. Ad esempio, quando gli utenti fanno clic su **Crea una chat room** nel client Lync, possono essere reindirizzati alla soluzione personalizzata.

  - Creare una varietà di componenti aggiuntivi che aiutano a migliorare l'esperienza delle chat room introducendo altri dati aziendali in chat room. Gli amministratori devono registrare i componenti aggiuntivi che desiderano consentire nel sistema. I responsabili delle chat room e i creatori possono scegliere l'elenco dei componenti aggiuntivi consentiti per i più rilevanti per le rispettive sale.

<div>

## <a name="see-also"></a>Vedere anche


[Gestione di categorie, chat room e componenti aggiuntivi in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

