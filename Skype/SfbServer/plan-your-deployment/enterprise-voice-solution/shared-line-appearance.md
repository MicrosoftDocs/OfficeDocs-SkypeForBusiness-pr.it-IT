---
title: Pianificare l'aspetto della linea condivisa in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015.
ms.openlocfilehash: d7fa13b36c232e37c79e8509de71b4ac29ceff72
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813346"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Pianificare l'aspetto della linea condivisa in Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, aggiornamento cumulativo di novembre 2015. 
  
L'aspetto linea condivisa è una funzionalità di Skype for Business per la gestione di più chiamate su un numero specifico denominato numero condiviso. Sla can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls. Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che fungono da delegati per il numero condiviso. Uno qualsiasi dei delegati può riprendere la chiamata mentre il resto dei delegati ottiene una notifica sul telefono su chi ha preso la chiamata e quale linea è diventata occupata di conseguenza. Sia il numero di righe che i delegati sono configurabili per un numero condiviso nel contratto di servizio. Inoltre, le opzioni avanzate, come BusyOption (cosa accade in una situazione in cui tutte le linee sono occupate) e MissedCallOption (nel caso in cui nessuno dei delegati preleva una chiamata), possono anche essere configurate per un numero condiviso.
  
Sla is supported only on the following phone devices (it is not supported for Skype for Business clients on computers, mobile phones, or other devices): 
  
- Polycom VVX300 con aggiornamento del firmware 5.4.1
    
- Polycom VVX400 con aggiornamento del firmware 5.4.1
    
- Polycom VVX500 con aggiornamento del firmware 5.4.1
    
- Polycom VVX600 con aggiornamento del firmware 5.4.1
    
SLA is a new feature in Skype for Business Server, November 2015 Cumulative Update. 
  
Per informazioni sulla distribuzione del contratto di servizio, vedere [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)
  
## <a name="feature-list"></a>Elenco caratteristiche

La configurazione di un gruppo di contratti di servizio consente quanto segue:
  
- Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso. Le chiamate possono essere basate su PSTN o SIP.
    
- I delegati possono contenere e riprendere le chiamate.
    
- I delegati possono trasferire le chiamate a un numero esterno al gruppo sla.
    
- I delegati possono visualizzare il numero di chiamate attualmente presenti nel numero condiviso e visualizzare lo stato di ognuna di queste chiamate.
    
- È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso. È inoltre possibile impostare la modalità di gestione delle chiamate aggiuntive una volta raggiunto questo valore massimo. Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.
    
- È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non effettuate dopo un determinato periodo di tempo). Se si abilita la segreteria telefonica per l'identità del gruppo, le chiamate senza risposta passano automaticamente alla segreteria telefonica. Se la segreteria telefonica non è abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere che le chiamate senza risposta siano rifiutate con un segnale di occupato, inoltrate a un numero alternativo o disconnesse.
    

