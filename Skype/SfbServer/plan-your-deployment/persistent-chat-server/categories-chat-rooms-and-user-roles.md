---
title: Categorie di Chat persistente, chat room e ruoli utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Riepilogo: leggere questo argomento per informazioni sulle categorie, le chat room e i ruoli utente e amministratore per il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 03a7b68a9728b60ebae25081e3e974bb61b0fc5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815764"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorie di Chat persistente, chat room e ruoli utente
 
**Riepilogo:** Leggere questo argomento per informazioni su categorie, chat room e ruoli utente e amministratore per il server di chat persistente in Skype for Business Server 2015.
  
Per controllare l'accesso alle chat room, è possibile creare categorie di chat, quindi specificare l'accesso alle categorie e alle chat room all'interno delle categorie. È anche possibile specificare diversi ruoli di amministratore. Questo argomento descrive: 
  
- Categorie per l'organizzazione di chat room
    
- Chat room e ruoli utente
    
- Ruoli di amministratore

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorie per l'organizzazione di chat room

Le categorie consentono di organizzare le chat room e di controllare quali utenti e gruppi sono autorizzati a creare o partecipare alle chat room all'interno di tali categorie. Ogni categoria contiene proprietà associate che determinano le opzioni disponibili per le chat room all'interno della categoria. Puoi controllare l'accesso a una specifica categoria specificando se un utente è autorizzato o negato l'accesso.
  
La logica primaria per il concetto di membri consentiti e negati è l'ethical wall. Ad esempio, è comune negli istituti bancari e finanziari avere confini etici che impediscono agli operatori commerciali e agli analisti di condividere comunicazioni durante l'implementazione di criteri e convenzioni. Per risolvere questo requisito, un amministratore può creare categorie in modo che una categoria consenta la creazione e l'uso di sale dagli operatori commerciali, mentre un'altra categoria consente la creazione e l'uso di sale dagli analisti. Gli utenti non possono essere aggiunti come membri di una chat room se la categoria padre lo impedisce.
  
> [!IMPORTANT]
> I membri consentiti e negati in una categoria non corrispondono a quelli di un ruolo **membro** , che si applica a una chat room persistente. > ricerche Visualizza tutte le chat room aperte e chiuse per cui l'utente che esegue la ricerca si trova nell'elenco dei membri Allowed e denied. Le sale segrete non vengono visualizzate a meno che l'utente che esegue la ricerca non sia un membro della sala segreta. L'utente può cercare solo le sale di cui è già membro o quelle per cui può richiedere l'appartenenza. 
  
## <a name="chat-rooms-and-user-roles"></a>Chat room e ruoli utente

Oltre a membri consentiti e negati per le categorie, puoi anche controllare l'accesso alle chat room specificando i ruoli utente seguenti: Creator, Manager, Member e relatore.
  
- **Creatore**: utenti autorizzati a creare chat room. Questi utenti si trovano nell'elenco Creators di alcune categorie: possono creare chat room in quella categoria e possono anche assegnare l'appartenenza in base alla categoria e assegnare i Manager per gestire la chat room. L'utente che crea una chat room viene automaticamente aggiunto come Manager della sala.
    
    > [!NOTE]
    > Essere un creatore fornisce semplicemente i diritti per la creazione di chat room. È la promozione automatica di Manager che consente al creatore di perfezionare ulteriormente le appartenenze, i Manager e così via, nei servizi di chat creati. 
  
    Questo ruolo esiste per darvi la possibilità di controllare chi crea chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e quindi delegare la gestione delle chat room ad altri utenti nell'organizzazione.
    
- **Manager**: utenti che gestiscono le proprietà di una chat room. I responsabili della chat room possono modificare l'elenco dei membri (aggiungere e rimuovere membri) e modificare l'elenco dei responsabili della chat room (Aggiungi e Rimuovi Manager). I responsabili della chat room possono aggiungersi all'elenco membri o relatori (per le sale Auditorium) in modo che possano partecipare alla chat room. I responsabili delle chat room possono anche disabilitare le chat room (gli amministratori possono eseguire query per le chat room disabilitate e possono eliminarle definitivamente). I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria della chat room. Solo l'amministratore della chat persistente può modificare la categoria dopo la creazione della chat room.
    
    > [!IMPORTANT]
    > Se il responsabile è anche un creatore in un'altra categoria, può modificare la categoria in uno dei casi in cui è autorizzato a creare sale. 
  
- **Membro**: utenti membri di una chat room. Questi utenti possono vedere le chat room nella directory (anche se la chat room è segreta), nonché abbonarsi alla chat room (incluse le opzioni per i metadati, ad esempio i messaggi non letti, i filtri ego e i filtri per le parole chiave), e partecipare alla chat room (può pubblicare, a meno che la sala è una sala auditorium in cui possono essere pubblicati solo relatori, ottenere contenuti e cercare. Gli utenti che non sono membri della chat room possono cercare la chat room se si trovano nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto. (Non esiste alcuna richiesta di accesso o approvazione incorporata nel sistema; questi vengono eseguiti esternamente tramite posta elettronica, telefono o altre forme di contatto).
    
- **Relatore**: utenti che possono inserire un post in una sala auditorium.
    
## <a name="administrator-roles"></a>Ruoli di amministratore

Di seguito sono riportati i ruoli di amministratore per il server di chat persistente:
  
- **Amministratore della chat persistente**: il ruolo di amministratore della chat persistente può gestire le chat room (modifica tutte le proprietà, inclusi l'appartenenza, i Manager, le categorie, le camere contrassegnate come disabilitate), oltre a creare e gestire categorie di chat che definiscono chi può creare e accedere alle chat room. Gli amministratori possono anche contrassegnare le chat room come disattivate e pulire le chat room non più attive. Gli amministratori non sono soggetti alle restrizioni per i creatori o i membri consentiti. Gli amministratori possono creare qualsiasi tipo di chat room e aggiungersi come membri di una chat room. Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione del server di chat di gruppo precedente a Skype for Business Server 2015 Server di chat persistente.
    
    Gli amministratori della chat persistente possono amministrare il server di chat persistente usando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server di chat persistente. Il server di chat persistente controlla che l'amministratore della chat persistente sia un membro del gruppo locale dell'amministratore locale RTC nel server front end del server di chat persistente.
    
- **Amministratore di Skype for Business server 2015**: amministratore globale dell'organizzazione per Skype for business server 2015 responsabile della distribuzione.
    
- **Operations Manager**: responsabile dell'utente per la gestione delle operazioni quotidiane.
    
- **Sviluppatori e partner**di terze parti: gli sviluppatori di terze parti estendono il sistema, in particolare fornendo una soluzione per il muro etico per le conversazioni di gruppo, il supporto e gli strumenti di conformità, i client Web/mobili e un Framework per lo sviluppo di bot.
    
## <a name="for-more-information"></a>Per altre informazioni

Per altre informazioni sulla configurazione e la gestione di chat room e ruoli utente, vedere gli argomenti seguenti:
  
- [Creare un amministratore di Chat persistente](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gestire le categorie nel server Chat persistente](../../manage/persistent-chat/categories.md)
    
- [Gestire le chat room nel server Chat persistente](../../manage/persistent-chat/chat-rooms.md)
    

