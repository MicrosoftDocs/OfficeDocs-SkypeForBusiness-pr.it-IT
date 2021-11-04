---
title: Espansione delle impostazioni generali dell'applicazione esterna
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà per un server applicazioni attendibili che è già stato definito, seguire queste istruzioni.
ms.openlocfilehash: 3820e426d90a0c35c54798080308319a5184cf0d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775376"
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

È possibile specificare il server hop successivo del pool di server applicazioni attendibili selezionando il pool Front End edizione Enterprise definito o edizione Standard Front End Server nell'elenco a discesa. Un Director o un pool di server Director non costituisce una selezione valida per l'hop successivo di un server applicazioni attendibili e non risulterà visualizzato nell'elenco.
  

Fare **clic su OK** per accettare e salvare le modifiche. Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.
  

