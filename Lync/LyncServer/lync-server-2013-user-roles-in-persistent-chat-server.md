---
title: 'Lync Server 2013: ruoli utente nel server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 771eac8e5c8ff1c72bfb2ce64d9b6c04853b30a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Ruoli utente nel server di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-03-19_

Il server di chat persistente fornisce il concetto di membri consentiti/negati, che si applica alle categorie di chat persistenti e ai controlli che possono accedere alle camere in una specifica categoria.

<div>


> [!IMPORTANT]  
> I membri consentiti/negati in una categoria non corrispondono a quelli di un ruolo <STRONG>membro</STRONG> , che si applica a una chat room persistente.<BR>Le ricerche visualizzano tutte le chat room aperte e chiuse per cui l'utente che esegue la ricerca si trova nell'elenco dei membri allowed/denied. Le sale segrete non vengono visualizzate a meno che l'utente che esegue la ricerca non sia un membro della sala segreta. L'utente può cercare solo le sale di cui è già membro o quelle per cui può richiedere l'appartenenza.



</div>

La logica principale per il concetto di membri consentiti/negati è l'ethical wall. Ad esempio, è comune negli istituti bancari e finanziari avere confini etici che impediscono agli operatori commerciali e agli analisti di condividere comunicazioni durante l'implementazione di criteri e convenzioni. Per risolvere questo requisito, un amministratore può creare categorie in modo che una categoria consenta la creazione e l'uso di sale dagli operatori commerciali, mentre un'altra categoria consente la creazione e l'uso di sale dagli analisti. Con questo vincolo è progettato nel sistema impedisce l'aggiunta di un utente come membro della sala se la categoria padre lo impedisce.

Di seguito sono riportati i quattro ruoli utente server di chat persistente:

  - **Creatore:** Utenti che dispongono delle autorizzazioni per creare chat room. Questi utenti si trovano nell'elenco Creators di alcune categorie: possono creare chat room in quella categoria e possono anche assegnare l'appartenenza in base alla categoria e assegnare i Manager per gestire la chat room. L'utente che crea una chat room viene automaticamente aggiunto come Manager della sala.
    
    <div>
    

    > [!NOTE]  
    > Essere un creatore fornisce semplicemente i diritti per la creazione di chat room. È la promozione automatica di Manager che consente al creatore di perfezionare ulteriormente le appartenenze, i Manager e così via, nei servizi di chat creati.

    
    </div>
    
    Questo ruolo esiste per darvi la possibilità di controllare chi crea chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e quindi delegare la gestione delle chat room ad altri utenti nell'organizzazione.

  - **Manager:** Utenti che gestiscono le proprietà di una chat room. I responsabili della chat room possono modificare l'elenco dei membri (aggiungere e rimuovere membri) e modificare l'elenco dei responsabili della chat room (Aggiungi e Rimuovi Manager). I responsabili della chat room possono aggiungersi all'elenco membri o relatori (per le sale Auditorium) in modo che possano partecipare alla chat room. I responsabili delle chat room possono anche disabilitare le chat room (gli amministratori possono eseguire query per le chat room disabilitate e possono eliminarle definitivamente). I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria della chat room. Solo l'amministratore della chat persistente può modificare la categoria dopo la creazione della chat room.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il responsabile è anche un creatore in un'altra categoria, può modificare la categoria in uno dei casi in cui è autorizzato a creare sale.

    
    </div>

  - **Member:** Utenti membri di una chat room. Questi utenti possono vedere le chat room nella directory (anche se la chat room è segreta), nonché abbonarsi alla chat room (incluse le opzioni per i metadati, ad esempio i messaggi non letti, i filtri ego e i filtri per le parole chiave), e partecipare alla chat room (può pubblicare, a meno che la sala è una sala auditorium in cui possono essere pubblicati solo relatori, ottenere contenuti e cercare. Gli utenti che non sono membri della chat room possono cercare la chat room se si trovano nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto. (Non esiste alcuna richiesta di accesso o approvazione incorporata nel sistema; questi vengono eseguiti esternamente tramite posta elettronica, telefono o altre forme di contatto).

  - **Relatore:** Utenti che possono inserire un post in una sala auditorium.

<div>


> [!NOTE]  
> Il server di chat persistente consente agli utenti di creare e gestire chat room per un sito specifico. Gli utenti non possono tuttavia creare o gestire chat room in altri siti all'interno della stessa topologia. Assicurati di specificare i creatori e i responsabili della chat room per tutti i siti dell'organizzazione.



</div>

I ruoli seguenti sono ruoli di amministratore per il server di chat persistente:

  - **Amministratore della chat persistente (CsPersistentChatAdministrator):** Questo è un nuovo ruolo di controllo di accesso basato sui ruoli (RBAC) per amministrare e gestire il server di chat persistente. Gli utenti o i gruppi di sicurezza designati come CsPersistentChatAdministrator possono amministrare il server di chat persistente usando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server di chat persistente. Il server di chat persistente controlla che l'amministratore della chat persistente sia membro del gruppo locale dell'amministratore locale RTC nel server front end del server di chat persistente.
    
    Il ruolo CsPersistentChatAdministrator può gestire le chat room (modifica tutte le proprietà, inclusi l'appartenenza, i Manager, le categorie, le camere contrassegnate come disabilitate), nonché la creazione e la gestione di categorie di chat che definiscono chi può creare e accedere alle chat room. Gli amministratori possono anche contrassegnare le chat room come disattivate e pulire le chat room non più attive. Gli amministratori non sono soggetti alle restrizioni per i creatori o i membri consentiti. Gli amministratori possono creare qualsiasi tipo di chat room e aggiungersi come membri di una chat room. Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione di Group Chat Server meno recente alla chat persistente di Lync Server 2013 Server.

  - **Amministratore di Lync:** Amministratore globale dell'organizzazione per Lync Server 2013 responsabile della distribuzione.

  - **Operations Manager:** Utente responsabile della gestione delle operazioni quotidiane.

  - **Sviluppatori e partner di terze parti:** Gli sviluppatori di terze parti estendono il sistema, in particolare fornendo una soluzione di Wall Ethical per le conversazioni di gruppo, il supporto della conformità e gli strumenti, i client Web/mobili e un Framework per lo sviluppo di bot.

</div>

<span> </span>

</div>

</div>

</div>

