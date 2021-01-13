---
title: Categorie di chat persistente, chat room e ruoli utente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Riepilogo: leggere questo argomento per informazioni su categorie, chat room e ruoli utente e amministratore per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 50b5cd6df9cbaa8958d0f1036fe5474f2d7e47dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834566"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorie di chat persistente, chat room e ruoli utente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su categorie, chat room e ruoli utente e amministratore per il server Chat persistente in Skype for Business Server 2015.
  
È possibile controllare l'accesso alle chat room creando categorie di chat, quindi specificando l'accesso alle categorie e alle chat all'interno delle categorie. È inoltre possibile specificare vari ruoli di amministratore. In questo argomento vengono descritte le operazioni seguenti: 
  
- Categorie per l'organizzazione di chat room
    
- Chat room e ruoli utente
    
- Ruoli di amministratore

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorie per l'organizzazione di chat room

Le categorie consentono di organizzare le chat room e di controllare quali utenti e gruppi sono autorizzati a creare o partecipare alle chat room all'interno di tali categorie. Ogni categoria ha proprietà associate che determinano le opzioni disponibili per le chat room all'interno della categoria. È possibile controllare l'accesso a una determinata categoria specificando se un utente è autorizzato o negato l'accesso.
  
La logica principale per il concetto di membri consentiti e negati è Ethical walls. Ad esempio è frequente negli istituti bancari e finanziari la presenza di vincoli etici che impediscono ai commercianti e agli analisti di condividere le comunicazioni quando implementano criteri e convenzioni. Per ovviare a questo problema, un amministratore può creare le categorie in modo che una categoria consenta la creazione e l'uso delle chat ai commercianti e un'altra agli analisti. Gli utenti non possono essere aggiunti come membri di una chat room se la categoria padre lo impedisce.
  
> [!IMPORTANT]
> I membri consentiti e negati in una categoria non sono uguali a quelli di un ruolo **membro** , che si applica a una chat room persistente. > le ricerche visualizzano tutte le chat aperte e chiuse per le quali l'utente che esegue la ricerca si trova nell'elenco dei membri consentiti e negati. Le chat segrete non vengono visualizzate, a meno che l'utente che esegue la ricerca non ne sia membro. L'utente può eseguire la ricerca solo delle chat di cui è già membro o di quelle per le quali può richiedere l'appartenenza. 
  
## <a name="chat-rooms-and-user-roles"></a>Chat room e ruoli utente

Oltre ai membri consentiti e negati per le categorie, è anche possibile controllare l'accesso alle chat room specificando i ruoli utente seguenti: Creator, Manager, Member e Relator.
  
- **Creatore**: utenti che dispongono dell'autorizzazione per creare chat room. Tali utenti sono inclusi nell'elenco Creatori di determinate categorie: possono creare chat room in tali categorie, assegnare l'appartenenza in base alla categoria e affidare la gestione delle chat room a responsabili. L'utente che crea una chat room viene aggiunto automaticamente all'elenco dei responsabili della chat.
    
    > [!NOTE]
    > Agli utenti con ruolo di Creatore vengono semplicemente concessi i diritti per la creazione di chat room. La promozione automatica al ruolo di Responsabile consente al Creatore di assegnare appartenenze, specificare responsabili ed eseguire altre operazioni per i servizi chat creati. 
  
    Questo ruolo ha lo scopo di controllare chi crea le chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e delegare la gestione delle chat room ad altri utenti dell'organizzazione.
    
- **Responsabile**: utenti che gestiscono le proprietà di una chat room. I responsabili delle chat room possono modificare l'elenco dei membri (aggiungere o rimuovere membri) e l'elenco dei responsabili delle chat room (aggiungere e rimuovere responsabili). I responsabili delle chat room possono inoltre aggiungere se stessi all'elenco dei membri o dei relatori (per le chat in modalità auditorium) per poter partecipare alla chat room. Possono inoltre disabilitare le chat room (gli amministratori possono eseguire la ricerca delle chat room disabilitate ed eliminarle in modo permanente). I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria. Solo l'amministratore di chat persistente può modificare la categoria dopo che è stata creata la chat room.
    
    > [!IMPORTANT]
    > Se il responsabile è anche Creatore per un'altra categoria, potrà cambiare la categoria in una categoria per la quale è autorizzato a creare chat. 
  
- **Membro**: utenti che sono membri di una chat room. Questi utenti possono visualizzare le chat room nella directory (anche se la chat room è segreta), nonché sottoscrivere la chat room (incluse le opzioni di metadati, ad esempio i messaggi non letti, i filtri ego e i filtri di parole chiave) e partecipare alla chat room (può postare, a meno che la sala è una sala auditorium in cui solo i relatori possono inserire, ottenere contenuto Gli utenti che non sono membri della chat room possono cercare la chat room se sono inclusi nell'elenco dei membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto. (Non vi è alcuna richiesta di accesso o approvazioni incorporate nel sistema; queste vengono eseguite esternamente tramite posta elettronica, telefono o altre forme di contatto).
    
- **Relatore**: utenti che possono inserire messaggi in una chat in modalità auditorium.
    
## <a name="administrator-roles"></a>Ruoli di amministratore

Di seguito sono riportati i ruoli di amministratore per il server Chat persistente:
  
- **Amministratore di chat persistente**: il ruolo amministratore di chat persistente può gestire le chat room (modificare tutte le proprietà, incluse le appartenenze, i Manager, le categorie, le sale contrassegnate come disabilitate), nonché creare e gestire le categorie di chat room che definiscono gli utenti che possono creare e accedere alle chat room. Gli amministratori possono inoltre contrassegnare le chat room come disabilitate e cancellare le chat room che non sono più attive. Gli amministratori non sono soggetti alle limitazioni previste per i ruoli Creatore o Membri consentiti. Possono infatti creare qualsiasi tipo di chat room e aggiungere se stessi come membro di qualsiasi chat room. Gli amministratori possono anche modificare e gestire la configurazione della chat persistente (proprietà del pool, impostazioni globali e configurazione della conformità) e possono anche pianificare e implementare la migrazione da una distribuzione di Group Chat Server precedente a Skype for Business Server 2015 Persistent Chat Server.
    
    Gli amministratori di chat persistente sono in grado di amministrare il server Chat persistente utilizzando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server Chat persistente. Il server Chat persistente verifica che l'amministratore di chat persistente sia membro del gruppo locale dell'amministratore locale RTC nel server front end server Chat persistente.
    
- **Amministratore di Skype for Business server 2015**: amministratore globale dell'organizzazione per Skype for business server 2015 responsabile della distribuzione.
    
- **Operations Manager**: utente responsabile della gestione delle operazioni quotidiane.
    
- **Sviluppatori e partner di terze parti**: gli sviluppatori di terze parti estendono il sistema, in particolare offrendo una soluzione di ethical wall per le conversazioni di gruppo, strumenti e supporto per la conformità, client web/mobile e un framework per lo sviluppo dei bot.
    
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sulla configurazione e la gestione di chat room e ruoli utente, vedere i seguenti argomenti:
  
- [Creare un amministratore di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gestire le categorie nel server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gestire le chat room nel server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

