---
title: Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisioni necessarie per la pianificazione di una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: fa300ac2f4ba1c0d847abec138b6882e4f240831
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802466"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server

Decisioni necessarie per la pianificazione di una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.

Prima di configurare Skype for business per E9-1-1, è necessario pianificare la distribuzione di E9-1-1. Alcune delle domande da prendere in considerazione includono:

 **Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il E9-1-1?**

 I requisiti legali di E9-1-1 per i PBX (detti sistemi telefonici multilinea o MLTS, in E9-1-1) sono diversi da stato a stato. Dovresti consultarti con il tuo team legale per comprendere gli obblighi che possono essere applicati alla tua distribuzione di Skype for business nelle tue geografie pertinenti.

 **Quali aree all'interno dell'organizzazione devono essere abilitate per il E9-1-1?**

 È possibile abilitare E9-1-1 per l'intera organizzazione o per le posizioni selezionate. Ad esempio, potresti avere requisiti di E9-1-1 diversi per gli uffici in diversi Stati oppure vuoi escludere i siti al di fuori degli Stati Uniti.

 **Come si distribuisce E9-1-1 a siti di succursale?**

 La resilienza vocale è un concetto importante da comprendere quando si distribuisce E9-1-1 in un sito di succursale. Se sono presenti trunk SIP e-9-1-1 centralizzati e si verifica un'interruzione WAN, i client che accedono potrebbero non essere in grado di ottenere un percorso dal servizio informazioni sulla posizione o connettersi al provider di servizi di emergenza. Skype for business offre diverse strategie per gestire la resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni filiale o spingere le chiamate di emergenza al gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [pianificazione della resilienza vocale del sito di succursale](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Si Abilita E9-1-1 per gli utenti che lavorano all'esterno della rete?**

 L'acquisizione automatica della posizione è disponibile solo per i client che si trovano all'interno della rete dell'organizzazione, quindi l'organizzazione deve decidere se supportare le chiamate E9-1-1 effettuate da client Skype for business mentre è fuori sede. Ad esempio, puoi consentire agli utenti di inserire chiamate di emergenza se lavorano da casa o da un sito del cliente? Se un client si trova all'esterno della rete aziendale, il client può essere configurato per richiedere all'utente una posizione. Tuttavia, dato che questi percorsi forniti dall'utente non possono essere convalidati rispetto alla guida per gli indirizzi master Street (stradario), il dispatcher del provider di servizi di emergenza dovrà confermare la validità della posizione verbalmente con il chiamante prima del routing chiamata al punto di risposta della sicurezza pubblica (PSAP).

> [!NOTE]
> I client Skype for business degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni interne sull'indirizzo IP, ma poiché questi indirizzi non possono essere usati per identificare la posizione effettiva dell'utente, è essenziale escludere le subnet VPN dal servizio informazioni sulla posizione.

 **Si desidera specificare il routing delle chiamate di emergenza ai siti esterni agli Stati Uniti?**

 Potrebbe essere necessario disporre di un routing di emergenza per le aree della società non gestite da un provider di servizi di emergenza (ad esempio, posizioni internazionali). A questo scopo, crea un nuovo sito e quindi Assegna criteri vocali ai siti che fanno riferimento a un uso PSTN che instrada la chiamata tramite il gateway PSTN locale.


