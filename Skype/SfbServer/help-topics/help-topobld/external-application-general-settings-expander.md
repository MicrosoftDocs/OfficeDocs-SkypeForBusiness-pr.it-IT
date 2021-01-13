---
title: Espansione delle impostazioni generali dell'applicazione esterna
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Per modificare le proprietà per un server applicazioni attendibili che è già stato definito, seguire queste istruzioni.
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804766"
---
# <a name="external-application-general-settings-expander"></a>Espansione delle impostazioni generali dell'applicazione esterna
 
Per modificare le proprietà per un server applicazioni attendibili che è già stato definito, seguire queste istruzioni.
  
È possibile modificare due sezioni:
  
> Impostazioni generali
> 
> Impostazioni dell'hop successivo
    
## <a name="general-settings"></a>Impostazioni generali

È possibile modificare l'attuale nome di dominio completo (FQDN) del pool di server applicazioni attendibili. Modificare il nome di questo FQDN. I record host (A) DNS (Domain Name System) per la nuova voce devono esistere prima che i client o i server possano connettersi al nuovo nome del pool.
  
Selezionare **Abilita la replica dei dati di configurazione nel pool** se è necessaria la replica dei dati di configurazione in questo pool. Deselezionare la casella di controllo se non si vuole replicare i dati di configurazione.
  
## <a name="next-hop-settings"></a>Impostazioni dell'hop successivo

È possibile specificare il server dell'hop successivo del pool di server applicazioni attendibili selezionando il pool Enterprise Edition front end o il server Standard Edition front end dall'elenco a discesa. Un Director o un pool di server Director non costituisce una selezione valida per l'hop successivo di un server applicazioni attendibili e non risulterà visualizzato nell'elenco.
  


Fare clic su **OK** per accettare e salvare le modifiche. Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.
  

