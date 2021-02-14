---
title: Pianificare le distribuzioni dei server perimetrali in Skype for Business Server
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
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: "Riepilogo: pianificare l'ambiente Skype for Business Server Edge. Questo argomento presenta i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi."
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813806"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Pianificare le distribuzioni dei server perimetrali in Skype for Business Server
 
**Riepilogo:** Pianificare l'ambiente Edge di Skype for Business Server. Questo argomento presenta i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.
  
Quando si dispone di un ambiente Skype for Business Server che funziona correttamente internamente, il passaggio successivo potrebbe consistere nell'introdurre un server perimetrale o un pool di server perimetrali nell'ambiente. Questo ruolo sarebbe fondamentale se vuoi che i servizi forniti da Skype for Business Server siano usati da persone esterne alla rete interna. Questi possono potenzialmente includere:
  
- Utenti remoti: dipendenti che sono fuori sede, temporaneamente o in modo continuamente.
    
- Utenti federati: dipendenti delle organizzazioni partner.
    
- Utenti mobili.
    
- Potenziali clienti, partner e persino utenti anonimi che si desidera invitare a riunioni e presentazioni.
    
L'accesso degli utenti esterni, che è quello fornito dal server perimetrale, consente tutto questo. Gli utenti interni potranno usufruire dei servizi seguenti ospitati dalla distribuzione di Skype for Business Server:
  
- Messaggistica istantanea e presenza per le comunicazioni: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea. Possono ottenere informazioni sulla presenza per altri utenti (che ottengono anche le informazioni sulla presenza). Non sarà possibile effettuare conferenze tra più partecipanti se si utilizza un provider di messaggistica istantanea pubblico, si tratta esclusivamente di comunicazioni peer-to-peer. Tuttavia, sono supportati entrambi i protocolli SIP e XMPP.
    
- Audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.
    
- Conferenze Web: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for Business. È inoltre possibile abilitare la partecipazione per utenti remoti, federati e anonimi, se lo si desidera. Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. Sono inoltre disponibili opzioni per consentire a questi utenti di partecipare alla condivisione di applicazioni e desktop e di agire anche come organizzatori o relatori della riunione.
    
L'accesso ai dispositivi mobili è supportato, così come VoIP aziendale. È possibile invitare utenti esterni a tali riunioni a cui si desidera che partecipino, anche a utenti anonimi, se si desidera concedere loro le autorizzazioni.
  
Se si tratta di un'operazione di cui l'organizzazione ha bisogno, la pianificazione di un ambiente perimetrale sarà un grande aiuto per la distribuzione. Per altre letture, abbiamo gli argomenti elencati di seguito.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 
  
## <a name="planning-topics"></a>Argomenti relativi alla pianificazione:

Gli articoli relativi alla pianificazione sono:
  
- [Requisiti di sistema dei server perimetrali in Skype for Business Server](system-requirements.md)
    
- [Requisiti ambientali dei server perimetrali in Skype for Business Server](edge-environmental-requirements.md)
    
- [Scenari di server perimetrali in Skype for Business Server 2015](scenarios.md)
    

