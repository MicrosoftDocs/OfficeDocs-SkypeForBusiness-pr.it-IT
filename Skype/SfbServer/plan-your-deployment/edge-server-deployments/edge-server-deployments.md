---
title: Pianificare le distribuzioni di Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: "Riepilogo: pianificare l'ambiente di Skype for Business Server Edge. Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi."
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187814"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Pianificare le distribuzioni di Edge Server in Skype for Business Server
 
**Riepilogo:** Pianificare l'ambiente di Skype for Business Server Edge. Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.
  
Quando si ha un ambiente di Skype for Business Server che funziona bene internamente, il passaggio successivo potrebbe essere l'introduzione di un Edge Server o di un pool di Edge nell'ambiente. Questo ruolo sarebbe essenziale se si vuole che i servizi forniti da Skype for Business Server vengano usati dagli utenti esterni alla rete interna. Questi possono includere potenzialmente:
  
- Utenti remoti: i dipendenti che sono fuori sede, temporaneamente o in modo continuo.
    
- Utenti federati: dipendenti delle organizzazioni partner.
    
- Utenti mobili.
    
- Potenziali clienti, partner e persino utenti anonimi che si vogliono invitare a riunioni e presentazioni.
    
L'accesso degli utenti esterni, che è quello che offre Edge Server, consente di ottenere tutto questo. Gli utenti interni potranno usufruire dei servizi seguenti ospitati dalla distribuzione di Skype for Business Server:
  
- Messaggistica istantanea e presenza per la comunicazione: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea. Possono ottenere informazioni sulla presenza per altri utenti (che ricevono anche le informazioni sulla presenza). Non sarà possibile eseguire conferenze multiparte se si usa un provider di messaggistica istantanea pubblica, che è strettamente correlato alla comunicazione peer-to-peer. Ma sono supportati sia i protocolli SIP che XMPP.
    
- Servizi di conferenza audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.
    
- Web Conferencing: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for business. È anche possibile abilitare la partecipazione per utenti remoti, utenti federati e utenti anonimi, se si preferisce. Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. Sono disponibili anche opzioni per consentire a questi utenti di partecipare a una condivisione di applicazioni e desktop e anche di fungere da organizzatori o relatori della riunione.
    
L'accesso al dispositivo mobile è supportato, così come VoIP aziendale. È possibile invitare utenti esterni alle riunioni a cui si vuole partecipare, anche agli utenti anonimi, se si desidera concedere loro le autorizzazioni.
  
Se si tratta di un aspetto che l'organizzazione ha bisogno, la pianificazione di un ambiente Edge sarà di grande aiuto per la distribuzione. Per ulteriori informazioni, abbiamo gli argomenti elencati di seguito.

> [!NOTE]
> I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019. Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Argomenti di pianificazione:

Gli articoli per la pianificazione sono:
  
- [Requisiti di sistema di Edge Server in Skype for Business Server 2015](system-requirements.md)
    
- [Requisiti ambientali di Edge Server in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Scenari di Edge Server in Skype for Business Server 2015](scenarios.md)
    

