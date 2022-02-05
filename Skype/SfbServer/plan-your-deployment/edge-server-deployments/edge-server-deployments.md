---
title: Pianificare le distribuzioni dei server perimetrali in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Riepilogo: pianificare l''ambiente Skype for Business Server Edge. Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.'
---

# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Pianificare le distribuzioni dei server perimetrali in Skype for Business Server
 
**Riepilogo:** Pianificare l'ambiente Skype for Business Server Edge. Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.
  
Quando si dispone di un Skype for Business Server che funziona correttamente internamente, il passaggio successivo potrebbe consistere nell'introdurre un server perimetrale o un pool di server perimetrali nell'ambiente. Questo ruolo è fondamentale se si desidera che i servizi forniti da Skype for Business Server siano utilizzati da utenti esterni alla rete interna. Questi possono potenzialmente includere:
  
- Utenti remoti: dipendenti che sono fuori sede, temporaneamente o in modo continuo.
    
- Utenti federati: dipendenti delle organizzazioni partner.
    
- Utenti mobili.
    
- Potenziali clienti, partner e persino utenti anonimi che si desidera invitare a riunioni e presentazioni.
    
L'accesso utente esterno, che è quello fornito da server perimetrali, consente tutto questo. Gli utenti interni potranno usufruire dei servizi seguenti ospitati dalla Skype for Business Server distribuzione:
  
- Messaggistica istantanea e presenza per le comunicazioni: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea. Possono ottenere informazioni sulla presenza per altri utenti (che ottengono anche le informazioni sulla presenza). Non sarà possibile eseguire conferenze tra più partecipanti se si utilizza un provider di messaggistica istantanea pubblico, si tratta di una comunicazione strettamente peer-to-peer. Tuttavia, sono supportati entrambi i protocolli SIP e XMPP.
    
- Conferenze audio/video ( A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video Skype for Business Server video.
    
- Conferenze Web: gli utenti esterni autorizzati possono partecipare alle conferenze Skype for Business aziendali. Se si desidera, è inoltre possibile abilitare la partecipazione per utenti remoti, utenti federati e utenti anonimi. Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. Esistono anche opzioni per consentire a questi utenti di partecipare alla condivisione di applicazioni e desktop e anche di agire come organizzatori o relatori di riunioni.
    
L'accesso ai dispositivi mobili è supportato, come VoIP aziendale. È possibile invitare utenti esterni a tali riunioni a cui si desidera partecipare, anche utenti anonimi, se si desidera concedere loro le autorizzazioni.
  
Se si tratta di un'operazione di cui l'organizzazione ha bisogno, la pianificazione di un ambiente Edge sarà un grande aiuto per la distribuzione. Per ulteriori letture, di seguito sono elencati gli argomenti.

> [!NOTE]
> I gateway XMPP e i proxy sono disponibili Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Argomenti relativi alla pianificazione:

Gli articoli sulla pianificazione sono:
  
- [Requisiti di sistema dei server perimetrali in Skype for Business Server 2015](system-requirements.md)
    
- [Requisiti ambientali dei server perimetrali in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Scenari di server perimetrali in Skype for Business Server 2015](scenarios.md)
    

