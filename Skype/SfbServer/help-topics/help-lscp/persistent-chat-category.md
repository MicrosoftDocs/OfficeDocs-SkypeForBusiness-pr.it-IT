---
title: Categoria Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: È possibile usare la sezione Categoria della pagina Chat persistente per configurare le categorie. Una categoria di chat room persistente è una struttura logica per l'organizzazione di chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso (ACL) per controllare gli utenti e i gruppi di utenti che possono creare o unirsi alle chat room. È possibile usare le categorie per applicare ethical wall tra diverse suddivisioni delle organizzazioni.
ms.openlocfilehash: fc430c7d61ad4662d28f81594d59bf95d03f84c8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195393"
---
# <a name="persistent-chat-category"></a>Categoria Chat persistente
 
È possibile usare la sezione **Categoria** della pagina **Chat persistente** per configurare le categorie. Una categoria di chat room persistente è una struttura logica per l'organizzazione di chat room. Una categoria definisce un insieme predefinito di elenchi di controllo di accesso (ACL) per controllare gli utenti e i gruppi di utenti che possono creare o unirsi alle chat room. È possibile usare le categorie per applicare ethical wall tra diverse suddivisioni delle organizzazioni.
  
Le categorie di chat room possono contenere chat room, ma non altre categorie. Ogni categoria descrive il suo contenuto con metadati, ad esempio _nome_ e _Descrizione_. Inoltre, la categoria contiene proprietà che possono essere impostate per controllare il comportamento delle chat room ad essa appartenenti, come se le chat room consentissero __ gli inviti o gli _upload di file_o contengano la _cronologia delle chat_.
  
Per creare una nuova categoria, vedere [gestire le categorie nel server di chat persistente in Skype for Business server 2015](../../manage/persistent-chat/categories.md). Se si è un amministratore della chat persistente, è possibile creare categorie usando il pannello di controllo o i cmdlet di Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Categoria** è possibile eseguire le attività seguenti:
  
- Creare o modificare una nuova categoria
    
- Spostare una chat room da una categoria all'altra
    
- Eliminare una chat room o una categoria
    
## <a name="to-configure-categories-for-chat-rooms"></a>Per configurare le categorie delle chat room

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Nella barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Categoria**.
    
    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.
    
4. Nella pagina **Categoria** fare clic su **Nuovo** o **Modifica**.
    
5. In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui deve essere creata la categoria. Il servizio è il pool di server di chat persistente usato dalla chat persistente (client) per identificare a quale pool appartiene la categoria. Una categoria può appartenere a un solo pool di server di chat persistente e non può essere spostata in un'altra o condivisa con un altro pool.
    
6. In **Nuova categoria** eseguire le operazioni seguenti:
    
7. In **Nome** specificare un nome per la nuova categoria di chat.
    
8. In **Descrizione** fornire una descrizione dettagliata della categoria di chat, ad esempio una categoria di chat per Contoso.
    
9. Per controllare se gli inviti possono essere abilitati per le chat room appartenenti a questa categoria, selezionare o deselezionare la casella di controllo **Abilita invito** . Se selezionata, le camere di questa categoria possono avere inviti o disattivarli; Se deselezionata, le camere di questa categoria non possono avere inviti. Se una sala contiene inviti, quando un nuovo membro viene aggiunto a una sala, riceve una notifica della nuova sala nel client di chat persistente.
    
10. Per controllare i caricamenti file nelle chat room che appartengono a questa categoria, selezionare o deselezionare la casella di controllo **Abilita caricamento file**. Se selezionata, per le chat di questa categoria è possibile abilitare o disabilitare i caricamenti file. Se deselezionata, per le chat di questa categoria non sono consentiti caricamenti file.
    
     > [!IMPORTANT]
     > Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che usano Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat possono pubblicare file in una sala. Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente. 
  
11. Per controllare la cronologia chat, selezionare o deselezionare la casella di controllo **Abilita cronologia chat** . Se selezionata, le chat room diventano permanenti; in caso contrario, i messaggi di chat non vengono mantenuti. Se è abilitata la conformità, le chat room verranno salvate in conformità, ma gli utenti non potranno accedere ai messaggi meno recenti. Questa opzione può essere usata per le sale designate per le collaborazioni ad hoc in tempo reale che non richiedono la cronologia della chat per essere rese persistenti.
    
12. In **Modifica categoria** eseguire le operazioni seguenti:
    
    - In **appartenenza**, nella sezione **consentiti membri** , aggiungere o rimuovere utenti e altre entità di servizi di dominio Active Directory (utenti, gruppi di distribuzione, unità organizzative e così via) che sono autorizzati ad essere aggiunti come membri delle chat room appartenenza alla categoria. Le entità consentite da una categoria possono cercare le chat della categoria (a meno che la chat non sia nascosta, caso in cui solo i membri della chat possono cercarla nella directory).
    
    - In **appartenenza**, nella sezione **membri negati** , aggiungere o rimuovere utenti e altre entità Active Directory associate ai membri negati dalla sala.
    
    - In **appartenenza**, nella sezione **Creators** , aggiungere o rimuovere utenti e altre entità Active Directory associate agli autori per la categoria. Per creatore si intende un utente con autorizzazioni per la creazione di chat room e l'assegnazione di membri e responsabili delle chat.
    
13. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [distribuire il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gestire il server di chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

