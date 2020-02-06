---
title: Creare amministratori del Pannello di controllo di Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: "Per concedere l'accesso a Skype for Business Server 2015, eseguire le operazioni seguenti:"
ms.openlocfilehash: f5300f9d3bf63e9deea103eb09e5a705953761d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823750"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Creare amministratori del Pannello di controllo di Skype for Business Server
 
Per concedere l'accesso a Skype for Business Server 2015, eseguire le operazioni seguenti:
  
1. Eseguire l'accesso come membri del gruppo Domain Admins o del gruppo RTCUniversalServerAdmins.
    
2. Aprire **Utenti e computer di Active Directory**, espandere il proprio dominio, fare clic con il pulsante destro del mouse sul contenitore degli **** utenti e quindi scegliere **Proprietà**.
    
3. Nelle **** proprietà di CsAdministrator fare clic sulla scheda **Membri**.
    
4. Nella scheda Membri fare clic su **Aggiungi**. In **Seleziona utenti, contatti, computer, account di servizio o gruppi** individuare **Immettere i nomi degli oggetti da selezionare**. Digitare i nomi degli utenti o dei gruppi da aggiungere al gruppo CsAdministrators. Fare clic su **OK**.
    
5. Nella scheda Membri verificare che siano presenti gli utenti o i gruppi selezionati. Fare clic su **OK**.
    
> [!TIP]
> Il pannello di controllo di Skype for Business Server è uno strumento di controllo di accesso basato sui ruoli. L'appartenenza al gruppo CsAdministrator offre a un utente che usa il controllo completo del pannello di controllo di Skype for Business Server per tutte le funzioni di configurazione disponibili. Vi sono inoltre altri ruoli per funzioni specifiche. Gli utenti non devono essere abilitati per Skype for Business Server per essere resi membri dei gruppi di gestione. 
  
Altri ruoli includono:
  
- **CsArchiving:** I membri di questo gruppo possono eseguire tutte le funzioni di archiviazione, ad esempio la configurazione e la gestione del ruolo del server di archiviazione.
    
- **CsHelpDesk:** i membri di questo gruppo possono visualizzare la configurazione e la distribuzione, inclusi i criteri e le proprietà degli utenti. Tali membri possono inoltre eseguire attività di risoluzione dei problemi specifiche.
    
- **CsLocationAdministrator:** i membri di questo gruppo dispongono dei diritti utente minimi associati alla gestione del servizio per le chiamate di emergenza. Possono creare posizioni e identificatori di rete per tale servizio e associarli nella distribuzione.
    
- **CsResponseGroupAdministrator:** i membri di questo gruppo possono gestire e configurare il servizio Response Group.
    
- **CsServerAdministrator:** I membri possono gestire, monitorare e risolvere i problemi di tutti i server che utilizzano Skype for Business Server.
    
- **CsUserAdministrator:** i membri di questo gruppo possono gestire, abilitare e disabilitare gli utenti e assegnare criteri esistenti agli utenti.
    
- **CsViewOnlyAdministrator:** I membri possono visualizzare la distribuzione e la configurazione delle informazioni sul server. Questa appartenenza consente a un membro di monitorare l'integrità dei server che utilizzano Skype for Business Server 2015.
    
- **CsVoiceAdministrator:** I membri possono creare, configurare e gestire le impostazioni relative alla voce in Skype for Business Server.
    
Per aiutare a mantenere la sicurezza e l'integrità del controllo di accesso basato sui ruoli, Aggiungi utenti ai gruppi che definiscono il ruolo che l'utente esegue nella gestione della distribuzione di Skype for Business Server.
  

