---
title: Pianificare le distribuzioni di server perimetrali in Skype for Business Server
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
description: "Riepilogo: pianificare l'ambiente Edge di Skype for Business Server. In questo argomento vengono illustrati i concetti di Edge e vengono organizzati gli argomenti più approfonditi."
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813806"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Pianificare le distribuzioni di server perimetrali in Skype for Business Server
 
**Riepilogo:** Pianificare l'ambiente Edge di Skype for Business Server. In questo argomento vengono illustrati i concetti di Edge e vengono organizzati gli argomenti più approfonditi.
  
Quando si dispone di un ambiente Skype for Business Server che funziona bene internamente, il passaggio successivo potrebbe essere quello di introdurre un server perimetrale o un pool perimetrale nell'ambiente. Questo ruolo sarebbe essenziale se si desidera che i servizi forniti da Skype for Business Server siano utilizzati da utenti esterni alla rete interna. Questi possono potenzialmente includere:
  
- Utenti remoti: dipendenti che sono fuori sede, temporaneamente o in modalità continua.
    
- Utenti federati: dipendenti delle organizzazioni partner.
    
- Utenti mobili.
    
- Potenziali clienti, partner e persino utenti anonimi che si desidera invitare a riunioni e presentazioni.
    
L'accesso degli utenti esterni, ovvero la fornitura dei server perimetrali, consente di eseguire tutte le operazioni. Gli utenti interni saranno in grado di usufruire dei seguenti servizi ospitati dalla distribuzione di Skype for Business Server:
  
- Messaggistica istantanea e presenza per la comunicazione: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea. Sono in grado di ottenere informazioni sulla presenza per gli altri utenti (che ricevono anche informazioni sulla presenza). Se si utilizza un provider di messaggistica istantanea pubblico, la comunicazione peer-to-peer non sarà in grado di eseguire conferenze con più partecipanti. Tuttavia, entrambi i protocolli SIP e XMPP sono supportati.
    
- Servizi di conferenza audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.
    
- Web Conferencing: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for business. Se lo si desidera, è anche possibile abilitare la partecipazione per gli utenti remoti, gli utenti federati e gli utenti anonimi. Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. Sono inoltre disponibili opzioni che consentono agli utenti di partecipare alla condivisione di applicazioni e desktop e di agire anche come organizzatori di riunioni o relatori.
    
L'accesso ai dispositivi mobili è supportato, come VoIP aziendale. È possibile invitare gli utenti esterni a quelle riunioni a cui si desidera partecipare, anche gli utenti anonimi, se si desidera concedere loro autorizzazioni.
  
Se si tratta di una cosa che l'organizzazione ha bisogno, la pianificazione di un ambiente Edge sarà di grande aiuto per la distribuzione. Per ulteriori informazioni, sono disponibili gli argomenti elencati di seguito.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019. Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Argomenti relativi alla pianificazione:

Gli articoli di pianificazione sono:
  
- [Requisiti di sistema per i server perimetrali in Skype for Business Server 2015](system-requirements.md)
    
- [Requisiti ambientali dei server perimetrali in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Scenari del server perimetrale in Skype for Business Server 2015](scenarios.md)
    

