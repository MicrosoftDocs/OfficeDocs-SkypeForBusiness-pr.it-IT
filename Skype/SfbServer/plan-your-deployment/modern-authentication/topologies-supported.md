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
description: In questo articolo sono elencate le topologie online e locali supportate con l'autenticazione moderna in Skype for Business, nonché le funzionalità di sicurezza che si applicano a ogni topologia.
ms.openlocfilehash: 759ee11a4cd6828d65b45a713f50bb8b32856a4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116064"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologie di Skype for Business supportate per l'autenticazione moderna

In questo articolo sono elencate le topologie online e locali supportate con l'autenticazione moderna in Skype for Business, nonché le funzionalità di sicurezza che si applicano a ogni topologia.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticazione moderna in Skype for Business

Skype for Business può sfruttare i vantaggi della sicurezza dell'autenticazione moderna. Poiché Skype for Business funziona a stretto contatto con Exchange, il comportamento di accesso che gli utenti del client Skype for Business potranno vedere saranno influenzati anche dallo stato ma di Exchange. Ciò si applica anche se si dispone di un ambiente ibrido con dominio diviso di Skype for Business. Si tratta di molte parti in movimento, ma l'obiettivo qui è visualizzare facilmente un elenco delle topologie supportate.

Date Skype for Business, Skype for Business online, Exchange Server ed Exchange online, quali topologie sono supportate con MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologie ma supportate in Skype for Business

Esistono potenzialmente due applicazioni server e due carichi di lavoro di Microsoft 365 o Office 365, coinvolti nelle topologie di Skype for Business usate da MA.

- Skype for Business Server (CU 5) locale

- Skype for Business online (SFBO)

- Server Exchange locale

- Exchange Server online (EXO)

Un'altra parte importante di MA è sapere dove avrà luogo l'autenticazione (authN) e l'autorizzazione (authZ) degli utenti. Le due opzioni sono:

- Azure AD, online in the Microsoft Cloud

- Active Directory Federation Server (ADFS) locale

Questo aspetto è simile al seguente, con EXO e SFBO nel cloud con Azure AD e Exchange Server (EXCH) e Skype for Business server (SFB) in locale.

![Un esempio di tutte le applicazioni (Exchange e Skype for Business) e i carichi di lavoro (EXO e SFBO) ed entrambi i server di autorizzazione (ADFS ed evoSTS) che possono essere coinvolti quando si attiva MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Ecco le topologie supportate. Tieni presente la chiave per la grafica:

- Se l'icona è in grigio o in grigio, non viene utilizzata nello scenario.

- EXO è Exchange Online.

- SFBO è Skype for Business online.

- EXCH è Exchange locale.

- SFB è Skype for Business locale.

- I server di autorizzazione sono rappresentati da triangoli, ad esempio, Azure AD è un triangolo con un cloud dietro di esso.

- Le frecce puntano al server di autorizzazione che verrà utilizzato quando i client tentano di raggiungere la risorsa server specificata.

Prima di tutto, esamini ma con Skype for Business sia in topologie locali che solo cloud.

> [!IMPORTANT]
> Sei pronto per configurare l'autenticazione moderna in Skype for Business online? I passaggi per abilitare questa funzionalità sono [qui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Nome topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportato  <br/> |
|:-----|:-----|:-----|:-----|
|Solo cloud  <br/> |![SfB supportato con topologia ma, solo cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utenti ospitati/cassette postali: online  <br/> |MA è disponibile sia per EXO che per SFBO.  <br/> Di conseguenza, il server di autorizzazione è Azure AD.  <br/> |Autenticazione a più fattori (MFA), Autenticazione basata su certificato client (CBA), Accesso condizionale (CA)/Gestione applicazioni mobili (MAM) con Intune. \*  <br/> |
|Solo in base all'utente  <br/> |![SfB supportato con topologia MA, solo locale.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utenti ospitati/cassette postali situati: locale  <br/> |Ma è per SFB locale.  <br/> Di conseguenza, il server di autorizzazione è ADFS.  <br/> Per informazioni dettagliate sulla configurazione, vedere [questo articolo.](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (solo Desktop di Windows: i client mobili non sono supportati). Nessuna funzionalità di integrazione di Exchange.  <br/><p> **Questo approccio non è consigliato. Vedere qui:**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> Per ridurre il numero di richieste, è consigliabile che lo stato ma sia lo stesso in Skype for Business ed Exchange (e nelle rispettive controparti online).

Le topologie miste implicano combinazioni di ibridi con dominio diviso SFB. Di seguito sono descritte le topologie miste attualmente supportate:

|Nome topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportato  <br/> |
|:-----|:-----|:-----|:-----|
|Misto 1  <br/> |![SfB supportato con topologia MA, misto 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utenti ospitati/cassette postali situati: EXO e SFB  <br/> |Ma non è abilitato per SFB; nessuna funzionalità di GESTIONE SFB disponibile in questa topologia.  <br/> |Nessuna funzionalità di gestione per SFB.  <br/> |
|Misto 2  <br/> |![Ma supportato con topologia mista S4B 2, SFBO e MA che lavorano con EXCH in modalità prem.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utenti ospitati/cassette postali situati: EXCH e SFBO  <br/> |Ma è solo per SFBO. Il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO, ma AD per EXCH locale.  <br/> |MFA, CBA, CA/MAM con Intune.\*  <br/> |
|Misto 3  <br/> |![Ma supportato con SFB, EXO con MA on, oltre a EXCH e SFB in locale.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utenti ospitati/cassette postali situati: EXO + SFB o EXCH + SFB  <br/> |Nessuna funzionalità di GESTIONE SFB disponibile in questa topologia  <br/> |Nessuna funzionalità di gestione per SFB.  <br/> |
|Misto 4  <br/> |![Ma supportato con SFB, SFBO con MA on, oltre a EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utenti ospitati/cassette postali situati: EXCH +SFBO o EXCH + SFB  <br/> |Ma è per SFBO, quindi il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO. Gli utenti locali in SFB ed EXO utilizzano AD.  <br/> |MFA, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Misto 5  <br/> |![Ma supportato in SFB, EXO con MA e SFBO con MA e EXCH e SFB in locale.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utenti ospitati/cassette postali situati: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |Ma è in esecuzione sia in EXO che in SFBO, pertanto il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO; Gli utenti locali in EXCH e SFB usano AD.  <br/> |MFA, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Misto 6  <br/> |![In una topologia Mixed 6, l'autenticazione moderna è attiva in tutte e quattro le posizioni, la situtation ideale per l'autenticazione moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utenti ospitati/cassette postali situati: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |Ma è ovunque, quindi il server di autorizzazione è Azure AD per tutti gli utenti. (online e locale)  <br/>  Vedere la [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) procedura di distribuzione. <br/> |MFA, CBA e CA/MAM (tramite Intune) per tutti gli utenti.  <br/> |

\* - MFA include Windows Desktop, MAC, iOS, dispositivi Android e Windows Phone; CBA include dispositivi Windows Desktop, iOS e Android; CA/MAM con Intune, include dispositivi Android e iOS.

> [!IMPORTANT]
> È molto importante notare che gli utenti possono visualizzare più richieste **in** alcuni casi, in particolare quando lo stato di Ma non è lo stesso per tutte le risorse del server che potrebbero essere necessarie e richieste dai client, come nel caso di tutte le versioni delle topologie miste.

> [!IMPORTANT]
> Si noti inoltre che in alcuni casi (mixed 1, 3 e 5 in particolare) è necessario impostare una chiave del Registro di sistema [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) per la configurazione appropriata per i client Desktop Windows.