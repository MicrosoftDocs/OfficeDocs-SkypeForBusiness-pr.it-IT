---
title: Prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: informazioni sui prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767239"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server
 
**Riepilogo:** Informazioni sui prerequisiti per la sicurezza e la configurazione di VoIP aziendale in Skype for Business Server.
  
Prima di distribuire Enterprise Voice, verificare che l'infrastruttura soddisfi i requisiti di sicurezza, configurazione utente e prerequisiti hardware specifici dello scenario. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Diritti amministrativi e infrastruttura dei certificati

Prima della distribuzione, controllare quanto segue:
  
- Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.
    
- Gli amministratori che eseguono le attività di configurazione devono avere diritti adeguati:
    
  - **CsVoiceAdministrator:** Questo ruolo di amministratore può eseguire attività di configurazione vocale, gestire le applicazioni vocali e assegnare criteri vocali agli utenti finali.
    
  - **CsUserAdministrator:** Questo ruolo di amministratore può gestire le proprietà degli utenti, ad esempio l'abilitazione di VoIP aziendale per un utente. Questo ruolo di amministratore può anche assegnare criteri per utente, ad eccezione dei criteri di archiviazione. trasferire utenti; e Gestisci telefoni per area comune e dispositivi analogici.
    
  - **CsAdministrator:** Questo ruolo di amministratore può eseguire tutte le attività di CsVoiceAdministrator e CsUserAdministrator.
    
- L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata tramite un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.
    
    > [!NOTE]
    > Per informazioni dettagliate sui requisiti dei certificati in Skype for Business Server, vedere [requisiti ambientali per i requisiti di Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server per Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configurazione utente

Se il Mediation Server è stato collocato con ogni pool Front end o server Standard Edition durante la distribuzione front-end, le impostazioni utente necessarie per Enterprise Voice sono state configurate automaticamente durante l'installazione dei file per i ruoli del server.
  
Se si sta distribuendo di nuovo il carico di lavoro VoIP aziendale in questo momento, prima di iniziare il processo di distribuzione, designare un numero di telefono principale per ogni utente che si prevede di abilitare per VoIP aziendale. Come amministratore, sei responsabile per verificare che questo numero sia univoco. Prima dell'implementazione, tutti i numeri di telefono primari devono essere normalizzati (formattati correttamente) e copiati nella proprietà **URI della linea** di ogni utente usando il pannello di controllo di Skype for Business Server.
  
> [!NOTE]
> Per esempi di numeri di telefono primari necessari per la distribuzione di VoIP aziendale, Vedi [regole di normalizzazione di esempio](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Passaggi successivi: installare i file o configurare la connettività PSTN

Dopo aver verificato il software e i prerequisiti ambientali per Enterprise Voice, è possibile:
  
- Installare il Mediation Server, come descritto in [distribuire un Mediation Server in Generatore di topologia in Skype for Business Server](deploy-a-mediation-server.md), ma solo se si vuole distribuire un server o un pool di mediazione autonomo perché i server di mediazione vengono installati come parte del pool di front-end o del processo di distribuzione del server Standard Edition durante la collocazione.
    
- In alternativa, iniziare a configurare le impostazioni per instradare le chiamate per gli utenti di VoIP aziendale, come descritto in [configurare Trunks in Skype for Business Server](configure-trunks.md).
    

