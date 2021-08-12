---
title: Pianificazione dell'autenticazione moderna (ADAL) con Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: In questo articolo viene illustrato il tipo di autenticazione moderna (basata su Active Directory Authentication Library (ADAL) e OAuth 2.0.
ms.openlocfilehash: 317c899600730438a56dc3e52ddf76ce5eeb6d6da5297ab2732166ceb9880074
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349918"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Come usare l'autenticazione moderna (ADAL) con Skype for Business
 
In questo articolo viene illustrata l'autenticazione moderna (basata su Active Directory Authentication Library (ADAL) e OAuth 2.0, disponibile nell'aggiornamento cumulativo di marzo 2016 per Skype for Business per Skype for Business Server 2015 o dalla versione iniziale per Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>Che cos'è ADAL?

ADAL è l'acronimo di "Active Directory Authentication Library" e, insieme a OAuth 2.0, è alla base dell'autenticazione moderna. Questa libreria di codice è progettata per rendere le risorse protette nella directory disponibili per le applicazioni client (come Skype for Business) tramite token di sicurezza. ADAL funziona con OAuth 2.0 per abilitare più scenari di autenticazione e autorizzazione, come l'autenticazione a più fattori (MFA) e altre forme di autenticazione SAML.
  
Un'ampia gamma di app che agiscono come client possono sfruttare l'autenticazione moderna per ottenere assistenza per accedere a risorse protette. In Skype for Business Server, questa tecnologia viene utilizzata tra i client locali e i server locali per fornire agli utenti un livello adeguato di autorizzazione per le risorse.
  
Le conversazioni di autenticazione moderna (basate su ADAL e OAuth 2.0) hanno alcuni elementi in comune.
  
- Esiste un client che effettua una richiesta per una risorsa, in questo caso il client è Skype for Business.
    
- Esiste una risorsa a cui il client necessita di un livello di accesso specifico e questa risorsa è protetta da un servizio directory, in questo caso la risorsa è Skype for Business Server.
    
- Esiste una connessione OAuth, in altre parole, una connessione dedicata all'autorizzazione  *di*  un utente ad accedere a una risorsa. OAuth è anche noto con il nome più descrittivo, "Server-to-Server" e spesso è abbreviato come S2S.
    
Nelle Skype for Business Server di autenticazione moderna (ADAL), Skype for Business Server comunica tramite ADFS (ADFS 3.0 in Windows Server 2012 R2). L'autenticazione può avvenire utilizzando un altro provider di identità (IdP), ma Skype for Business server deve essere configurato per comunicare direttamente con ADFS. Se ADFS non è stato configurato per l'utilizzo con Skype for Business Server completare [l'installazione di ADFS.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))
  
ADAL è incluso nell'aggiornamento cumulativo di marzo 2016 per Skype for Business Server 2015 e l'aggiornamento cumulativo di marzo 2016 per Skype for Business deve essere installato ed è necessario per la corretta configurazione.  Per Skype for Business Server 2019, è disponibile dalla versione iniziale del prodotto.
  
> [!NOTE]
> Durante la versione iniziale, l'autenticazione moderna in un ambiente locale è supportata solo se non sono coinvolte Skype topologia di autenticazione mista. Ad esempio, se l'ambiente è puramente Skype for Business Server. Questa dichiarazione può essere soggetta a modifiche. 
  
Per una corretta configurazione, è necessario scaricare un pacchetto di PowerShell .ps1 file con i comandi utilizzati da ADAL.

Per informazioni su come implementare l'autenticazione moderna in Skype for Business, vedere: Come usare l'autenticazione [moderna (ADAL) con](/microsoft-365/enterprise/hybrid-modern-auth-overview) Skype for Business