---
title: 'Lync Server 2013: ruoli utente nel server Chat persistente'
description: 'Lync Server 2013: ruoli utente nel server Chat persistente.'
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
ms.openlocfilehash: aed64aaa9129e6667cd138bc4365acfb2a64d52c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550852"
---
# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a>Ruoli utente nel server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-03-19_

Il server Chat persistente fornisce il concetto di membri consentiti/negati, che si applica alle categorie di chat persistente e ai controlli che possono accedere alle sale di una categoria specifica.

<div>


> [!IMPORTANT]  
> I membri consentiti/negati in una categoria non sono uguali a quelli di un ruolo <STRONG>membro</STRONG> , che si applica a una chat room persistente.<BR>Le ricerche visualizzano tutte le chat room aperte e chiuse per le quali l'utente che esegue la ricerca si trova nell'elenco dei membri consentiti/non consentiti. Le chat segrete non vengono visualizzate, a meno che l'utente che esegue la ricerca non ne sia membro. L'utente può eseguire la ricerca solo delle chat di cui è già membro o di quelle per le quali può richiedere l'appartenenza.



</div>

L'aspetto principale del concetto di membri consentiti/non consentiti sono gli ethical wall. Ad esempio è frequente negli istituti bancari e finanziari la presenza di vincoli etici che impediscono ai commercianti e agli analisti di condividere le comunicazioni quando implementano criteri e convenzioni. Per ovviare a questo problema, un amministratore può creare le categorie in modo che una categoria consenta la creazione e l'uso delle chat ai commercianti e un'altra agli analisti. Questo vincolo, se progettato nel sistema, non consente di aggiungere un utente come membro della chat se la categoria principale lo impedisce.

Di seguito sono riportati i quattro server di chat persistente dei ruoli utente:

  - **Creatore:** Utenti che dispongono delle autorizzazioni per la creazione di chat room. Tali utenti sono inclusi nell'elenco Creatori di determinate categorie: possono creare chat room in tali categorie, assegnare l'appartenenza in base alla categoria e affidare la gestione delle chat room a responsabili. L'utente che crea una chat room viene aggiunto automaticamente all'elenco dei responsabili della chat.
    
    <div>
    

    > [!NOTE]  
    > Agli utenti con ruolo di Creatore vengono semplicemente concessi i diritti per la creazione di chat room. La promozione automatica al ruolo di Responsabile consente al Creatore di assegnare appartenenze, specificare responsabili ed eseguire altre operazioni per i servizi chat creati.

    
    </div>
    
    Questo ruolo ha lo scopo di controllare chi crea le chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e delegare la gestione delle chat room ad altri utenti dell'organizzazione.

  - **Responsabile:** Utenti che gestiscono le proprietà di una chat room. I responsabili delle chat room possono modificare l'elenco dei membri (aggiungere o rimuovere membri) e l'elenco dei responsabili delle chat room (aggiungere e rimuovere responsabili). I responsabili delle chat room possono inoltre aggiungere se stessi all'elenco dei membri o dei relatori (per le chat in modalità auditorium) per poter partecipare alla chat room. Possono inoltre disabilitare le chat room (gli amministratori possono eseguire la ricerca delle chat room disabilitate ed eliminarle in modo permanente). I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria. Solo l'amministratore di chat persistente può modificare la categoria dopo che è stata creata la chat room.
    
    <div>
    

    > [!IMPORTANT]  
    > Se il responsabile è anche Creatore per un'altra categoria, potrà cambiare la categoria in una categoria per la quale è autorizzato a creare chat.

    
    </div>

  - **Membro:** Utenti che sono membri di una chat room. Questi utenti possono visualizzare le chat room nella directory (anche se la chat room è segreta), nonché sottoscrivere la chat room (incluse le opzioni di metadati, ad esempio i messaggi non letti, i filtri ego e i filtri di parole chiave) e partecipare alla chat room (può postare, a meno che la sala è una sala auditorium in cui solo i relatori possono inserire, ottenere contenuto Gli utenti che non sono membri della chat room possono cercare la chat room se sono inclusi nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto. (Non vi è alcuna richiesta di accesso o approvazioni incorporate nel sistema; queste vengono eseguite esternamente tramite posta elettronica, telefono o altre forme di contatto).

  - **Relatore:** Utenti che possono inviare messaggi a una sala auditorium.

<div>


> [!NOTE]  
> Il server Chat persistente consente agli utenti di creare e gestire la chat room per un sito specifico. Tuttavia, gli utenti non possono creare o gestire chat room su altri siti all'interno della stessa topologia. Assicurarsi di specificare i creatori e i responsabili delle chat room per tutti i siti dell'organizzazione.



</div>

I ruoli seguenti sono i ruoli di amministratore per il server Chat persistente:

  - **Amministratore di chat persistente (ruolo CsPersistentChatAdministrator):** Si tratta di un nuovo ruolo di controllo di accesso Role-Based (RBAC) per l'amministrazione e la gestione del server Chat persistente. Gli utenti o i gruppi di sicurezza designati come ruolo CsPersistentChatAdministrator sono in grado di amministrare il server Chat persistente utilizzando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server Chat persistente. Il server Chat persistente verifica che l'amministratore di Persistent Chat sia membro del gruppo locale dell'amministratore locale RTC nel server front end server Chat persistente.
    
    Il ruolo CsPersistentChatAdministrator consente di gestire le chat room (modificare tutte le proprietà inclusi l'appartenenza, i responsabili, le categorie e contrassegnare le chat come disabilitate), nonché creare e gestire le categorie di chat room che stabiliscono chi può creare le chat room e chi può accedervi. Gli amministratori possono inoltre contrassegnare le chat room come disabilitate e cancellare le chat room che non sono più attive. Gli amministratori non sono soggetti alle limitazioni previste per i ruoli Creatore o Membri consentiti. Possono infatti creare qualsiasi tipo di chat room e aggiungere se stessi come membro di qualsiasi chat room. Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione di Group Chat Server precedente a Lync Server 2013 Persistent Chat Server.

  - **Amministratore di Lync:** Amministratore globale dell'organizzazione per Lync Server 2013 responsabile della distribuzione.

  - **Operations Manager:** Utente responsabile della gestione delle operazioni quotidiane.

  - **Sviluppatori e partner di terze parti:** Gli sviluppatori di terze parti estendono il sistema, in particolare fornendo una soluzione ethical wall per le conversazioni di gruppo, il supporto per la conformità e gli strumenti, i client Web/mobili e un Framework per lo sviluppo di bot.

</div>

<span> </span>

</div>

</div>

</div>

