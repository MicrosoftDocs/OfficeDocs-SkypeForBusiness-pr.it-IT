---
title: Utilizzo di categorie per l'amministrazione del server Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fed28ecc7c2698f4b320729c68de9c5d56b435b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>Utilizzo di categorie per l'amministrazione del server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-01_

La distribuzione del server di chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in un set di categorie nel server. Ogni chat room appartiene a una sola categoria ed eredita alcune impostazioni da tale categoria. In questo modo viene creata una struttura utile per identificare le conversazioni in base alle esigenze aziendali e per facilitare l'amministrazione delegata e la gestione semplificata.

<div>


> [!NOTE]  
> Anche se molte delle caratteristiche di gestione delle chat room sono disponibili nei computer che eseguono la chat persistente (client Lync) per l'utente, gli amministratori della chat persistente (nel ruolo <STRONG>CsPersistentChatAdministrator</STRONG> ) devono usare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare o gestire categorie.



</div>

Gli amministratori della chat persistente usano il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare e gestire categorie e per progettare l'accesso per le chat room per gli utenti dell'organizzazione.

I responsabili delle chat room permanenti, che hanno la possibilità di gestire una o più chat room, possono usare il client Lync per avviare un'applicazione Web di gestione delle room per creare e gestire le sale (oppure i clienti possono creare soluzioni e flussi di lavoro personalizzati da richiamare). Gli amministratori della chat persistente possono anche usare il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell per creare e gestire le sale.

<div>


> [!NOTE]  
> Una chat room persistente non può avere lo stesso nome di una categoria di chat persistente.



</div>

I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, con l'eccezione della modifica della categoria. Non è possibile impedire loro di eseguire le azioni seguenti:

  - Disabilitare una chat room

  - Modificare il nome di una chat room

  - Modificare la descrizione di una chat room

  - Modificare il tipo di chat room (auditorium o normale)

  - Modificare la privacy di una chat room (aperta, chiusa o segreta)

  - Aggiungere o rimuovere membri

  - Aggiungere o rimuovere responsabili di chat room

  - Aggiungere o rimuovere componenti aggiuntivi

  - Modificare impostazioni come gli inviti (a seconda di quanto consentito dalla categoria)

<div>

## <a name="delegated-administration"></a>Amministrazione delegata

La creazione e la gestione di chat room persistenti è molto più semplice con l'uso corretto delle categorie. Un amministratore della chat persistente può definire **AllowedMembers** e **creatori** per ogni categoria e può anche definire le impostazioni e i comportamenti predefiniti della chat room che verranno applicati a tutte le chat room create nella categoria. Gli amministratori della chat persistente creano e gestiscono categorie tramite il pannello di controllo di Lync Server o i cmdlet di Windows PowerShell.

Gli utenti, le unità organizzative e i gruppi di utenti identificati come creatori della categoria sono gli unici autorizzati a creare chat room nella categoria. Dopo la creazione della categoria, essi potranno scegliere utenti, unità organizzative e gruppi di utenti dall'elenco **Membri consentiti** della categoria come responsabili di chat room e membri per la gestione e la partecipazione.

Le chat room create in una categoria sono conformi ai criteri e alle impostazioni applicate dalla categoria, ad esempio chi può essere presente nell'appartenenza della sala, che può gestire la sala, indipendentemente dal fatto che siano consentiti i caricamenti di file, l'invio di inviti e così via.

</div>

</div>

<span> </span>

</div>

</div>

</div>

