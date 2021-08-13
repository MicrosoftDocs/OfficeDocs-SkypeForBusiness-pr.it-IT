---
title: Categoria Persistent Chat
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
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: È possibile utilizzare la sezione Categoria della pagina Persistent Chat per configurare le categorie. Una categoria di chat persistente è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso per il controllo degli utenti e dei gruppi di utenti che possono creare chat room o prendervi parte. Le categorie possono essere usate per applicare gli ethical wall tra le varie suddivisioni all'interno delle organizzazioni.
ms.openlocfilehash: 009cc7ef5cd35b7637f687043a0a5c5ddd24fa2f228c95a8bb4660b4c9140b47
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299822"
---
# <a name="persistent-chat-category"></a>Categoria di Chat persistente
 
È possibile utilizzare la **sezione Categoria** della pagina **Persistent Chat** per configurare le categorie. Una categoria di chat persistente è una struttura logica per l'organizzazione delle chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso per il controllo degli utenti e dei gruppi di utenti che possono creare chat room o prendervi parte. Le categorie possono essere usate per applicare gli ethical wall tra le varie suddivisioni all'interno delle organizzazioni.
  
Le categorie di chat room possono contenere chat room, ma non altre categorie. Ogni categoria descrive il contenuto con metadati, ad esempio _Name_ e _Description._ Inoltre, la categoria dispone di proprietà che possono essere impostate per controllare il comportamento delle  chat room ad essa appartenenti, ad esempio se le chat room consentono inviti o caricamenti _di file_ o contengono Cronologia _chat._
  
Per creare una nuova categoria, vedere [Manage categories in Persistent Chat Server in Skype for Business Server 2015.](../../manage/persistent-chat/categories.md) Gli amministratori di Persistent Chat possono creare categorie utilizzando il Pannello di controllo o Windows PowerShell cmdlet.
  
## <a name="tasks-that-you-can-perform"></a>Attività eseguibili

Nella pagina **Categoria** è possibile eseguire le attività seguenti:
  
- Creare o modificare una nuova categoria
    
- Spostare una chat room da una categoria a un'altra
    
- Eliminare una chat room o una categoria
    
## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server Chat persistente, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Selezionare un servizio** selezionare il servizio corrispondente al pool di server Chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server Chat persistente utilizzato da Persistent Chat (client) per identificare il pool a cui appartiene la categoria. Una categoria può appartenere a un solo pool di server Chat persistente e non può essere spostata in un altro pool o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
7. In **Nome** specificare un nome per la nuova categoria di chat.
    
8. In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
9. Per controllare l'abilitazione di inviti nelle chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita inviti**. Se l'opzione viene selezionata, le chat di questa categoria possono avere inviti attivati o disattivati; se invece viene deselezionata, alle chat di questa categoria non è consentito avere inviti. Se una sala dispone di inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova chat nel client Persistent Chat.
    
10. Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
     > [!IMPORTANT]
     > Questa impostazione viene applicata al server perché le applicazioni personalizzate o i client di Group Chat precedenti che utilizzano Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat può pubblicare file in una sala. Il client Lync 2013 non dispone della funzionalità di caricamento/download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server Chat persistente. 
  
11. Per controllare la cronologia delle chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat.** Se la casella è selezionata, le chat room diventano persistenti, in caso contrario i messaggi delle chat non diventano persistenti. Se è abilitata la conformità, le chat room verranno salvate nella conformità, ma gli utenti non potranno accedere ai messaggi datati. Questa opzione può essere utilizzata per le sale designate per le collaborazioni ad hoc in tempo reale che non necessitano di salvare in modo permanente la cronologia delle chat.
    
12. In **Modifica categoria** eseguire le operazioni seguenti:
    
    - In Appartenenza  , nella sezione Membri consentiti, aggiungere o rimuovere gli utenti e altre entità di Servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che possono essere aggiunti come membri delle chat room appartenenti alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
    - In **Appartenenza**, nella **sezione Membri** negati aggiungere o rimuovere utenti e altre entità di Active Directory associate ai membri negati dalla chat room.
    
    - In **Appartenenza,** nella **sezione Creatori,** aggiungere o rimuovere utenti e altre entità di Active Directory associate ai creatori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
13. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)Deploy Persistent Chat Server in Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015.](../../manage/persistent-chat/persistent-chat.md)
  

