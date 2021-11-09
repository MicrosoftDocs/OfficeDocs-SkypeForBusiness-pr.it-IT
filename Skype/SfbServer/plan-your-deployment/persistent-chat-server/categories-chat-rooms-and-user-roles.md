---
title: Categorie di chat persistente, chat room e ruoli utente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Riepilogo: leggere questo argomento per informazioni su categorie, chat room e ruoli utente e amministratore per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 212e731da29bc327487e0e6512db413546d20670
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857253"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Categorie di chat persistente, chat room e ruoli utente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su categorie, chat room e ruoli utente e amministratore per il server Chat persistente in Skype for Business Server 2015.
  
È possibile controllare l'accesso alle chat room creando categorie di chat room, quindi specificando l'accesso a categorie e chat room all'interno di categorie. È inoltre possibile specificare diversi ruoli di amministratore. In questo argomento vengono descritte le seguenti informazioni: 
  
- Categorie per l'organizzazione delle chat room
    
- Chat room e ruoli utente
    
- Ruoli di amministratore

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Categorie per l'organizzazione delle chat room

Le categorie consentono di organizzare chat room e controllare quali utenti e gruppi sono autorizzati a creare o partecipare alle chat room all'interno di tali categorie. A ogni categoria sono associate proprietà che determinano le opzioni disponibili per le chat room all'interno della categoria. È possibile controllare l'accesso a una determinata categoria specificando se a un utente è consentito o negato l'accesso.
  
La logica principale per il concetto di membri consentiti e negati è la parete etica. Ad esempio è frequente negli istituti bancari e finanziari la presenza di vincoli etici che impediscono ai commercianti e agli analisti di condividere le comunicazioni quando implementano criteri e convenzioni. Per ovviare a questo problema, un amministratore può creare le categorie in modo che una categoria consenta la creazione e l'uso delle chat ai commercianti e un'altra agli analisti. Gli utenti non possono essere aggiunti come membri di una chat room se la categoria padre la impedisce.
  
> [!IMPORTANT]
> I membri consentiti e negati in una categoria non sono uguali **a** un ruolo Membro, che si applica a una chat room di Persistent Chat.> Le ricerche visualizzano tutte le chat room aperte e chiuse per le quali l'utente che esegue la ricerca si trova nell'elenco dei membri Consentiti e Negati. Le chat segrete non vengono visualizzate, a meno che l'utente che esegue la ricerca non ne sia membro. L'utente può eseguire la ricerca solo delle chat di cui è già membro o di quelle per le quali può richiedere l'appartenenza. 
  
## <a name="chat-rooms-and-user-roles"></a>Chat room e ruoli utente

Oltre ai membri consentiti e negati per le categorie, è anche possibile controllare l'accesso alle chat room specificando i ruoli utente seguenti: Creator, Manager, Member e Presenter.
  
- **Creator**: utenti che dispongono dell'autorizzazione per creare chat room. Tali utenti sono inclusi nell'elenco Creatori di determinate categorie: possono creare chat room in tali categorie, assegnare l'appartenenza in base alla categoria e affidare la gestione delle chat room a responsabili. L'utente che crea una chat room viene aggiunto automaticamente all'elenco dei responsabili della chat.
    
    > [!NOTE]
    > Agli utenti con ruolo di Creatore vengono semplicemente concessi i diritti per la creazione di chat room. La promozione automatica al ruolo di Responsabile consente al Creatore di assegnare appartenenze, specificare responsabili ed eseguire altre operazioni per i servizi chat creati. 
  
    Questo ruolo ha lo scopo di controllare chi crea le chat room nell'organizzazione, in particolare se si vuole gestire in modo centralizzato la creazione di chat room per applicare criteri e convenzioni e delegare la gestione delle chat room ad altri utenti dell'organizzazione.
    
- **Responsabile**: utenti che gestiscono le proprietà di una chat room. I responsabili delle chat room possono modificare l'elenco dei membri (aggiungere o rimuovere membri) e l'elenco dei responsabili delle chat room (aggiungere e rimuovere responsabili). I responsabili delle chat room possono inoltre aggiungere se stessi all'elenco dei membri o dei relatori (per le chat in modalità auditorium) per poter partecipare alla chat room. Possono inoltre disabilitare le chat room (gli amministratori possono eseguire la ricerca delle chat room disabilitate ed eliminarle in modo permanente). I responsabili possono modificare tutte le proprietà di una chat room, ad eccezione della categoria. Solo l'amministratore di Persistent Chat può modificare la categoria dopo la creazione della chat room.
    
    > [!IMPORTANT]
    > Se il responsabile è anche Creatore per un'altra categoria, potrà cambiare la categoria in una categoria per la quale è autorizzato a creare chat. 
  
- **Membro**: utenti membri di una chat room. Questi utenti possono visualizzare le chat room nella directory (anche se la chat room è segreta), nonché sottoscrivere la chat room (incluse le opzioni di metadati come messaggi non letti, filtri ego e filtri per parole chiave) e partecipare alla chat room (può pubblicare, a meno che la sala non sia una sala auditorium in cui solo i relatori possono pubblicare,  ottenere contenuto e cercare). Gli utenti che non sono membri della chat room possono cercare la chat room se sono nell'elenco Membri consentiti della categoria, ma devono richiedere l'accesso per partecipare a queste chat room per accedere al contenuto. Non sono disponibili richieste di accesso o approvazioni integrate nel sistema, che vengono eseguite esternamente tramite posta elettronica, telefono o altre forme di contatto.
    
- **Relatore**: utenti che possono inserire messaggi in una chat in modalità auditorium.
    
## <a name="administrator-roles"></a>Ruoli di amministratore

Di seguito sono riportati i ruoli di amministratore per il server Chat persistente:
  
- **Amministratore chat persistente**: il ruolo amministratore di Persistent Chat può gestire le chat room (modificare tutte le proprietà, tra cui appartenenza, responsabili, categorie, contrassegnare le chat room come disabilitate), nonché creare e gestire categorie di chat room che definiscono chi può creare e accedere alle chat room. Gli amministratori possono inoltre contrassegnare le chat room come disabilitate e cancellare le chat room che non sono più attive. Gli amministratori non sono soggetti alle limitazioni previste per i ruoli Creatore o Membri consentiti. Possono infatti creare qualsiasi tipo di chat room e aggiungere se stessi come membro di qualsiasi chat room. Gli amministratori possono inoltre modificare e gestire la configurazione di Persistent Chat (proprietà del pool, impostazioni globali e configurazione di conformità) e possono anche pianificare e implementare la migrazione da una distribuzione precedente di Group Chat Server a Skype for Business Server 2015 Persistent Chat Server.
    
    Gli amministratori di Chat persistente sono in grado di amministrare il server Chat persistente utilizzando i cmdlet di Windows PowerShell in remoto, ovvero da un computer diverso dal server Chat persistente. Il server Chat persistente verifica che l'amministratore di Persistent Chat sia membro del gruppo locale RTC Local Administrator nel Front End Server del server Chat persistente.
    
- **Skype for Business Server 2015 Administrator**: Amministratore globale dell'organizzazione per Skype for Business Server 2015 responsabile della distribuzione.
    
- **Operations Manager**: utente responsabile della gestione delle operazioni quotidiane.
    
- **Sviluppatori e partner di terze parti**: gli sviluppatori di terze parti estendono il sistema, in particolare offrendo una soluzione di ethical wall per le conversazioni di gruppo, strumenti e supporto per la conformità, client web/mobile e un framework per lo sviluppo dei bot.
    
## <a name="for-more-information"></a>Ulteriori informazioni

Per ulteriori informazioni sulla configurazione e sulla gestione delle chat room e dei ruoli utente, vedere i seguenti argomenti:
  
- [Creare un amministratore di Persistent Chat in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gestire le categorie nel server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gestire chat room nel server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

