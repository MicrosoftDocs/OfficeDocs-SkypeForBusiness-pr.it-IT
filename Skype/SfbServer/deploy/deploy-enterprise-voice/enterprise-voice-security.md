---
title: Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Riepilogo: informazioni sui prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830846"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server
 
**Riepilogo:** Informazioni sui prerequisiti di sicurezza e configurazione per VoIP aziendale in Skype for Business Server.
  
Prima di distribuire VoIP aziendale, verificare che l'infrastruttura soddisfi i prerequisiti hardware di sicurezza, configurazione utente e specifici dello scenario seguenti. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Diritti amministrativi e infrastruttura dei certificati

Prima della distribuzione, controllare quanto segue:
  
- Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.
    
- Gli amministratori che eseguono le attività di configurazione devono disporre di diritti appropriati:
    
  - **CsVoiceAdministrator:** questo ruolo di amministratore consente di eseguire attività di configurazione vocale, di gestire le applicazioni vocali e di assegnare criteri vocali agli utenti finali.
    
  - **CsUserAdministrator:** questo ruolo di amministratore consente di gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Consente inoltre di assegnare criteri per utente, ad eccezione del criterio di archiviazione, di spostare gli utenti e di gestire i telefoni di area comune e i dispositivi analogici.
    
  - **CsAdministrator:** questo ruolo di amministratore consente di eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.
    
- La distribuzione e la configurazione dell'infrastruttura MKI (Managed Key Infrastructure) vengono eseguite utilizzando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.
    
    > [!NOTE]
    > Per informazioni dettagliate sui requisiti dei certificati in Skype for Business Server, vedere Requisiti ambientali per [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Server per Skype for Business Server [2019.](../../../SfBServer2019/plan/system-requirements.md) 
  
## <a name="user-configuration"></a>Configurazione utente

Se il Mediation Server è stato collocato con ogni pool Front End o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per VoIP aziendale sono state configurate automaticamente durante l'installazione dei file per tali ruoli del server.
  
Se si sta procedendo ora alla distribuzione del carico di lavoro di VoIP aziendale, prima di iniziare il processo di distribuzione designare un numero di telefono primario per ogni utente che si intende abilitare per VoIP aziendale. In qualità di amministratori, è necessario verificare che questo numero sia univoco. Prima dell'implementazione, tutti i numeri di telefono principali devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI** linea di ogni utente tramite il Pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> Per esempi di numeri di telefono principali necessari per VoIP aziendale distribuzione, vedere [Regole di normalizzazione di esempio.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules) 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Passaggi successivi: Installare i file o configurare la connettività PSTN

Dopo aver verificato i prerequisiti software e ambientali per VoIP aziendale è possibile:
  
- Installare il Mediation Server, come descritto in Distribuire un Mediation Server in Generatore di topologie [in Skype for Business Server,](deploy-a-mediation-server.md)ma solo se si desidera distribuire un Mediation Server autonomo o un pool perché i Mediation Server vengono installati come parte del processo di distribuzione del pool Front End o del server Standard Edition quando sono collocati.
    
- Oppure, iniziare a configurare le impostazioni per instradare le chiamate VoIP aziendale utenti, come descritto [in Configurare i trunk in Skype for Business Server.](configure-trunks.md)
    

