---
title: Account utente in ambiente ibrido con PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Informazioni sulle diverse combinazioni di creazione utente e sulle combinazioni supportate o non supportate.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676418"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Account utente in un ambiente ibrido con connettività PSTN

## <a name="about-the-environment"></a>Informazioni sull'ambiente

Questo articolo si applica agli ambienti in cui sono presenti tutti gli elementi seguenti:

- Skype for Business Server o Lync Server 2013
- Un Microsoft 365 o un'organizzazione Office 365
- Connettività ibrida configurata tra Skype for Business Server e Skype for Business online o Microsoft Teams tenant
- Utenti abilitati a effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) da e verso il client


Se si ha un ambiente diverso, ad esempio Skype for Business Cloud Connector Edition, la distribuzione ibrida non è configurata o gli utenti non sono abilitati per le chiamate PSTN, la matrice di supporto sarà diversa.

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informazioni sulle combinazioni e sull'istruzione di supporto

Un ambiente ibrido Skype for Business con connettività PSTN offre flessibilità per quanto riguarda la posizione in cui vengono forniti i servizi utente e le modalità di provisioning e gestione degli account utente. Ma l'abbondanza di opzioni potrebbe creare alcune combinazioni non supportate. Questa sezione illustra le diverse combinazioni di creazione utente, seguite da una dichiarazione di supporto.

**Definizioni:**

- **VoIP aziendale:** opzione per fornire l'accesso a PSTN per gli utenti con account utente Skype for Business locale. L'Skype for Business Mediation Server locale garantisce l'interconnettività con PSTN.
- **Connettività vocale ibrida:** Opzione per fornire l'accesso a PSTN per gli utenti con Skype for Business account online. L'Skype for Business Mediation Server locale garantisce l'interconnettività con PSTN.
- **Routing diretto:** Opzione per fornire l'accesso a PSTN per gli utenti con account di Skype for Business online, Microsoft Teams licenza, utilizzando Microsoft Teams client. SBC è connesso al proxy SIP in Microsoft 365 o Office 365 senza la necessità di software locale di Microsoft.

**L'ambiente supporta le combinazioni seguenti:**

- **Scenario 1:** Account utente in Skype for Business locale e userà il client Skype for Business con VoIP aziendale
- **Scenario 2:** Account utente in Skype per le aziende online e userà il client Skype for Business con connettività vocale ibrida
- **Scenario 3:** Account utente in Skype for Business online con licenza di Microsoft Teams e userà Teams client

### <a name="supportability-matrix"></a>Matrice di supporto

|Oggetto utente creato in|Provider di servizi Skype for Business dell'utente|Client dell'utente|Opzione Voce|Supportati|
|---|---|---|---|---|
|Active Directory locale|In locale|Skype for Business|VoIP aziendale|Sì|
|Active Directory locale|Online|Skype for Business|Connettività vocale ibrida|Sì|
|Active Directory locale|Online|Microsoft Teams|Routing diretto|Sì|
|**Combinazioni non supportate**|||||
|Azure AD|Locale/online|Skype for Business/Microsoft Teams|VoIP aziendale/Connettività vocale ibrida/Routing diretto|No, l'oggetto utente DEVE essere prima creato in Active Directory locale|
|Active Directory locale|In locale|Microsoft Teams|VoIP aziendale/Connettività vocale ibrida/Routing diretto|No, Microsoft Teams client non è supportato con Skype for Business locale|
|Active Directory locale|Online|Skype for Business|Routing diretto|No, il routing diretto non è supportato con Skype for Business client|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Istruzione di supporto per l'ambiente ibrido con PSTN

Per tutti gli utenti, l'oggetto utente **deve** essere creato in Active Directory locale e sincronizzato con Azure AD usando lo strumento di Connessione di Azure AD. L'abilitazione degli utenti per Teams/Skype for Business **non è supportata** se l'oggetto utente viene creato direttamente in Azure AD in una configurazione ibrida. Per i nuovi utenti, ad esempio i nuovi assunti, che verranno abilitati direttamente per Teams, l'utente deve essere abilitato per Skype for Business usando gli strumenti di gestione Skype for Business locali. La creazione di utenti in Skype for Business o Teams online senza prima abilitarli nel pool locale con VoIP aziendale **non è supportata**. Per altre informazioni, vedere [Pianificare Sistema telefonico con la connettività PSTN locale in Skype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
