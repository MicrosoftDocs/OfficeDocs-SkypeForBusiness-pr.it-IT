---
title: Account utente in un ambiente ibrido con connettività PSTN
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
description: Informazioni sulle diverse combinazioni di creazione degli utenti e sulle combinazioni supportate o non consolidate.
ms.openlocfilehash: f33c7bffadb443aafad6fa0e7d910f6416a95d6f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837286"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Account utente in un ambiente ibrido con connettività PSTN

## <a name="about-the-environment"></a>Informazioni sull'ambiente

Questo articolo si applica agli ambienti in cui sono presenti tutte le operazioni seguenti: 
 
- Skype for Business Server o Lync Server 2013 
- Un tenant di Office 365 
- Connettività ibrida configurata tra il tenant di Skype for Business Server e Skype for business online o Microsoft Teams 
- Utenti abilitati a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) da e verso il client

 
Se si ha un ambiente diverso (ad esempio Skype for Business Cloud Connector Edition), Hybrid non è configurato o gli utenti non sono abilitati per le chiamate PSTN, la matrice di supporto sarà diversa.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informazioni sulle combinazioni e sull'istruzione di supporto  

Un ambiente ibrido di Skype for business con connettività PSTN offre flessibilità per quanto riguarda la posizione dei servizi utente e il provisioning e la gestione degli account utente. Ma l'abbondanza di opzioni potrebbe creare alcune combinazioni non supportate. In questa sezione vengono illustrate diverse combinazioni di creazione degli utenti, seguite da un'istruzione di supporto.


**Definizioni**   
- **Enterprise Voice:** Opzione per consentire l'accesso a PSTN per gli utenti con account utente Skype for business locale. Il Mediation Server Skype for business in locale offre l'interconnettività alla rete PSTN.  
- **Connettività vocale ibrida:** Opzione per consentire l'accesso a PSTN per gli utenti con account Skype for business online. Il Mediation Server Skype for business in locale offre l'interconnettività alla rete PSTN. 
- **Routing diretto:** Opzione per consentire l'accesso a PSTN per gli utenti con account Skype for business online, licenza Microsoft teams, con il client Microsoft teams. SBC è connesso al proxy SIP in Office 365 senza bisogno di alcun software locale da Microsoft.

  
**L'ambiente supporta le combinazioni seguenti:**
- **Scenario 1:** Account utente in Skype for business locale e userà il client Skype for business con VoIP aziendale
- **Scenario 2:** Account utente in Skype for business online e userà il client Skype for business con connettività vocale ibrida
- **Scenario 3:** Account utente in Skype for business online con licenza Microsoft teams e userà client Teams
 
### <a name="supportability-matrix"></a>Matrice di supporto


|**Oggetto utente creato in**  |**Provider di servizi Skype for business dell'utente**|**Client dell'utente**|**Opzione voce**|**Supportati**|
| ------------ | --------- | --------- | --------- | -------- |
|ANNUNCIO locale| Locale |Skype for business   | VoIP aziendale   |Sì|
|ANNUNCIO locale|Online| Skype for business  | Connettività vocale ibrida   |Sì |
|ANNUNCIO locale|Online |Microsoft Teams |Routing diretto  |Sì |
|**Combinazioni non supportate**    | |         |         |      |
|Azure AD| Locale/online | Skype for Business/Microsoft Teams|VoIP aziendale/connettività vocale ibrida/routing diretto  |No, l'oggetto utente deve essere creato prima in un annuncio locale |
|ANNUNCIO locale  |Locale| Microsoft Teams| VoIP aziendale/connettività vocale ibrida/routing diretto   |No, il client Microsoft teams non è supportato con Skype for business locale |     
|ANNUNCIO locale  |Online |Skype for business  | Routing diretto  |No, il routing diretto non è supportato con il client Skype for business e l'utente deve essere abilitato per VoIP aziendale in Skype for business per primo  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Istruzione di supporto per l'ambiente ibrido con PSTN

Per tutti gli utenti, è **necessario** creare l'oggetto utente nell'annuncio locale e sincronizzarlo con Azure ad usando lo strumento Azure ad Connect. L'abilitazione degli utenti per Teams/Skype for business **non è supportata** se l'oggetto utente viene creato direttamente in Azure ad in una configurazione ibrida. Per i nuovi utenti, ad esempio un nuovo noleggio, che verranno abilitati direttamente per i team, l'utente deve essere abilitato per Skype for business usando gli strumenti di gestione di Skype for business locali. La creazione di utenti in Skype for business online o in teams senza prima averli abilitati in pool locale con Enterprise Voice **non è supportata**. Per altre informazioni, vedere [sistema telefono piano in Office 365 con connettività PSTN locale in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
