---
title: Pianificazione per l'autenticazione moderna (ADAL) con Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Questo articolo illustra l'autenticazione moderna, basata sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0.
ms.openlocfilehash: 239dd6a49ecbec043a661e622a66eb5cb4665e96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815834"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Come usare l'autenticazione moderna (ADAL) con Skype for business
 
Questo articolo introduce l'autenticazione moderna (che si basa sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0) che si trova nell'aggiornamento cumulativo di marzo 2016 per Skype for business per Skype for Business Server 2015 o da Initial rilascio per Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>Che cos'è ADAL?

ADAL è l'acronimo di "Active Directory Authentication Library" e, insieme a OAuth 2,0, è un fondamento dell'autenticazione moderna. Questa raccolta di codice è progettata per rendere le risorse protette nella directory disponibili per le applicazioni client (come Skype for business) tramite token di sicurezza. ADAL funziona con OAuth 2,0 per consentire più scenari di autenticazione e autorizzazione, come l'autenticazione a più fattori e altre forme di auth SAML.
  
Una varietà di app che fungono da client possono sfruttare l'autenticazione moderna per ottenere informazioni sulle risorse protette. In Skype for Business Server questa tecnologia viene usata tra i clienti locali e i server locali per offrire agli utenti un livello di autorizzazione appropriato per le risorse.
  
Le conversazioni di autenticazione moderna basate su ADAL e OAuth 2,0 hanno alcuni elementi comuni.
  
- C'è un client che effettua una richiesta per una risorsa, in questo caso il client è Skype for business.
    
- Esiste una risorsa a cui il client ha bisogno di un livello di accesso specifico e questa risorsa è protetta da un servizio directory, in questo caso la risorsa è Skype for Business Server.
    
- C'è una connessione OAuth, in altre parole, una connessione dedicata a *autorizzare* un utente ad accedere a una risorsa. (OAuth è noto anche per il nome più descrittivo, "server-to-server", ed è spesso abbreviato in S2S.)
    
Nelle conversazioni di Skype for Business Server Modern Authentication (ADAL), Skype for Business Server comunica tramite ADFS (ADFS 3,0 in Windows Server 2012 R2). L'autenticazione può essere eseguita usando un altro provider di identità (IdP), ma è necessario configurare Skype for Business Server per comunicare direttamente con ADFS. Se ADFS non è stato configurato per l'utilizzo con Skype for Business Server, completare l' [installazione di ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL è incluso nell'aggiornamento cumulativo di marzo 2016 per Skype for Business Server 2015 e l'aggiornamento cumulativo di marzo 2016 per Skype for business **deve** essere installato ed è necessario per la configurazione corretta. Per Skype for Business Server 2019 è disponibile dalla versione iniziale del prodotto.
  
> [!NOTE]
> Durante la versione iniziale, l'autenticazione moderna in un ambiente locale è supportata solo se non è coinvolta una topologia di Skype mista. Ad esempio, se l'ambiente è puramente Skype for Business Server. Questa istruzione può essere soggetta a modifiche. 
  
È necessario scaricare un pacchetto di PowerShell, inclusi i file con estensione ps1, con i comandi usati da ADAL per la configurazione corretta.

Per informazioni su come implementare l'autenticazione moderna in Skype for business, vedere: [come usare l'autenticazione moderna (adal) con Skype for business](../../manage/authentication/use-adal.md)
