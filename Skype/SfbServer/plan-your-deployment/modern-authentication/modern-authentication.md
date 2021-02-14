---
title: Pianificare l'autenticazione moderna in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Argomenti relativi alla pianificazione per l'autenticazione e l'autorizzazione per Skype for Business Server, inclusa l'integrazione con altri prodotti
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816246"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discussione dell'autenticazione e dell'autorizzazione in Skype for Business

L'autenticazione e l'autorizzazione sono concetti correlati, ma ese un lavoro diverso (anche se entrambi sono necessari). In parole semplici, l'autenticazione (AuthN) dipende dai segreti che solo un utente valido conosce o possiede e può essere una password, un codice, un'impronta digitale, un certificato, una combinazione di attestazioni sull'utente vere o una combinazione di questi elementi usati insieme. AuthN è un processo per dimostrare di essere chi si dice di essere.

L'autorizzazione (AuthZ) riguarda gli elementi a cui si ha accesso dopo aver dimostrato chi si è. Determina gli elementi a cui è stato consentito visualizzare, modificare e accedere in altro modo. Ad esempio, è possibile disporre di un potente accesso di amministratore della raccolta siti a SharePoint Online, ma se si passa a un altro carico di lavoro online, come Skype for Business online, è possibile disporre dei privilegi per risolvere i problemi degli utenti, non modificare la configurazione del server o dei server. In un terzo carico di lavoro, ad esempio Exchange Online, si potrebbe avere solo l'accesso dell'utente medio. AuthZ controlla cosa e quanto accesso è necessario a servizi/worload, applicazioni, file e altri dati.

I nostri esempi riguardano proprietà online come SharePoint ed Exchange Online, ma i processi di AuthN e AuthZ funzionano in locale e in una distribuzione ibrida allo stesso modo. Infine, strumenti come AAD Connect e ADFS vengono coinvolti nella storia AuthN e AuthZ sincronizzando gli account e le password locali nell'AD del cloud (che è Azure AD) o intrusendo nel flusso di AuthZ in modo che a un utente non venga richiesto frequentemente di immettere le credenziali, ad esempio quando si passa da un carico di lavoro all'altro nel cloud, creando scenari single Sign-On. Ma non sono, di per sé, responsabili AuthN o AuthZ, solo parte delle meccaniche.

Oggi, molte tecnologie considerano questi processi (AuthN e AuthZ) un unico meccanismo e si sentiranno molti riferimenti al processo di autenticazione che includono anche l'autorizzazione in essi. È importante ricordare che il primo passaggio dell'accesso utente è AuthN, dimostrando di essere chi si dice di essere e che AuthZ usa la conoscenza di chi è l'utente per determinare a cosa ha accesso (come si vede con Open Authorization o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Argomenti relativi alla pianificazione dell'autenticazione e dell'autorizzazione

[Come usare l'autenticazione moderna (ADAL) con Skype for Business](plan-adal.md)

[Topologie di Skype for Business supportate per l'autenticazione moderna](topologies-supported.md)

[Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete.](turn-on-modern-auth.md)

