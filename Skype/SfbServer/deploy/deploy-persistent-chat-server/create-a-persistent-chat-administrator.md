---
title: Creare un amministratore di Persistent Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Riepilogo: leggere questo argomento per informazioni su come creare un ruolo di amministratore del server Chat persistente per abilitare la configurazione iniziale e la gestione dei servizi Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 61b601399f1e21fa36a7f7b9ead1a458b577179295c40154a78f861c6bc0c156
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337096"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Creare un amministratore di Persistent Chat in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come creare un ruolo di amministratore del server Chat persistente per abilitare la configurazione iniziale e la gestione dei servizi Chat persistente in Skype for Business Server 2015.
  
In Skype for Business Server, gli utenti che eseguono attività specifiche devono essere assegnati come membri di uno o più gruppi specifici. Role-Based controllo di accesso (RBAC) viene utilizzato per concedere privilegi assegnando gli utenti a ruoli amministrativi Skype for Business Server predefiniti. Questi ruoli corrispondono ai gruppi di sicurezza universali in Servizi di dominio Active Directory. Ai membri del gruppo di sicurezza amministratore di Persistent Chat, CsPersistentChatAdministrator, viene concesso l'accesso ai cmdlet del server Chat persistente, che possono essere eseguiti utilizzando Skype for Business Server Management Shell o il Pannello di controllo di Skype for Business Server.
  
Prima di configurare e amministrare il server Chat persistente, verificare che siano presenti le autorizzazioni e i diritti utente appropriati e che tutti gli utenti che agiranno come amministratori di Persistent Chat siano aggiunti al gruppo di sicurezza Amministratore chat persistente.
  
> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare Persistent Chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Creare un amministratore di Chat persistente

Per aggiungere un utente al gruppo di sicurezza Dell'amministratore di Persistent Chat, CsPersistentChatAdministrator, eseguire la procedura seguente:
  
1. Utilizzando un account autorizzato a modificare l'appartenenza a un gruppo di Active Directory, accedere a un computer in cui sono stati installati Utenti e computer di Active Directory.
    
2. Fare clic sul pulsante Start, scegliere Tutti i programmi, Strumenti di amministrazione e quindi Utenti e computer di Active Directory.
    
3. In Utenti e computer di Active Directory espandere il nome del dominio e fare clic sul contenitore degli utenti.
    
4. Fare clic con il pulsante destro del mouse sul gruppo di sicurezza CsPersistentChatAdministrator e quindi scegliere Proprietà.
    
5. Nella finestra di dialogo Proprietà fare clic su Aggiungi nella scheda Membri.
    
6. Nella finestra di dialogo Seleziona utenti, computer, contatti o gruppi digitare il nome utente o il nome visualizzato dell'utente da aggiungere al gruppo nella casella Immettere i nomi degli oggetti da selezionare e quindi fare clic su OK.
    
7. Nella finestra di dialogo Proprietà fare clic su OK.
    

