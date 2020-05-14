---
title: Pianificare l'autenticazione moderna in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Argomenti di pianificazione per l'autenticazione e l'autorizzazione per Skype for Business Server, inclusa l'integrazione con altri prodotti
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221580"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discussione dell'autenticazione e dell'autorizzazione in Skype for business

L'autenticazione e l'autorizzazione sono concetti correlati, ma è necessario eseguire operazioni diverse (sebbene entrambi siano necessari). In termini semplici, Authenciation (AuthN) dipende da segreti che un utente valido SA o ha e che può essere una password, codice, impronta digitale, un certificato, una combinazione di attestazioni relative all'utente vero o una combinazione di questi elementi utilizzati insieme. AuthN è un processo per dimostrare di essere chi dici di essere.

Autorizzazione (AuthZ) è interessata a ciò che si ha accesso dopo che si è verificato ciò che si è. Determina gli elementi che sono stati autorizzati a visualizzare, modificare e altrimenti accedere. Ad esempio, è possibile che l'amministratore di raccolta siti sia un potente accesso a SharePoint Online, ma se si passa a un altro carico di lavoro online, come Skype for business online, è possibile che si disponga dei privilegi per risolvere i problemi degli utenti, non modificare la configurazione del server o dei server. In un terzo carico di lavoro, ad esempio Exchange Online, è possibile che si disponga solo dell'accesso medio dell'utente. AuthZ verifica le informazioni e la quantità di accesso che è necessario per i servizi/worloads, le applicazioni, i file e altri dati.

I nostri esempi coinvolgono proprietà online come SharePoint ed Exchange Online, ma i processi di AuthN e AuthZ funzionano in locale e in un ambiente ibrido allo stesso modo. Infine, gli strumenti come AAD Connect ed ADFS sono coinvolti nella storia AuthN e AuthZ sincronizzando gli account e le password locali nell'annuncio del cloud (ovvero Azure AD) o invadendo il flusso di AuthZ in modo che un utente non venga spesso richiesto per le proprie credenziali, ad esempio quando si passa da un carico di lavoro all'altro nel cloud, creando scenari di Single Sign-on. Ma non sono, di per sé, responsabili AuthN o AuthZ, solo parte dei meccanici.

Oggi molte tecnologie considerano questi processi (AuthN e AuthZ) come un meccanismo e si sentono numerosi riferimenti al processo di autenticazione che includono anche l'autorizzazione in essi. È importante tenere presente che il primo passaggio nell'accesso degli utenti è AuthN, dimostrando di essere coloro che si dicono di essere e che AuthZ utilizza la conoscenza di chi l'utente deve determinare gli elementi a cui ha accesso (come si vedrà con l'autorizzazione aperta o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Argomenti relativi alla pianificazione dell'autenticazione e dell'autorizzazione

[Come usare l'autenticazione moderna (ADAL) con Skype for business](plan-adal.md)

[Topologie di Skype for business supportate con l'autenticazione moderna](topologies-supported.md)

[Pianificazione della disattivazione dei metodi di autenticazione legacy all'interno e all'esterno della rete.](turn-on-modern-auth.md)

