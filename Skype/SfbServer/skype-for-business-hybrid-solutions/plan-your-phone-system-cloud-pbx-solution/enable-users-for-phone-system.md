---
title: Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'In questo argomento viene descritto come abilitare gli utenti Sistema telefonico con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, leggere quanto segue: .'
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563663"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Abilitare gli utenti per Sistema telefonico con connettività PSTN in locale in Skype for Business Server

In questo argomento viene descritto come abilitare gli utenti Sistema telefonico con connettività PSTN locale. Prima di eseguire la procedura descritta in questo argomento, leggere quanto segue: .
  
- Per informazioni su come configurare la connettività ibrida, vedere [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype for Business Server [and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Per informazioni sulla pianificazione della distribuzione, vedere [Plan Sistema telefonico with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Per ulteriori informazioni sulle Sistema telefonico, incluse le licenze e i piani, vedere Piani per chiamate [PSTN per Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
> [!Important]
> Skype for Business Online è stato ritirato il 31 luglio 2021 e la connettività PSTN tra l'ambiente locale, tramite Skype for Business Server o Cloud Connector Edition e Skype for Business Online, non è più supportata. Informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Spostamento degli utenti Sistema telefonico con connettività PSTN locale

Prima di spostare gli utenti in Skype for Business Online, è consigliabile abilitare gli utenti in locale in Skype for Business Server o Lync Server 2013 e quindi spostarli online. Per ulteriori informazioni, vedere [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e la sezione considerazioni speciali di Enable the users for VoIP aziendale on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (eseguita mentre gli utenti sono ospitati in locale). 
  
Tutti gli utenti devono essere creati in Active Directory locale e sincronizzati con Microsoft 365 o Office 365 utilizzando la versione supportata di Azure AD Connector. Non è possibile abilitare gli utenti Sistema telefonico in Office 365 creati direttamente in Azure AD. Se si desidera abilitare Sistema telefonico con connettività PSTN locale per un utente creato in Azure AD, sarà necessario creare un nuovo account per tale utente nell'ad locale, configurare l'account locale e quindi sincronizzare l'account utilizzando una versione supportata dello strumento connettore di Azure AD. 
  
Per abilitare un utente Sistema telefonico con connettività PSTN locale e quindi spostarli in Skype for Business Online, è necessario eseguire la procedura seguente:
  
- [Abilitare gli utenti per VoIP aziendale locale](enable-the-users-for-enterprise-voice-on-premises.md) (eseguito mentre gli utenti sono ospitati in locale).
    
- [Assegnare un criterio di routing vocale](assign-a-voice-routing-policy.md) (eseguito mentre gli utenti sono ospitati in locale).
    
- [Sincronizzare gli utenti nel cloud e assegnare le licenze](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (eseguite Office 365).
    
- [Spostare gli utenti locali](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) in Skype for Business Online (eseguito usando Windows PowerShell locale, ma usando le credenziali di amministratore Office 365 locale).
    
- [Abilitare gli utenti per VoIP aziendale online e Sistema telefonico segreteria telefonica](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (eseguita tramite Remote PowerShell.
