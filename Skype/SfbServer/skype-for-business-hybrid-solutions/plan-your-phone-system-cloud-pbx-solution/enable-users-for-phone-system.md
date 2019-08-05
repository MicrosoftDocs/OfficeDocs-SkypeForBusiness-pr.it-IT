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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Questo argomento descrive come abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale. Prima di seguire la procedura descritta in questo argomento, leggere quanto segue:.
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190835"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server
 
Questo argomento descrive come abilitare gli utenti per il sistema telefonico in Office 365 con connettività PSTN locale. Prima di seguire la procedura descritta in questo argomento, leggere quanto segue:.
  
- Per informazioni su come configurare la connettività ibrida, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Per informazioni sulla pianificazione della distribuzione, vedere [pianificare il sistema telefonico in Office 365 con connettività PSTN locale in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Per altre informazioni sul sistema telefonico in Office 365, incluse le licenze e i piani, vedere [piani per chiamate PSTN per Skype for business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Spostamento di utenti nel sistema telefonico in Office 365 con connettività PSTN locale

Prima di spostare gli utenti in Skype for business online, è consigliabile abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online. Per altre informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e la sezione Considerazioni speciali [consente agli utenti di accedere a VoIP aziendale locale](enable-the-users-for-enterprise-voice-on-premises.md) (eseguito durante l'esecuzione degli utenti locale). 
  
Tutti gli utenti devono essere creati in Active Directory in locale e sincronizzati con Office 365 usando la versione supportata di Azure AD Connector. Non è possibile abilitare gli utenti per il sistema telefonico in Office 365 creati direttamente in Azure AD. Se si vuole abilitare il sistema telefonico in Office 365 con la connettività PSTN locale per un utente creato in Azure AD, è necessario creare un nuovo account per l'utente nell'annuncio locale, configurare l'account locale e quindi sincronizzare l'account con il una versione supportata dello strumento Azure AD Connector. 
  
L'abilitazione di un utente per il sistema telefonico in Office 365 con connettività PSTN locale e lo spostamento in Skype for business online richiede la procedura seguente:
  
- [Consentire agli utenti di VoIP aziendale in locale](enable-the-users-for-enterprise-voice-on-premises.md) (eseguita mentre gli utenti vengono ospitati in locale).
    
- [Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguita mentre gli utenti vengono ospitati in locale).
    
- [Sincronizzare gli utenti con il cloud e assegnare licenze](synchronize-users-to-the-cloud-and-assign-licenses.md) (eseguita con Office 365).
    
- [Trasferire utenti locali in Skype for business online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (eseguita con Windows PowerShell locale, ma con le credenziali di amministratore di Office 365).
    
- [Abilitare gli utenti per Enterprise Voice online e il sistema telefonico in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (eseguita tramite PowerShell remoto.
    

