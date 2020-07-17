---
title: Utilizzo di categorie per l'amministrazione del server Chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73801c006f7ef5487960628d0f981809cdfd2d38
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755630"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Utilizzo di categorie per l'amministrazione del server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-01_

La distribuzione del server Chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in una serie di categorie sul server. Ogni chat room appartiene a una categoria, da cui eredita alcune impostazioni. In questo modo viene creata una struttura che consente di identificare le conversazioni in base alle esigenze aziendali e di facilitare l'amministrazione delegata e la gestione semplificata.

<div>


> [!NOTE]  
> Anche se molte delle funzionalità di gestione delle chat room sono disponibili nei computer che eseguono la chat persistente (client Lync) per l'utente, gli amministratori di chat persistente (nel ruolo <STRONG>ruolo CsPersistentChatAdministrator</STRONG> ) devono utilizzare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare o gestire le categorie.



</div>

Gli amministratori di chat persistente utilizzano i cmdlet del pannello di controllo di Lync Server o di Windows PowerShell per creare e gestire categorie e per progettare l'accesso per le chat room per gli utenti dell'organizzazione.

I responsabili delle chat room permanenti, che hanno la possibilità di gestire una o più chat room, possono utilizzare il client Lync per avviare un'applicazione Web di gestione sala per creare e gestire le sale (oppure i clienti possono creare soluzioni e flussi di lavoro personalizzati per essere richiamati). Gli amministratori di chat persistente possono anche utilizzare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare e gestire le sale.

<div>


> [!NOTE]  
> Una chat room persistente non può avere lo stesso nome di una categoria di chat persistente.



</div>

I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, ad eccezione della categoria della chat. Non è invece possibile impedire loro di eseguire le azioni seguenti:

  - Disabilitazione di una chat room

  - Modifica del nome di una chat room

  - Modifica della descrizione di una chat room

  - Modifica del tipo di chat room (Auditorium o Normale)

  - Modifica della privacy di una chat (aperta, chiusa o segreta)

  - Aggiunta o rimozione di membri

  - Aggiunta o rimozione di responsabili della chat room

  - Aggiunta o rimozione di componenti aggiuntivi

  - Modificare impostazioni come gli inviti (a seconda di quanto consentito dalla categoria)

<div>

## <a name="delegated-administration"></a>Amministrazione delegata

La creazione e la gestione di chat room permanenti è molto più facile con il corretto utilizzo delle categorie. Un amministratore di chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti per le chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori di chat persistente creano e gestiscono le categorie utilizzando i cmdlet di Lync Server Control Panel o Windows PowerShell.

Gli utenti, le unità organizzative e i gruppi di utenti identificati come creatori della categoria sono gli unici autorizzati a creare chat room nella categoria. Dopo la creazione della categoria, essi potranno scegliere utenti, unità organizzative e gruppi di utenti dall'elenco **Membri consentiti** della categoria come responsabili di chat room e membri per la gestione e la partecipazione.

Le chat room create in una categoria sono soggette ai criteri e alle impostazioni applicati dalla categoria, ad esempio i membri autorizzati, gli utenti che possono gestire la chat room, se sono consentiti caricamenti di file, se è previsto l'invio di inviti e così via.

</div>

</div>

<span> </span>

</div>

</div>

</div>

