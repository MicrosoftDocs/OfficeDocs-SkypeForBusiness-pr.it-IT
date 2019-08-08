---
title: Distribuire il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Riepilogo: leggere questo argomento per informazioni su come distribuire il server di chat persistente di Skype for Business Server 2015.'
ms.openlocfilehash: 2d3c9ca11447a5be212a053d8c5cb002ada4c522
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240830"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Distribuire il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni su come distribuire il server di chat persistente di Skype for Business Server 2015.
  
Per distribuire il server di chat persistente, è possibile: 
  
- Usare generatore di topologia per definire o importare e successivamente pubblicare la topologia e i componenti che si desidera distribuire
    
- Preparare l'ambiente per la distribuzione dei componenti del server di chat persistente
    
- Installare e configurare i componenti del server di chat persistenti per la distribuzione
    
Prima di distribuire il server di chat persistente, è consigliabile leggere il [piano per il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Gli argomenti di pianificazione descrivono i requisiti hardware e software, le topologie possibili e gli scenari di collocazione. 
  
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 

## <a name="deployment-checklist"></a>Elenco di controllo della distribuzione

È possibile distribuire il server di chat persistente dopo la distribuzione della topologia iniziale, incluso almeno un pool Front-End di Skype for Business Server o un server Skype for Business Standard Edition. L'elenco di controllo della distribuzione descrive i passaggi di base necessari per distribuire il server di chat persistente e fornisce collegamenti per ulteriori dettagli.
  
**Processo di distribuzione del server di chat persistente**

|**Attività**|**Passaggi**|**Ruoli obbligatori e appartenenze ai gruppi**|**Argomenti correlati**|
|:-----|:-----|:-----|:-----|
|**Installare hardware e software prerequisiti** <br/> | Sull'hardware che soddisfa i requisiti di sistema, installare le operazioni seguenti: <br/>  Nei server front end del server di chat persistente: <br/>  Sistema operativo che soddisfa i requisiti di sistema <br/>  Prerequisiti software per i computer che eseguono Skype for Business Server <br/>  Nel server che ospiterà il database del server di chat persistente: <br/>  Una versione supportata di SQL Server <br/>  Se è necessaria la conformità del server di chat persistente: <br/>  SQL Server nel server che ospiterà il database di conformità del server di chat persistente <br/> |Qualsiasi utente membro del gruppo Administrators locale.  <br/> |[Requisiti server di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisiti ambientali di Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisiti hardware e software per il server Chat persistente](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Creare la topologia interna appropriata per supportare il server di chat persistente e, facoltativamente, la conformità della chat persistente** <br/> | Eseguire Generatore di topologie per aggiungere un pool di server di chat persistente alla topologia: <br/>  Aggiungere componenti del server di chat persistenti alla topologia <br/>  Creare un database di SQL Server per l'archivio di Chat Server persistente (e un backup di SQL Server per il ripristino di emergenza) <br/>  Definire un nuovo archivio di file Skype for business o usare un archivio di file Skype for business esistente per i file del server di chat persistente <br/>  Associare il pool di Skype for Business Server che può instradare le richieste a questo pool di server di chat persistente <br/>  Se è necessaria la conformità della chat persistente: <br/>  Aggiungere lo Store di conformità della chat persistente <br/>  Fare clic sulla casella di controllo della definizione del pool di Persistent Chat Server per abilitare la conformità <br/>  Pubblicare la topologia. <br/>  Se si installa il server di chat persistente in Standard Edition, il nome di dominio completo (FQDN) del pool del server di chat persistente deve corrispondere al server Standard Edition e i database di SQL Server sono collocati nell'istanza di SQL Server Express nello standard Server Edition <br/> |Per definire una topologia, un account membro del gruppo utenti locali.  <br/> Per pubblicare la topologia, un account che sia membro del gruppo Domain Admins e del gruppo RTCUniversalServerAdmins e che l'utente disponga anche delle autorizzazioni di controllo completo (lettura/scrittura/modifica) nell'archivio file di Skype for business per i file del server di chat persistente, quindi il generatore di topologia può configurare gli elenchi DACL obbligatori.  <br/> |[Creare e pubblicare una nuova topologia in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Aggiungere il server di chat persistente alla topologia di Skype for Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Distribuire il server Chat persistente** <br/> | Eseguire la configurazione di Skype for Business Server in tutti i computer che eseguono il server di chat persistente. La configurazione del server di chat persistente è integrata nella distribuzione guidata di Skype for Business Server che fornisce le istruzioni seguenti: <br/>  Distribuire l'archivio di gestione locale <br/>  Installare servizi di chat persistenti <br/>  Richiedere e assegnare certificati <br/>  Eseguire e avviare i servizi <br/> |Qualsiasi utente membro del gruppo Administrators locale.  <br/> |[Distribuire il server Chat persistente in Skype for Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Creare un amministratore di Chat persistente** <br/> |Aggiungere utenti al gruppo di sicurezza CsPersistentChatAdministrator.  <br/> |Qualsiasi utente membro di Domain Administrators.  <br/> |[Creare un amministratore di Chat persistente](create-a-persistent-chat-administrator.md) <br/> |
|**Configurare il server Chat persistente** <br/> | Configurare gli utenti: <br/>  L'utente deve essere abilitato tramite criteri per accedere al server di chat persistente. Per impostazione predefinita, il criterio è disattivato per tutti gli utenti e può essere definito in ambito globale/sito/pool/User. <br/>  Configurare le impostazioni <br/> |L'utente deve essere un membro di CsPersistentChatAdministrator. Per modificare i criteri, l'utente deve essere in CsUserAdministrator, almeno.  <br/> |[Gestire il server Chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

