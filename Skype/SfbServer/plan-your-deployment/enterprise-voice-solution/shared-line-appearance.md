---
title: Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leggere questo argomento per informazioni su come pianificare l'uso di SLA (Shared Line Appearance) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.
ms.openlocfilehash: 966c9f32a27ba936e880bdb51690bcefed4ffbe4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187559"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Pianificare l'aspetto della linea condivisa in Skype for Business Server 2015
 
Leggere questo argomento per informazioni su come pianificare l'uso di SLA (Shared Line Appearance) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. 
  
L'aspetto delle linee condivise è una funzionalità di Skype for business per la gestione di più chiamate su un numero specifico denominato numero condiviso. SLA può configurare qualsiasi utente di Skype for business abilitato per VoIP aziendale come numero condiviso con più linee per rispondere a più chiamate. Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso. Uno qualsiasi dei delegati può prendere la chiamata mentre il resto dei delegati riceve una notifica al telefono su chi ha ricevuto la chiamata e quale linea si è occupata di conseguenza. Sia il numero di righe che i delegati sono configurabili per un numero condiviso in SLA. Inoltre, le opzioni avanzate, ad esempio BusyOption (cosa succede in una situazione in cui tutte le linee sono occupate) e MissedCallOption (il caso in cui nessuno dei delegati prende una chiamata), possono essere configurate anche per un numero condiviso.
  
SLA è supportato solo nei dispositivi telefonici seguenti (non è supportato per i client Skype for business su computer, telefoni cellulari o altri dispositivi): 
  
- Polycom VVX300 con aggiornamento firmware 5.4.1
    
- Polycom VVX400 con aggiornamento firmware 5.4.1
    
- Polycom VVX500 con aggiornamento firmware 5.4.1
    
- Polycom VVX600 con aggiornamento firmware 5.4.1
    
SLA è una nuova funzionalità in Skype for Business Server, aggiornamento cumulativo di novembre 2015. 
  
Per informazioni sulla distribuzione di SLA, vedere [distribuire l'aspetto delle linee condivise in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Elenco delle caratteristiche

La configurazione di un gruppo di SLA consente la seguente procedura:
  
- Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso. Le chiamate possono essere basate su PSTN o SIP.
    
- I delegati possono tenere e ritirare le chiamate.
    
- I delegati possono trasferire le chiamate a un numero esterno al gruppo SLA.
    
- I delegati possono vedere quante chiamate sono attualmente sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.
    
- Puoi configurare un numero massimo di chiamate simultanee per il numero condiviso. È anche possibile impostare la modalità di gestione delle chiamate aggiuntive dopo il raggiungimento del massimo. Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrato a un numero alternativo oppure inoltrato alla segreteria telefonica.
    
- È possibile configurare la modalità di gestione delle chiamate perse (le chiamate non vengono raccolte dopo un determinato periodo di tempo). Se si Abilita la segreteria telefonica per l'identità del gruppo, le chiamate perse vengono automaticamente inoltrate alla segreteria telefonica. Se non si dispone della segreteria telefonica abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere di rifiutare le chiamate perse con un segnale di occupato, inoltrato a un numero alternativo o disconnesso.
    

