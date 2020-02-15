---
title: Abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: In questo argomento viene descritto come abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, è consigliabile leggere quanto segue:.
ms.openlocfilehash: 87dcafcfe0c5ce69bcdbcd9809d23cea80c234ba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050188"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server
 
In questo argomento viene descritto come abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, è consigliabile leggere quanto segue:.
  
- Per informazioni su come configurare la connettività ibrida, vedere Pianificare la connettività ibrida [tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Per ulteriori informazioni sulla pianificazione della distribuzione, vedere [Plan Phone System in Office 365 con connettività PSTN locale in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Per ulteriori informazioni sul sistema telefonico in Office 365, incluse le licenze e i piani, vedere [PSTN Calling plans for Skype for business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Spostamento di utenti nel sistema telefonico in Office 365 con connettività PSTN locale

Prima di spostare gli utenti in Skype for business online, si consiglia di abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online. Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e la sezione Considerazioni speciali di [abilitare gli utenti per VoIP aziendale nei locali](enable-the-users-for-enterprise-voice-on-premises.md) (eseguiti mentre gli utenti sono ospitati in locale). 
  
Tutti gli utenti devono essere creati in Active Directory in locale e sincronizzati con Office 365 utilizzando la versione supportata di Azure AD Connector. Non è possibile abilitare gli utenti per il sistema telefonico in Office 365 che sono stati creati direttamente in Azure AD. Se si desidera abilitare il sistema telefonico in Office 365 con connettività PSTN locale per un utente che è stato creato in Azure AD, è necessario creare un nuovo account per tale utente nell'annuncio locale, configurare l'account in locale, quindi sincronizzare l'account utilizzando una versione supportata dello strumento Azure AD Connector. 
  
L'abilitazione di un utente per il sistema telefonico in Office 365 con connettività PSTN locale e lo spostamento in Skype for business online richiede i passaggi seguenti:
  
- [Abilitare gli utenti per VoIP aziendale nei locali](enable-the-users-for-enterprise-voice-on-premises.md) (eseguiti mentre gli utenti sono ospitati in locale).
    
- [Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguito mentre gli utenti sono ospitati in locale).
    
- [Sincronizzare gli utenti con il cloud e assegnare licenze](synchronize-users-to-the-cloud-and-assign-licenses.md) (eseguite con Office 365).
    
- [Spostare gli utenti locali in Skype for business online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (eseguito utilizzando Windows PowerShell in locale, ma usando le credenziali di amministratore di Office 365).
    
- [Abilitare gli utenti per Enterprise Voice online e il sistema telefonico in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (eseguito tramite Remote PowerShell.
    

