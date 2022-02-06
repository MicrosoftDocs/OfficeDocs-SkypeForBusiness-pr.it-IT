---
title: Pianificare l'autenticazione moderna in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 'Argomenti relativi alla pianificazione dell''autenticazione e dell''Skype for Business Server, inclusa l''integrazione con altri prodotti'
---

# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discussione dell'autenticazione e dell'autorizzazione in Skype for Business

L'autenticazione e l'autorizzazione sono concetti correlati, ma possono essere utilizzati in modo diverso (anche se entrambi sono necessari). In termini semplici, l'autenticazione (AuthN) dipende dai segreti che solo un utente valido conosce o possiede e può essere una password, un codice, un'impronta digitale, un certificato, una combinazione di attestazioni sull'utente vere o una combinazione di questi elementi usati insieme. AuthN è un processo che dimostra di essere quello che dici di essere.

L'autorizzazione (AuthZ) riguarda ciò a cui hai accesso dopo aver dimostrato chi sei. Determina ciò che ti è stato consentito di vedere, modificare e accedere in altro modo. Ad esempio, è possibile disporre di un potente accesso dell'amministratore della raccolta siti a SharePoint Online, ma se si passa a un altro carico di lavoro online, ad esempio Skype for Business Online, è possibile disporre dei privilegi per risolvere i problemi degli utenti e non modificare la configurazione del server o dei server. In un terzo carico di lavoro, ad esempio Exchange Online, si potrebbe avere solo l'accesso medio dell'utente. AuthZ controlla cosa e quanto accesso è necessario a servizi/worload, applicazioni, file e altri dati.

I nostri esempi riguardano proprietà online come SharePoint e Exchange online, ma i processi di AuthN e AuthZ funzionano in locale e in una sede ibrida nello stesso modo. Infine, strumenti come AAD Connessione e ADFS vengono coinvolti nella storia di AuthN e AuthZ sincronizzando account e password locali nell'AD del cloud (che è Azure AD) o intrusendo nel flusso di AuthZ in modo che a un utente non venga richiesto spesso di immettere le credenziali, ad esempio quando si passa da un carico di lavoro all'altro nel cloud, creando scenari di Sign-On single. Ma non sono, di per sé, responsabili di AuthN o AuthZ, solo una parte delle meccaniche.

Oggi, molte tecnologie considerano questi processi (AuthN e AuthZ) come un meccanismo e si sentiranno molti riferimenti al processo di autenticazione che includono anche l'autorizzazione in essi. È importante ricordare che il primo passaggio nell'accesso degli utenti è AuthN, dimostrando di essere chi si dice di essere e che AuthZ usa la conoscenza di chi è l'utente per determinare a cosa ha accesso (come vedrai con Open Authorization o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Argomenti relativi alla pianificazione dell'autenticazione e dell'autorizzazione

[Come usare l'autenticazione moderna (ADAL) con Skype for Business](plan-adal.md)

[Topologie di Skype for Business supportate per l'autenticazione moderna](topologies-supported.md)

[Pianificazione della disattivazione dei metodi di autenticazione legacy internamente ed esternamente alla rete.](turn-on-modern-auth.md)

