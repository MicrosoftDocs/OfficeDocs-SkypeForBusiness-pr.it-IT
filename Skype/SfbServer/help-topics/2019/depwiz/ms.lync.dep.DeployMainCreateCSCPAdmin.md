---
title: Creare amministratori del pannello di controllo di Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: "Per concedere l'accesso al Skype for Business Server, eseguire le operazioni seguenti:"
ms.openlocfilehash: 7023af3163500dbc8052a3fc35dab37aa37cbf71
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755239"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Creare amministratori del pannello di controllo di Skype for Business Server
 
Per concedere l'accesso al Skype for Business Server, eseguire le operazioni seguenti:
  
1. Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.
    
2. Aprire **Utenti e computer di Active Directory**, espandere il proprio dominio, fare clic con il pulsante destro del mouse sul contenitore degli **** utenti e quindi scegliere **Proprietà**.
    
3. Nelle **** proprietà di CSAdministrators fare clic sulla scheda **Membri**.
    
4. Nella scheda Membri fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CSAdministrators. Fare clic su **OK**.
    
5. Nella scheda Membri verificare che siano presenti gli utenti o i gruppi selezionati. Fare clic su **OK**.
    
> [!TIP]
> Il Skype for Business Server pannello di controllo è uno strumento di controllo di accesso basato sui ruoli. L'appartenenza al gruppo CsAdministrator consente a un utente che utilizza il Pannello di controllo di Skype for Business Server controllo completo per tutte le funzioni di configurazione disponibili. Vi sono inoltre altri ruoli per funzioni specifiche. Gli utenti non devono essere abilitati per Skype for Business Server per essere resi membri dei gruppi di gestione. 
  
Altri ruoli includono:
  
- **CsArchiving:** I membri di questo gruppo possono eseguire tutte le funzioni di archiviazione, ad esempio la configurazione e la gestione del ruolo del server di archiviazione.
    
- **CsHelpDesk:** i membri di questo gruppo possono visualizzare la configurazione e la distribuzione, inclusi i criteri e le proprietà degli utenti. Tali membri possono inoltre eseguire attività di risoluzione dei problemi specifiche.
    
- **CsLocationAdministrator:** i membri di questo gruppo dispongono dei diritti utente minimi associati alla gestione del servizio per le chiamate di emergenza. Possono creare posizioni e identificatori di rete per tale servizio e associarli nella distribuzione.
    
- **CsResponseGroupAdministrator:** i membri di questo gruppo possono gestire e configurare il servizio Response Group.
    
- **CsServerAdministrator:** I membri possono gestire, monitorare e risolvere i problemi di tutti i server che eseguono Skype for Business Server.
    
- **CsUserAdministrator:** i membri di questo gruppo possono gestire, abilitare e disabilitare gli utenti e assegnare criteri esistenti agli utenti.
    
- **CsViewOnlyAdministrator:** I membri possono visualizzare la distribuzione e la configurazione delle informazioni sul server. Questa appartenenza consente a un membro di monitorare l'integrità dei server che eseguono Skype for Business Server.
    
- **CsVoiceAdministrator:** I membri possono creare, configurare e gestire le impostazioni vocali in Skype for Business Server.
    
Per mantenere l'integrità del controllo di accesso basato sui ruoli e della sicurezza, aggiungere utenti ai gruppi che definiscono il ruolo che l'utente svolge nella gestione della distribuzione Skype for Business Server ruoli.
  

