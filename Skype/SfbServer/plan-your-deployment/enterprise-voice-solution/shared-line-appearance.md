---
title: Pianificare l'aspetto della linea condivisa Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/21/2016
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
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, Aggiornamento cumulativo di novembre 2015.
ms.openlocfilehash: dbe90a1d506f8d90e66ae065b9f31d95897e8c9a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759488"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Pianificare l'aspetto della linea condivisa Skype for Business Server 2015
 
Leggere questo argomento per informazioni su come pianificare l'aspetto linea condivisa (SLA) in Skype for Business Server 2015, Aggiornamento cumulativo di novembre 2015. 
  
L'aspetto linea condivisa è una funzionalità Skype for Business per la gestione di più chiamate su un numero specifico denominato numero condiviso. Sla can configure any enterprise voice enabled Skype for Business user as a shared number with multiple lines to respond to multiple calls. Le chiamate non vengono effettivamente ricevute sul numero condiviso, ma vengono inoltrate agli utenti che agiscono come delegati per il numero condiviso. Uno qualsiasi dei delegati può riprendere la chiamata mentre gli altri delegati ottengono una notifica sul telefono su chi ha preso la chiamata e quale linea è diventata occupata di conseguenza. Sia il numero di righe che i delegati sono configurabili per un numero condiviso nel contratto di servizio. Inoltre, le opzioni avanzate, ad esempio BusyOption (cosa accade in una situazione in cui tutte le linee sono occupate) e MissedCallOption (nel caso in cui nessuno dei delegati preleva una chiamata), possono essere configurate anche per un numero condiviso.
  
Il contratto di servizio è supportato solo nei seguenti dispositivi telefonici (non è supportato per i client Skype for Business computer, telefoni cellulari o altri dispositivi): 
  
- Polycom VVX300 con aggiornamento del firmware 5.4.1
    
- Polycom VVX400 con aggiornamento del firmware 5.4.1
    
- Polycom VVX500 con aggiornamento del firmware 5.4.1
    
- Polycom VVX600 con aggiornamento del firmware 5.4.1
    
Sla è una nuova funzionalità di Skype for Business Server, aggiornamento cumulativo di novembre 2015. 
  
Per informazioni sulla distribuzione del contratto di servizio, vedere [Deploy Shared Line Appearance in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md)
  
## <a name="feature-list"></a>Elenco funzionalità

La configurazione di un gruppo di contratti di servizio consente quanto segue:
  
- Tutti i delegati del gruppo possono rispondere alle chiamate in ingresso allo stesso numero condiviso. Le chiamate possono essere basate su PSTN o SIP.
    
- I delegati possono contenere e prelevare le chiamate.
    
- I delegati possono trasferire le chiamate a un numero esterno al gruppo sla.
    
- I delegati possono visualizzare il numero di chiamate attualmente presenti sul numero condiviso e visualizzare lo stato di ognuna di queste chiamate.
    
- È possibile configurare un numero massimo di chiamate simultanee per il numero condiviso. È inoltre possibile impostare la modalità di gestione delle chiamate aggiuntive dopo aver raggiunto questo valore massimo. Le chiamate in eccesso possono essere rifiutate con un segnale di occupato, inoltrate a un numero alternativo o inoltrate alla segreteria telefonica.
    
- È possibile configurare la modalità di gestione delle chiamate senza risposta (chiamate non effettuate dopo un determinato periodo di tempo). Se si abilita la segreteria telefonica per l'identità del gruppo, le chiamate senza risposta verranno automaticamente effettuate alla segreteria telefonica. Se la segreteria telefonica non è abilitata per l'identità del gruppo (numero condiviso), è possibile scegliere che le chiamate senza risposta siano rifiutate con un segnale di occupato, inoltrate a un numero alternativo o disconnesse.
    

