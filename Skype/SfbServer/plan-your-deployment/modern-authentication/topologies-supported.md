---
title: Topologie di Skype for Business supportate per l'autenticazione moderna
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: In questo articolo sono elencate le topologie online e locali supportate con l'autenticazione moderna in Skype for business, nonché le funzionalità di sicurezza che si applicano a ogni topologia.
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810105"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologie di Skype for Business supportate per l'autenticazione moderna

In questo articolo sono elencate le topologie online e locali supportate con l'autenticazione moderna in Skype for business, nonché le funzionalità di sicurezza che si applicano a ogni topologia.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticazione moderna in Skype for business

Skype for business è in grado di sfruttare i vantaggi di sicurezza dell'autenticazione moderna. Poiché Skype for business è compatibile con Exchange, gli utenti di client Skype for business per il comportamento di accesso verranno visualizzati anche per lo stato MA di Exchange. Questo si applica anche se si dispone di un ibrido Split-Domain di Skype for business. Si tratta di molte parti mobili, ma l'obiettivo è un elenco di topologie supportate di facile visualizzazione.

Dato Skype for business, Skype for business online, Exchange Server ed Exchange Online, quali topologie sono supportate con MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologie di MA supportate in Skype for business

Esistono potenzialmente due applicazioni server e due carichi di lavoro Microsoft 365 o Office 365, coinvolti nelle topologie Skype for business utilizzate da MA.

- Skype for Business Server (CU 5) in locale

- Skype for business online (SFBO)

- Exchange Server locale

- Exchange Server online (EXO)

Un'altra parte importante di MA è sapere dove avrà luogo l'autenticazione (AuthN) e l'autorizzazione (authZ) degli utenti. Le due opzioni sono le seguenti:

- Azure AD, online nel cloud Microsoft

- Server federativo Active Directory (ADFS) in locale

Così sembra un po' come questo, con EXO e SFBO nel cloud con Azure AD, e Exchange Server (EXCH) e Skype for Business Server (questo) on-Prem.

![Un esempio di tutte le applicazioni (Exchange e Skype for business) e dei carichi di lavoro (EXO e SFBO) e di entrambi i server di autorizzazione (ADFS e evoSTS) che possono essere coinvolti durante l'attivazione di MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Di seguito sono ritrovate le topologie supportate. Tenere presente la chiave per gli elementi grafici:

- Se l'icona è in grigio o grigia, non viene utilizzata nello scenario.

- EXO è Exchange Online.

- SFBO è Skype for business online.

- EXCH è Exchange locale.

- Questo è Skype for business locale.

- L'autorizzazione dei server è rappresentata da triangoli, ad esempio, l'Azure AD è un triangolo con un cloud sottostante.

- Le frecce puntano sul server di autorizzazione che verrà utilizzato quando i client tentano di raggiungere la risorsa server specificata.

Per prima cosa, è possibile coprire MA con Skype for business sia nelle topologie solo locali che in quelle solo cloud.

> [!IMPORTANT]
> Sei pronto per configurare l'autenticazione moderna in Skype for business online? La procedura per abilitare questa funzionalità è proprio [qui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Nome della topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportato  <br/> |
|:-----|:-----|:-----|:-----|
|Solo cloud  <br/> |![QUESTO supportato con topologia MA, solo cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utenti ospitati/cassette postali che si trovano: online  <br/> |MA è attiva sia per EXO che per SFBO.  <br/> Di conseguenza, il server di autorizzazione è Azure AD.  <br/> |Autenticazione a più fattori (AMF), autenticazione basata su certificato client (CBA), accesso condizionale (CA)/Mobile Application Management (MAM) con Intune. \*  <br/> |
|Solo on-Prem  <br/> |![Questo supportata con la topologia di MA, solo in locale.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utenti ospitati/cassette postali che si trovano: locale  <br/> |MA è attiva per questo in locale.  <br/> Di conseguenza, il server di autorizzazione è ADFS.  <br/> Per informazioni dettagliate sulla configurazione, vedere [questo articolo.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |AMF (solo desktop di Windows-i client mobili non sono supportati). Nessuna funzionalità di integrazione di Exchange.  <br/><p> **Questo approccio non è consigliato. Vedere qui:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> È consigliabile che lo stato di MA sia lo stesso tra Skype for business e Exchange (e le loro controparti online) per ridurre il numero di richieste.

Le topologie miste coinvolgono combinazioni di ibridi di questo Split-Domain. Queste sono le topologie miste attualmente supportate:

|Nome della topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportato  <br/> |
|:-----|:-----|:-----|:-----|
|Misto 1  <br/> |![QUESTO supportato con topologia MA, misto 1 (EXO + questo).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utenti ospitati/cassette postali che si trovano: EXO e questo  <br/> |MA non è abilitato per questo; Nessuna funzionalità di questo MA disponibile in questa topologia.  <br/> |Nessuna funzionalità di MA per questo.  <br/> |
|Misto 2  <br/> |![MA supportato con topologia mista S4B 2, SFBO Plus MA che lavora con EXCH on-Prem.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utenti ospitati/cassette postali che si trovano: EXCH e SFBO  <br/> |MA è attiva solo per SFBO. Il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO, ma AD per EXCH locale.  <br/> |AMF, CBA, CA/MAM con Intune.\*  <br/> |
|Misto 3  <br/> |![Supporto di MA con questo, EXO con MA on, oltre a EXCH e questo in locale.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utenti ospitati/cassette postali che si trovano: EXO + questo, o EXCH + questo  <br/> |Nessuna funzionalità di questo MA disponibile in questa topologia  <br/> |Nessuna funzionalità di MA per questo.  <br/> |
|Misto 4  <br/> |![MA supportato con questo, SFBO con MA su, più EXCH e questo.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utenti ospitati/cassette postali che si trovano: EXCH + SFBO o EXCH + questo  <br/> |MA è attiva per SFBO, pertanto il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO. Gli utenti di questo e EXO usano Active Directory.  <br/> |Solo AMF, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Misto 5  <br/> |![MA supportato in questo, EXO con MA e SFBO con MA, e EXCH e questo in locale.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utenti ospitati/cassette postali che si trovano: EXO + SFBO, EXO + questo, EXCH + SFBO o EXCH + questo  <br/> |MA è attiva sia in EXO che in SFBO, pertanto il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO; Gli utenti di on-Prem in EXCH e questo utilizzano Active Directory.  <br/> |Solo AMF, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Misto 6  <br/> |![In una topologia mista 6, l'autenticazione moderna è attiva in tutte e quattro le posizioni possibili: la situazione ideale quando si tratta di un'autorizzazione moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utenti ospitati/cassette postali che si trovano: EXO + SFBO, EXO + questo, EXCH + SFBO o EXCH + questo  <br/> |MA è su Everywhere, quindi il server di autorizzazione è Azure AD per tutti gli utenti. (online e in locale)  <br/>  Per ulteriori informazioni [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) , vedere per la procedura di distribuzione. <br/> |Mae, CBA e CA/MAM (tramite Intune) per tutti gli utenti.  <br/> |

\* -AMF include Windows desktop, MAC, iOS, dispositivi Android e telefoni Windows; CBA include i dispositivi desktop, iOS e Android di Windows; CA/MAM con Intune, include dispositivi Android e iOS.

> [!IMPORTANT]
> È molto importante tenere presente che gli utenti possono visualizzare **più istruzioni** in alcuni casi, in particolare se lo stato di ma non è lo stesso in tutte le risorse del server che i client possono richiedere e richiedono, come nel caso di tutte le versioni delle topologie miste.

> [!IMPORTANT]
> Si noti inoltre che, in alcuni casi (misti 1, 3 e 5 in particolare), è necessario impostare una chiave del registro di sistema di [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) per la corretta configurazione dei client desktop di Windows.


