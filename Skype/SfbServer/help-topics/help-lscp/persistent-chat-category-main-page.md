---
title: Pagina principale della categoria Persistent Chat
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: È possibile utilizzare la sezione Categoria della pagina Persistent Chat per configurare le categorie. Una categoria di chat persistente è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso per il controllo degli utenti e dei gruppi di utenti che possono creare chat room o prendervi parte. Le categorie possono essere usate per applicare gli ethical wall tra le varie suddivisioni all'interno delle organizzazioni.
ms.openlocfilehash: 18456a5f0b58939acfe994180765fffd6fc3a0f1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807292"
---
# <a name="persistent-chat-category-main-page"></a>Pagina principale della categoria di Chat persistente
 
È possibile utilizzare la **sezione Categoria** della pagina **Persistent Chat** per configurare le categorie. Una categoria di chat persistente è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso per il controllo degli utenti e dei gruppi di utenti che possono creare chat room o prendervi parte. Le categorie possono essere usate per applicare gli ethical wall tra le varie suddivisioni all'interno delle organizzazioni.
  
Le categorie di chat room possono contenere chat room, ma non altre categorie. Ogni categoria descrive il contenuto con metadati, ad esempio _Nome_ e _Descrizione._ Inoltre, la categoria dispone di proprietà che possono essere impostate per controllare il comportamento delle  chat room ad essa appartenenti, ad esempio se le chat room consentono inviti o caricamenti _file_ o contengono cronologia _chat._
  
Per creare una nuova categoria, vedere [Gestire le categorie nel server Chat persistente in Skype for Business Server 2015.](../../manage/persistent-chat/categories.md) Gli amministratori di Persistent Chat possono creare categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.
  
## <a name="tasks-that-you-can-perform"></a>Attività eseguibili

Nella pagina **Categoria** è possibile eseguire le attività seguenti:
  
- Creare o modificare una nuova categoria
    
- Spostare una chat room da una categoria a un'altra
    
- Eliminare una chat room o una categoria
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>Per configurare le categorie per le chat room di Persistent Chat

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione. .
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server Chat persistente utilizzato dal client per identificare il pool a cui appartiene la categoria. Una categoria può appartenere a un solo pool di server Chat persistente e non può essere spostata in un altro pool o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
7. In **Nome** specificare un nome per la nuova categoria di chat.
    
8. In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
9. Per controllare l'abilitazione di inviti nelle chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita inviti**. Se l'opzione viene selezionata, le chat di questa categoria possono avere inviti attivati o disattivati; se invece viene deselezionata, alle chat di questa categoria non è consentito avere inviti. Se una chat dispone di inviti, quando un nuovo membro viene aggiunto a una chat room riceve una notifica della nuova chat nel client di Persistent Chat.
    
10. Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
11. Per controllare la cronologia chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat.** Se la casella è selezionata, le chat room diventano persistenti, in caso contrario i messaggi delle chat non diventano persistenti. Se è abilitata la conformità, le chat room verranno salvate nella conformità, ma gli utenti non potranno accedere ai messaggi datati. Questa opzione può essere utilizzata per le chat designate per le collaborazioni ad hoc in tempo reale che non necessitano della cronologia chat per essere salvate in modo permanente.
    
12. In **Modifica categoria** eseguire le operazioni seguenti:
    
    - In Appartenenza,  nella sezione Membri consentiti aggiungere o rimuovere utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
    - In Appartenenza, **nella** sezione Membri non consentiti aggiungere o rimuovere utenti e altre entità di Active Directory associate ai membri negati dalla chat room.
    
    - In **Appartenenza,** nella **sezione Creators,** aggiungere o rimuovere utenti e altre entità di Active Directory associate ai creatori della categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
13. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere Plan [for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)
  

