---
title: Sicurezza dell’app per dispositivi mobili di Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Informazioni su come impostare la protezione di applicazioni per dispositivi mobili per gli utenti. '
ms.openlocfilehash: a87719bc4135ab429fca8425812b285a2eed5b5e
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861292"
---
# <a name="skype-for-business-mobile-app-security"></a>Sicurezza dell’app per dispositivi mobili di Skype for Business

## <a name="skype-for-business-client-security"></a>Skype per la sicurezza dei Client di Business

In questo articolo vengono illustrate informazioni sulla crittografia dei dati in Skype per le applicazioni di Business Mobile.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/password** <br/> |**App Data (conversazioni,<br/> elenco, le riunioni contatti)** <br/> |**Registri diagnostici** <br/> |
|**Android** <br/> |Informazioni sulle credenziali memorizzate in account Android. È anche possibile crittografare le credenziali prima del salvataggio in account. Viene utilizzato " **AES/CBC/PKCS5Padding** " algoritmo di crittografia. <br/> |Memorizzati in un database SQL crittografato mediante una libreria denominata [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Viene utilizzato l'algoritmo predefinito di AES a 256 bit in modalità CBC. I dati statici sempre vengono crittografati nei file di database e solo non crittografati in transito all'interno dell'app volatili memoria e chiamata stack. È inoltre crittografare i file di segreteria telefonica utilizzando lo stesso metodo come nome dell'utente e la crittografia delle password (non vengono archiviati nel database). Messaggi vocali vengono temporaneamente non crittografate su disco per consentire la riproduzione.  <br/> |Queste informazioni non crittografate.  <br/> |
|**iOS** <br/> |NON è crittografare il nome utente e la password in keychain. Keychain viene crittografato, tuttavia, in modo autonomo.  <br/> |Flag di protezione dati [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) utilizziamo già su tutti i file di archiviazione app. Ciò significa che i file nell'archivio app potrebbero essere crittografati fino a quando non utente consente di sbloccare il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone utilizza DPAPI (Data Protection API) di Windows per proteggere le password. È possibile provare a utilizzare lo schema di crittografia è AES. Windows non invio di commenti un'opzione per configurare la chiave dimensioni (o combinazione), in modo da essere ciò che offre DPAPI. Utilizza il dispositivo GPC per proteggere le chiavi quali sono specifiche per l'utente e il dispositivo. Si noti che le chiavi DPAPI non sono specifiche per l'applicazione.  <br/> |WP App Data è protetta con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)è possibile, ad esempio le credenziali. A seconda della quantità dettagli vogliamo, alcune delle informazioni sugli indici per i dati di App viene protetta tramite la crittografia AES (non DPAPI) per evitare la salagione, in modo che è possibile cercare senza decrittografare e tale chiave, a sua volta è protetta con DPAPI. Leggere i dati memorizzati nella cache da qualsiasi processo dal telefono stesso, presupponendo che sia possibile raggiungere la cartella di dati. Crittografia di Windows non protegge da violazione sandbox, tenta solo l'accesso esterno.  <br/> |Queste informazioni non crittografate.  <br/> |
   
**Nota:** Fare riferimento a [questa documentazione pubblica](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) per l'applicazione pin dispositivi disponibile in ogni le piattaforme mobili
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 