---
title: Creare un amministratore di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Riepilogo: leggere questo argomento per informazioni su come creare un ruolo di amministratore del server di chat persistente per abilitare la configurazione e la gestione iniziali dei servizi di chat persistenti in Skype for Business Server 2015.'
ms.openlocfilehash: b0edd3e1f10bf040be18242bfa600bb694169257
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195943"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Creare un amministratore di Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni su come creare un ruolo di amministratore del server di chat persistente per abilitare la configurazione e la gestione iniziali dei servizi di chat persistenti in Skype for Business Server 2015.
  
In Skype for Business Server gli utenti che eseguono attività specifiche devono essere assegnati come membri di uno o più gruppi specifici. Il controllo di accesso basato sui ruoli (RBAC) viene usato per concedere privilegi assegnando agli utenti i ruoli amministrativi predefiniti di Skype for Business Server. Questi ruoli corrispondono ai gruppi di sicurezza universale in servizi di dominio Active Directory. Ai membri del gruppo di sicurezza dell'amministratore della chat persistente, CsPersistentChatAdministrator, viene concesso l'accesso ai cmdlet del server di chat persistente, che possono essere eseguiti con Skype for Business Server Management Shell o con Skype for business Pannello di controllo server.
  
Prima di configurare e amministrare il server di chat persistente, assicurati che siano presenti i diritti e le autorizzazioni degli utenti appropriati e che tutti gli utenti che agiscono come amministratori della chat persistente vengano aggiunti al gruppo di sicurezza dell'amministratore della chat persistente.
  
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Creare un amministratore di Chat persistente

Per aggiungere un utente al gruppo di sicurezza dell'amministratore della chat persistente, CsPersistentChatAdministrator, eseguire la procedura seguente:
  
1. Utilizzando un account che disponga delle autorizzazioni per modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati utenti e computer di Active Directory.
    
2. Fare clic sul pulsante Start, scegliere tutti i programmi, strumenti di amministrazione e quindi fare clic su utenti e computer di Active Directory.
    
3. In utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore utenti.
    
4. Fare clic con il pulsante destro del mouse sul gruppo di sicurezza CsPersistentChatAdministrator e quindi scegliere Proprietà.
    
5. Nella scheda membri della finestra di dialogo Proprietà fare clic su Aggiungi.
    
6. Nella finestra di dialogo Seleziona utenti, computer, contatto o gruppi digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo nella casella Immettere i nomi degli oggetti da selezionare e quindi fare clic su OK.
    
7. Nella finestra di dialogo Proprietà fare clic su OK.
    

