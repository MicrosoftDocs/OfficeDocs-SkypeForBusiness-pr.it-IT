---
title: Topologie Skype for business supportate con l'autenticazione moderna
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Questo articolo elenca le topologie online e locali supportate con l'autenticazione moderna in Skype for business, nonché le caratteristiche di sicurezza applicabili a ogni topologia.
ms.openlocfilehash: 2eb043768c46406696b32da5dfb84e2358a30749
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815824"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologie Skype for business supportate con l'autenticazione moderna
 
Questo articolo elenca le topologie online e locali supportate con l'autenticazione moderna in Skype for business, nonché le caratteristiche di sicurezza applicabili a ogni topologia.
  
## <a name="modern-authentication-in-skype-for-business"></a>Autenticazione moderna in Skype for business

Skype for business può sfruttare i vantaggi della sicurezza dell'autenticazione moderna. Poiché Skype for business lavora in stretta collaborazione con Exchange, il comportamento di accesso degli utenti client Skype for business verrà visualizzato anche tramite lo stato MA di Exchange. Questo si applica anche se si ha un ibrido di dominio condiviso Skype for business. Si tratta di un gran numero di parti mobili, ma l'obiettivo qui è un elenco facile da visualizzare delle topologie supportate.
  
In Skype for business, Skype for business online, Exchange Server ed Exchange Online, quali topologie sono supportate con MA?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologie di MA supportate in Skype for business

Esistono potenzialmente due applicazioni server e due carichi di lavoro di Office 365, coinvolti nelle topologie Skype for business usate da MA.
  
- Skype for Business Server (CU 5) in locale
    
- Skype for business online (SFBO)
    
- Exchange Server locale
    
- Exchange Server online (EXO)
    
Un'altra parte importante di MA è sapere dove avverrà l'autenticazione (AuthN) e l'autorizzazione (authZ) degli utenti. Le due opzioni sono:
  
- Azure AD, online in Microsoft Cloud
    
- Active Directory Federation Server (ADFS) locale
    
Sembra quindi un po' come questo, con EXO e SFBO nel cloud con Azure AD e Exchange Server (EXCH) e Skype for Business Server (SFB) on-Prem.
  
![Un esempio di tutte le applicazioni (Exchange e Skype for business) e i carichi di lavoro (EXO e SFBO) e entrambi i server di autorizzazione (ADFS e evoSTS) che possono essere coinvolti durante l'attivazione di MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Ecco le topologie supportate. Tenere presente la chiave per la grafica:
  
- Se l'icona è ombreggiata o grigia, non viene usata nello scenario.
    
- EXO è Exchange Online.
    
- SFBO è Skype for business online.
    
- EXCH è uno scambio locale.
    
- SFB è un locale di Skype for business.
    
- L'autorizzazione dei server è rappresentata da triangoli, ad esempio Azure AD è un triangolo con una nuvola dietro.
    
- Le frecce puntano sul server di autorizzazione che verrà usato quando i client tenteranno di raggiungere la risorsa del server specificata.
    
Prima di tutto, riprendiamo MA con Skype for business in topologie solo locali o solo cloud.
  
> [!IMPORTANT]
> Sei pronto per configurare l'autenticazione moderna in Skype for business online? La procedura per abilitare questa funzionalità è proprio [qui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Nome topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportati  <br/> |
|:-----|:-----|:-----|:-----|
|Solo cloud  <br/> |![SFB supportato con topologia MA, solo cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Utenti ospitati/cassette postali situate: online  <br/> |MA è attiva sia per EXO che per SFBO.  <br/> Di conseguenza, il server di autorizzazione è Azure AD.  <br/> |Autenticazione a più fattori (AMF), autenticazione basata su certificato client (CBA), accesso condizionale (CA)/Mobile Application Management (MAM) con Intune. \*  <br/> |
|Solo on-Prem  <br/> |![SFB supportato con topologia MA, solo locale.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Utenti ospitati/cassette postali presenti: locale  <br/> |MA è attivato per SFB locale.  <br/> Di conseguenza, il server di autorizzazione è ADFS.  <br/> Per informazioni dettagliate sulla configurazione, vedere [questo articolo.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |AMF (solo desktop di Windows-i client mobili non sono supportati). Nessuna funzionalità di integrazione di Exchange.  <br/><p> **Questo approccio non è consigliabile. Vedere qui:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> È consigliabile che lo stato MA sia lo stesso in Skype for business e Exchange (e le rispettive controparti online) per ridurre il numero di richieste. 
  
Le topologie miste coinvolgono le combinazioni degli ibridi di SFB Split-Domain. Queste sono le topologie miste attualmente supportate:
  
|Nome topologia  <br/> |Esempio  <br/> |Descrizione  <br/> |Supportati  <br/> |
|:-----|:-----|:-----|:-----|
|Mixed 1  <br/> |![SFB supportato con topologia MA mista 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Utenti ospitati/cassette postali situate: EXO e SFB  <br/> |MA non è abilitato per SFB; Nessuna funzionalità di SFB MA disponibile in questa topologia.  <br/> |Nessuna funzionalità MA per SFB.  <br/> |
|Misto 2  <br/> |![MA supportato con la topologia mista S4B 2, SFBO Plus MA che lavora con EXCH on-Prem.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Utenti ospitati/cassette postali situate: EXCH e SFBO  <br/> |MA è attiva solo per SFBO. Il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO, ma AD per EXCH locale.  <br/> |AMF, CBA, CA/MAM con Intune.\*  <br/> |
|Mixed 3  <br/> |![Supportato MA con SFB, EXO con MA on, più EXCH e SFB in locale.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Utenti ospitati/cassette postali situate: EXO + SFB o EXCH + SFB  <br/> |Nessuna funzionalità di SFB MA disponibile in questa topologia  <br/> |Nessuna funzionalità MA per SFB.  <br/> |
|Misto 4  <br/> |![MA supportato con SFB, SFBO con MA in, più EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Utenti ospitati/cassette postali situate: EXCH + SFBO o EXCH + SFB  <br/> |MA è attivato per SFBO, quindi il server di autorizzazione è Azure AD per gli utenti ospitati in SFBO. Gli utenti di on-Prem in SFB e EXO usano Active Directory.  <br/> |AMF, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Mixed 5  <br/> |![MA supportati in SFB, EXO con MA e SFBO con MA e EXCH e SFB in locale.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Utenti ospitati/cassette postali situate: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA è attiva sia in EXO che in SFBO, quindi il server di autorizzazione è Azure AD per gli utenti residenti in SFBO; Gli utenti di on-Prem in EXCH e SFB usano Active Directory.  <br/> |AMF, CBA, CA/MAM con Intune solo per gli utenti online.\*  <br/> |
|Misto 6  <br/> |![In una topologia mista 6 l'autenticazione moderna è attiva in tutte e quattro le posizioni possibili: la situazione ideale quando si parla di auth moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Utenti ospitati/cassette postali situate: EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB  <br/> |MA è ovunque, quindi il server di autorizzazione è Azure AD per tutti gli utenti. (online e in locale)  <br/>  Vedere [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) la procedura per la distribuzione. <br/> |AMF, CBA e CA/MAM (via Intune) per tutti gli utenti.  <br/> |
   
\*-L'AMF include Windows desktop, MAC, iOS, dispositivi Android e telefoni Windows; CBA include dispositivi desktop, iOS e Android di Windows; CA/MAM con Intune include dispositivi Android e iOS. 
  
> [!IMPORTANT]
> È molto importante notare che gli utenti possono visualizzare **più richieste** in alcuni casi, in particolare quando lo stato ma non è lo stesso in tutte le risorse del server che i client possono richiedere e richiedono, come nel caso di tutte le versioni delle topologie miste.

> [!IMPORTANT]
> Si noti inoltre che in alcuni casi (in particolare 1, 3 e 5 misti) è necessario impostare una chiave del registro di sistema [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) per la configurazione appropriata per i client desktop di Windows.
  

