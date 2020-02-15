---
title: Pianificazione dell'autenticazione moderna (ADAL) con Skype for business
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
description: In questo articolo viene illustrato l'autenticazione moderna (basata sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0).
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046289"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Come usare l'autenticazione moderna (ADAL) con Skype for business
 
Questo articolo introduce l'autenticazione moderna (basata sulla libreria di autenticazione di Active Directory (ADAL) e OAuth 2,0) che può essere trovata nell'aggiornamento cumulativo di marzo 2016 per Skype for business per Skype for Business Server 2015 o da Initial versione per Skype for Business Server 2019.
  
## <a name="what-is-adal"></a>Che cos'è ADAL?

ADAL è l'acronimo della "libreria di autenticazione di Active Directory" e, insieme a OAuth 2,0, è un fondamento dell'autenticazione moderna. Questa libreria di codice è progettata per rendere le risorse protette nella directory disponibili per le applicazioni client (come Skype for business) tramite token di sicurezza. ADAL funziona con OAuth 2,0 per consentire più scenari di autenticazione e autorizzazione, come l'autenticazione a più fattori (AMF) e altre forme di auth SAML.
  
Un'ampia gamma di app che fungono da client possono sfruttare l'autenticazione moderna per ottenere informazioni sulle risorse protette. In Skype for Business Server, questa tecnologia viene utilizzata tra i client locali e i server locali per consentire agli utenti di disporre di un livello di autorizzazione adeguato alle risorse.
  
Le conversazioni di autenticazione moderne (basate su ADAL e OAuth 2,0) presentano alcuni elementi in comune.
  
- C'è un client che effettua una richiesta per una risorsa, in questo caso, il client è Skype for business.
    
- Esiste una risorsa a cui il client ha bisogno di un livello di accesso specifico e questa risorsa è protetta da un servizio directory, in questo caso la risorsa è Skype for Business Server.
    
- Vi è una connessione OAuth, in altre parole, una connessione dedicata all' *autorizzazione* di un utente per l'accesso a una risorsa. (OAuth è conosciuto anche con il nome più descrittivo, l'autenticazione da server a server, ed è spesso abbreviato in S2S).
    
Nelle conversazioni di Skype for Business Server Modern Authentication (ADAL), Skype for Business Server comunica tramite ADFS (ADFS 3,0 in Windows Server 2012 R2). L'autenticazione può essere eseguita utilizzando un altro provider di identità (IdP), ma è necessario configurare Skype for Business Server per comunicare direttamente con ADFS. Se non è stato configurato ADFS per l'utilizzo con Skype for Business Server, completare l' [installazione di ADFS](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL è incluso nell'aggiornamento cumulativo di marzo 2016 per Skype for Business Server 2015 e l'aggiornamento cumulativo di marzo 2016 per Skype for business **deve** essere installato ed è necessario per una corretta configurazione. Per Skype for Business Server 2019, è disponibile dalla versione iniziale del prodotto.
  
> [!NOTE]
> Durante la versione iniziale, l'autenticazione moderna in un ambiente locale è supportata solo se non è coinvolta una topologia di Skype mista. Ad esempio, se l'ambiente è puramente Skype for Business Server. Questa dichiarazione può essere soggetta a modifiche. 
  
È necessario scaricare un pacchetto di PowerShell che include i file con estensione ps1 con i comandi utilizzati da ADAL per una corretta configurazione.

Per informazioni su come implementare l'autenticazione moderna in Skype for business, fare riferimento a: [come usare l'autenticazione moderna (adal) con Skype for business](../../manage/authentication/use-adal.md)
