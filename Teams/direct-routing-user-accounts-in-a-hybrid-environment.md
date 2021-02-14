---
title: Account utente in ambiente ibrido con PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni sulle diverse combinazioni di creazione utente e sulle combinazioni supportate o non supportate.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7b41eb474d7574aa23b5fa195219794ed715424
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690872"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Account utente in un ambiente ibrido con connettività PSTN

## <a name="about-the-environment"></a>Informazioni sull'ambiente

Questo articolo si applica agli ambienti in cui sono disponibili tutti gli ambienti seguenti: 
 
- Skype for Business Server o Lync Server 2013 
- Un'organizzazione di Microsoft 365 o Office 365 
- Connettività ibrida configurata tra Skype for Business Server e Skype for Business Online o il tenant di Microsoft Teams 
- Utenti abilitati a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) da e verso il client

 
Se si ha un ambiente diverso, ad esempio Skype for Business Cloud Connector Edition, la distribuzione ibrida non è configurata o gli utenti non sono abilitati per le chiamate PSTN, la matrice di supporto sarà diversa.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informazioni sulle combinazioni e sulla dichiarazione di supporto  

Un ambiente ibrido di Skype for Business con connettività PSTN offre flessibilità per quanto riguarda la fornitura dei servizi utente e il provisioning e la gestione degli account utente. Ma l'estensione delle opzioni potrebbe creare alcune combinazioni non supportate. Questa sezione illustra le diverse combinazioni di creazione degli utenti, seguite da una dichiarazione di supporto.


**Definizioni:**   
- **VoIP aziendale:** Opzione per fornire l'accesso a PSTN per gli utenti con account utente Skype for Business locale. Skype for Business Mediation Server locale fornisce connettività a PSTN.  
- **Connettività vocale ibrida:** Opzione per fornire l'accesso a PSTN per gli utenti con account Skype for Business online. Skype for Business Mediation Server locale fornisce connettività a PSTN. 
- **Routing diretto:** Opzione per fornire l'accesso a PSTN per gli utenti con account Skype for Business online, licenza Microsoft Teams, utilizzando client Microsoft Teams. L'SBC è connesso al proxy SIP in Microsoft 365 o Office 365 senza bisogno di software locale di Microsoft.

  
**L'ambiente supporta le combinazioni seguenti:**
- **Scenario 1:** Account utente in Skype for Business locale e utilizzerà il client Skype for Business con VoIP aziendale
- **Scenario 2:** Account utente in Skype for Business online e utilizzerà il client Skype for Business con connettività vocale ibrida
- **Scenario 3:** Account utente in Skype for Business online con licenza Microsoft Teams e utilizzerà il client Teams
 
### <a name="supportability-matrix"></a>Matrice di supporto


|**Oggetto utente creato in**  |**Provider di servizi Skype for Business dell'utente**|**Client dell'utente**|**Opzione voce**|**Supportata**|
| ------------ | --------- | --------- | --------- | -------- |
|Active Directory locale| Locale |Skype for Business   | VoIP aziendale   |Sì|
|Active Directory locale|Online| Skype for Business  | Connettività vocale ibrida   |Sì |
|Active Directory locale|Online |Microsoft Teams |Routing diretto  |Sì |
|**Combinazioni non supportate**    | |         |         |      |
|Azure AD| Locale/online | Skype for Business/Microsoft Teams|VoIP aziendale/Connettività vocale ibrida/Routing diretto  |No, l'oggetto utente DEVE essere prima creato in Active Directory locale |
|Active Directory locale  |Locale| Microsoft Teams| VoIP aziendale/Connettività vocale ibrida/Routing diretto   |No, il client Microsoft Teams non è supportato con Skype for Business locale |     
|Active Directory locale  |Online |Skype for Business  | Routing diretto  |No, l'instradamento diretto non è supportato con il client Skype for Business  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Dichiarazione di supporto per l'ambiente ibrido con PSTN

Per tutti gli utenti, l'oggetto utente deve essere creato in Active Directory locale e sincronizzato con Azure AD usando lo strumento Azure AD Connect.  L'abilitazione degli utenti per Teams/Skype for **Business** non è supportata se l'oggetto utente viene creato direttamente in Azure AD in una configurazione ibrida. Per i nuovi utenti, ad esempio i nuovi assunti, che saranno abilitati direttamente per Teams, l'utente deve essere abilitato per Skype for Business utilizzando gli strumenti di gestione locali di Skype for Business. La creazione di utenti in Skype for Business o Teams online senza prima abilitarli in pool locale VoIP aziendale **non è supportata.** Per ulteriori informazioni, vedere Pianificare il sistema telefonico con connettività [PSTN locale in Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
