---
title: Distribuire il server Chat persistente in Skype for Business Server 2015
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
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire il server Chat persistente di Skype for Business Server 2015.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830476"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Distribuire il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire il server Chat persistente di Skype for Business Server 2015.
  
Per distribuire il server Chat persistente, è necessario: 
  
- Utilizzare Generatore di topologie per definire o importare e successivamente pubblicare la topologia e i componenti che si desidera distribuire.
    
- Preparare l'ambiente per la distribuzione dei componenti del server Chat persistente
    
- Installare e configurare i componenti del server Chat persistente per la distribuzione
    
Prima di distribuire il server Chat persistente, è consigliabile leggere [Plan for Persistent Chat Server in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Negli argomenti di pianificazione vengono descritti i requisiti hardware e software, le topologie possibili e gli scenari di collocazione. 
  
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015. 

## <a name="deployment-checklist"></a>Elenco di controllo di distribuzione

È possibile distribuire il server Chat persistente dopo la distribuzione della topologia iniziale, incluso almeno un pool Front End di Skype for Business Server o un server Skype for Business Standard Edition. Nell'elenco di controllo di distribuzione vengono descritti i passaggi di base necessari per distribuire il server Chat persistente e vengono forniti collegamenti per ulteriori dettagli.
  
**Processo di distribuzione del server Chat persistente**

|**Attività**|**Procedura**|**Appartenenze a gruppi e ruoli richiesti**|**Argomenti correlati**|
|:-----|:-----|:-----|:-----|
|**Installare l'hardware e il software prerequisiti** <br/> | Nell'hardware che soddisfa i requisiti di sistema installare gli elementi seguenti: <br/>  Nei front end server di Persistent Chat: <br/>  Sistema operativo che soddisfa i requisiti di sistema seguenti <br/>  Prerequisiti software per i computer che eseguono Skype for Business Server <br/>  Nel server che ospiterà il database del server Chat persistente: <br/>  Una versione supportata di SQL Server <br/>  Se è necessaria la conformità del server Chat persistente: <br/>  SQL Server nel server che ospiterà il database di conformità del server Chat persistente <br/> |Tutti gli utenti membri del gruppo Administrators locale.  <br/> |[Requisiti del server per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisiti ambientali per Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisiti hardware e software per il server Chat persistente in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Creare la topologia interna appropriata per supportare il server Chat persistente (e, facoltativamente, la conformità chat persistente)** <br/> | Eseguire Generatore di topologie per aggiungere un pool di server Chat persistente alla topologia: <br/>  Aggiungere componenti del server Chat persistente alla topologia <br/>  Creare un database di SQL Server per l'archivio del server Chat persistente (e un backup di SQL Server per il ripristino di emergenza) <br/>  Definire un nuovo archivio file di Skype for business o utilizzare un archivio file di Skype for business esistente per i file del server Chat persistente <br/>  Associare il pool di Skype for Business Server in grado di instradare le richieste al pool di server Chat persistente <br/>  Se è necessaria la conformità della chat persistente: <br/>  Aggiungere l'archivio di conformità di chat persistente <br/>  Fare clic sulla casella di controllo definizione pool di server Chat persistente per abilitare la conformità <br/>  Pubblicare la topologia. <br/>  Se si installa il server Chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool di server Chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nel server Standard Edition. <br/> |Per definire una topologia, un account membro del gruppo Users locale.  <br/> Per pubblicare la topologia, un account membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e l'utente deve disporre anche di autorizzazioni di controllo completo (lettura/scrittura/modifica) sull'archivio file di Skype for business per i file del server Chat persistente, in modo che il generatore di topologie possa configurare gli elenchi DACL necessari.  <br/> |[Creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Aggiungere il server Chat persistente alla topologia di Skype for Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Distribuire il server Chat persistente** <br/> | Eseguire il programma di installazione di Skype for Business Server su tutti i computer che eseguono il server Chat persistente. La configurazione del server Chat persistente è integrata nella distribuzione guidata di Skype for Business Server che fornisce le istruzioni seguenti: <br/>  Distribuire l'archivio di gestione locale <br/>  Installare servizi di chat persistente <br/>  Richiedere e assegnare i certificati <br/>  Eseguire e avviare i servizi <br/> |Tutti gli utenti membri del gruppo Administrators locale.  <br/> |[Distribuire il server Chat persistente in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Creare un amministratore di Chat persistente** <br/> |Aggiungere gli utenti al gruppo di sicurezza CsPersistentChatAdministrator.  <br/> |Tutti gli utenti membri del gruppo degli amministratori di dominio.  <br/> |[Creare un amministratore di chat persistente in Skype for Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurare il server chat persistente** <br/> | Configurare gli utenti: <br/>  L'utente deve essere abilitato dai criteri per accedere al server Chat persistente. Per impostazione predefinita, i criteri sono disattivati per tutti gli utenti e possono essere definiti nell'ambito globale, del sito, del pool e dell'utente <br/>  Configurare le impostazioni <br/> |L'utente deve essere membro di CsPersistentChatAdministrator. Per modificare i criteri, l'utente deve essere almeno membro di CsUserAdministrator.  <br/> |[Gestire il server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

