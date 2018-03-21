---
title: Skype per la protezione di applicazioni per dispositivi mobili aziendali
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Informazioni su come impostare la protezione di applicazioni per dispositivi mobili per gli utenti. '
ms.openlocfilehash: 98a748ca626d9b27a3e75ce5d75641155af7853d
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="skype-for-business-mobile-app-security"></a>Skype per la protezione di applicazioni per dispositivi mobili aziendali

## <a name="skype-for-business-client-security"></a>Skype per la sicurezza dei Client di Business

In questo articolo vengono illustrate informazioni sulla crittografia dei dati in Skype per le applicazioni di Business Mobile.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/Password** <br/> |**App Data (conversazioni,<br/> elenco, le riunioni contatti)** <br/> |**Registri diagnostici** <br/> |
|**Android** <br/> |Informazioni sulle credenziali memorizzate in account Android. È anche possibile crittografare le credenziali prima del salvataggio in account. Viene utilizzato " **AES/CBC/PKCS5Padding** " algoritmo di crittografia. <br/> |Memorizzati in un database SQL crittografato mediante una libreria denominata [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Viene utilizzato l'algoritmo predefinito di AES a 256 bit in modalità CBC. I dati statici sempre vengono crittografati nei file di database e solo non crittografati in transito all'interno dell'app volatili memoria e chiamata stack. È inoltre crittografare i file di segreteria telefonica utilizzando lo stesso metodo come nome dell'utente e la crittografia delle password (non vengono archiviati nel database). Messaggi vocali vengono temporaneamente non crittografate su disco per consentire la riproduzione.  <br/> |Queste informazioni non crittografate.  <br/> |
|**iOS** <br/> |NON è crittografare il nome utente e la password in keychain. Keychain viene crittografato, tuttavia, in modo autonomo.  <br/> |Flag di protezione dati [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) utilizziamo già su tutti i file di archiviazione app. Ciò significa che i file nell'archivio app potrebbero essere crittografati fino a quando non utente consente di sbloccare il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone utilizza DPAPI (Data Protection API) di Windows per proteggere le password. È possibile provare a utilizzare lo schema di crittografia è AES. Windows non invio di commenti un'opzione per configurare la chiave dimensioni (o combinazione), in modo da essere ciò che offre DPAPI. Utilizza il dispositivo GPC per proteggere le chiavi quali sono specifiche per l'utente e il dispositivo. Si noti che le chiavi DPAPI non sono specifiche per l'applicazione.  <br/> |WP App Data è protetta con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)è possibile, ad esempio le credenziali. A seconda della quantità dettagli vogliamo, alcune delle informazioni sugli indici per i dati di App viene protetta tramite la crittografia AES (non DPAPI) per evitare la salagione, in modo che è possibile cercare senza decrittografare e tale chiave, a sua volta è protetta con DPAPI. Leggere i dati memorizzati nella cache da qualsiasi processo dal telefono stesso, presupponendo che sia possibile raggiungere la cartella di dati. Crittografia di Windows non protegge da violazione sandbox, tenta solo l'accesso esterno.  <br/> |Queste informazioni non crittografate.  <br/> |
   
**Nota:** Fare riferimento a [questa documentazione pubblica](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) per l'applicazione pin dispositivi disponibile in ogni le piattaforme mobili
  
## <a name="related-topics"></a>See also
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a>Commenti e suggerimenti?
Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).