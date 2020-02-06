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
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815844"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a>Discutere di autenticazione e autorizzazione in Skype for business

L'autenticazione e l'autorizzazione sono concetti correlati, ma il lavoro è diverso (anche se entrambi sono necessari). In termini semplici, Authenciation (AuthN) dipende da segreti che solo un utente valido conosce o ha e che può essere una password, un codice, un'impronta digitale, un certificato, una combinazione di attestazioni relative all'utente vero o una combinazione di questi elementi usati insieme. AuthN è un processo che dimostra di essere quello che dici di essere.

Authorization (AuthZ) è interessato a ciò a cui si ha accesso dopo aver provato chi è. Determina le informazioni che è stato consentito visualizzare, modificare e accedere in altro modo. Ad esempio, potresti avere un potente amministratore della raccolta siti per l'accesso a SharePoint Online, ma se passi a un altro carico di lavoro online, come Skype for business online, potresti avere i privilegi per risolvere i problemi degli utenti, non modificare la configurazione del Server o server. In un terzo carico di lavoro, ad esempio Exchange Online, potresti avere solo l'accesso dell'utente medio. AuthZ controlla la quantità e l'accesso a servizi/worloads, applicazioni, file e altri dati.

I nostri esempi coinvolgono proprietà online come SharePoint ed Exchange Online, ma i processi di AuthN e AuthZ funzionano in locale e in una sede ibrida allo stesso modo. In definitiva, gli strumenti come AAD Connect e ADFS vengono coinvolti nella storia AuthN e AuthZ sincronizzando gli account locali e le password nell'annuncio della nuvola (ad esempio Azure AD, nel caso di Office 365 o Azure) oppure invadendo il flusso di AuthZ in modo che un utente non viene spesso richiesto le credenziali, ad esempio quando si passa tra i carichi di lavoro nel cloud, creando scenari Single Sign-on. Ma non sono, in se stessi, responsabili AuthN o AuthZ, solo parte della meccanica.

Oggi molte tecnologie considerano questi processi (AuthN e AuthZ) come un unico meccanismo e si sentono molti riferimenti al processo di autenticazione che includono anche l'autorizzazione. È importante ricordare che il primo passaggio nell'accesso degli utenti è AuthN, che dimostra di essere quello che dici di essere e che AuthZ usa la conoscenza di chi l'utente deve determinare di cosa ha accesso (come vedrai con l'autorizzazione aperta o OAuth).

  
## <a name="authentication-and-authorization-planning-topics"></a>Argomenti per l'autenticazione e la pianificazione delle autorizzazioni

[Come usare l'autenticazione moderna (ADAL) con Skype for business](plan-adal.md)

[Topologie Skype for business supportate con l'autenticazione moderna](topologies-supported.md)

[Pianificazione per disattivare i metodi di autenticazione legacy internamente e esternamente alla rete.](turn-on-modern-auth.md)

