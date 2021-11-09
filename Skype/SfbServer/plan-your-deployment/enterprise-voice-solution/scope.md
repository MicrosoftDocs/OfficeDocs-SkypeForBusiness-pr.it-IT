---
title: Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: a1757477d9d4de2a0e26c3490bb6214e6c14e1e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836248"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server

Decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.

Prima di configurare Skype for Business per E9-1-1, è necessario pianificare la distribuzione di E9-1-1. Di seguito sono riportati alcuni aspetti di cui tenere conto:

 **Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda E9-1-1?**

 Le disposizioni legali del servizio E9-1-1 per i PBX (denominati sistemi telefonici multilinea, o MLTS, nella terminologia relativa a E9-1-1) variano a seconda delle località. È consigliabile consultare il team legale per comprendere gli obblighi che possono essere applicati alla distribuzione di Skype for Business nelle aree geografiche pertinenti.

 **Aree dell'organizzazione che devono essere abilitate per il servizio E9-1-1**

 È possibile abilitare il servizio E9-1-1 per l'intera organizzazione o solo per località selezionate. È ad esempio possibile applicare requisiti E9-1-1 diversi per gli uffici di stati diversi oppure escludere le sedi al di fuori degli Stati Uniti.

 **Modalità di distribuzione del servizio E9-1-1 nei siti di succursale**

 La resilienza vocale è un concetto importante di cui tenere conto quando si distribuisce il servizio E9-1-1 in un sito di succursale. Se si dispone di trunk SIP E-9-1-1 centralizzati e si verifica un'interruzione della rete WAN, i client che effettuano l'accesso potrebbero non essere in grado di ottenere una posizione dal servizio informazioni sulla posizione o di connettersi al provider di servizi di emergenza. Skype for Business fornisce diverse strategie per gestire la resilienza vocale nelle succursali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni succursale o distribuire chiamate di emergenza al gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).

 **Possibilità di abilitare il servizio E9-1-1 per gli utenti che lavorano all'esterno della rete**

 L'acquisizione automatica della posizione è disponibile solo per i client che si trovano all'interno della rete dell'organizzazione, quindi l'organizzazione deve decidere se supporterà le chiamate E9-1-1 effettuate da client Skype for Business mentre è fuori sede. L'organizzazione deve pertanto decidere se supportare le chiamate E9-1-1 effettuate da client Lync non locali, ad esempio se consentire agli utenti di effettuare chiamate di emergenza quando lavorano dalla propria abitazione o dalla sede di un cliente. Se è posizionato all'esterno di una rete aziendale, un client può essere configurato per richiedere la posizione a un utente. Poiché tuttavia queste posizioni fornite dagli utenti non possono essere precedentemente convalidate a fronte dello stradario generale, il dispatcher del provider di servizi di emergenza dovrà verificare la validità della posizione verbalmente con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).

> [!NOTE]
> Skype for Business i client degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni sull'indirizzo IP interno, ma poiché questi indirizzi non possono essere utilizzati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dal servizio Informazioni percorso.

 **Possibilità di fornire il routing delle chiamate di emergenza per siti al di fuori degli Stati Uniti**

 È possibile offrire il routing delle chiamate di emergenza per aree dell'azienda non servite dal provider di servizi di emergenza, ad esempio sedi internazionali. A tale scopo, creare un nuovo sito e quindi assegnare i criteri vocali ai siti che fanno riferimento a un utilizzo PSTN che instrada le chiamate tramite il gateway PSTN locale.