---
title: Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Le decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813426"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>Definire l'ambito della distribuzione di E9-1-1 in Skype for Business Server

Le decisioni necessarie per la pianificazione di una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.

Prima di configurare Skype for business per il servizio E9-1-1, è necessario pianificare la distribuzione di E9-1-1. Di seguito sono riportati alcuni aspetti di cui tenere conto:

 **Quali sono i criteri e gli obblighi legali dell'organizzazione per quanto riguarda il servizio E9-1-1?**

 Le disposizioni legali del servizio E9-1-1 per i PBX (denominati sistemi telefonici multilinea, o MLTS, nella terminologia relativa a E9-1-1) variano a seconda delle località. È consigliabile rivolgersi al proprio team legale per capire gli obblighi che possono essere applicati alla distribuzione di Skype for business nelle rispettive aree geografiche.

 **Aree dell'organizzazione che devono essere abilitate per il servizio E9-1-1**

 È possibile abilitare il servizio E9-1-1 per l'intera organizzazione o solo per località selezionate. È ad esempio possibile applicare requisiti E9-1-1 diversi per gli uffici di stati diversi oppure escludere le sedi al di fuori degli Stati Uniti.

 **Modalità di distribuzione del servizio E9-1-1 nei siti di succursale**

 La resilienza vocale è un concetto importante di cui tenere conto quando si distribuisce il servizio E9-1-1 in un sito di succursale. Se si dispone di trunk SIP e-9-1-1 centralizzato e si verifica un'interruzione della rete WAN, i client che effettuano l'accesso potrebbero non essere in grado di ottenere un percorso dal servizio informazioni percorso o connettersi al provider di servizi di emergenza. In Skype for business sono disponibili diverse strategie per la gestione della resilienza vocale nelle succursali, tra cui: una rete di dati resilienti, la distribuzione di un trunk SIP in ogni filiale o la pressione di chiamate di emergenza verso il gateway locale durante le interruzioni. Per informazioni dettagliate, vedere [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).

 **Possibilità di abilitare il servizio E9-1-1 per gli utenti che lavorano all'esterno della rete**

 L'acquisizione automatica delle posizioni è disponibile solo per i client situati all'interno della rete dell'organizzazione, quindi è necessario che l'organizzazione decida se supporta le chiamate E9-1-1 effettuate dai client Skype for business in locale. L'organizzazione deve pertanto decidere se supportare le chiamate E9-1-1 effettuate da client Lync non locali, ad esempio se consentire agli utenti di effettuare chiamate di emergenza quando lavorano dalla propria abitazione o dalla sede di un cliente. Se è posizionato all'esterno di una rete aziendale, un client può essere configurato per richiedere la posizione a un utente. Poiché tuttavia queste posizioni fornite dagli utenti non possono essere precedentemente convalidate a fronte dello stradario generale, il dispatcher del provider di servizi di emergenza dovrà verificare la validità della posizione verbalmente con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point).

> [!NOTE]
> I client Skype for business degli utenti che si connettono alla rete dell'organizzazione tramite VPN possono raccogliere informazioni sull'indirizzo IP interno, ma poiché questi indirizzi non possono essere utilizzati per identificare la posizione effettiva dell'utente, è essenziale che le subnet VPN siano escluse dal servizio informazioni percorso.

 **Possibilità di fornire il routing delle chiamate di emergenza per siti al di fuori degli Stati Uniti**

 È possibile offrire il routing delle chiamate di emergenza per aree dell'azienda non servite dal provider di servizi di emergenza, ad esempio sedi internazionali. A tale scopo, creare un nuovo sito e quindi assegnare i criteri vocali ai siti che fanno riferimento a un utilizzo PSTN che instrada le chiamate tramite il gateway PSTN locale.


