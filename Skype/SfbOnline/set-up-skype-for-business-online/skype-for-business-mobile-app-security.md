---
title: Sicurezza dell’app per dispositivi mobili di Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Informazioni su come configurare la sicurezza delle app per dispositivi mobili per gli utenti. '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010779"
---
# <a name="skype-for-business-mobile-app-security"></a>Sicurezza dell’app per dispositivi mobili di Skype for Business

## <a name="skype-for-business-client-security"></a>Skype for Business Client Security

Questo articolo illustra le informazioni sulla crittografia dei dati nelle app skype for Business per dispositivi mobili.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/password** <br/> |**Dati dell'app (conversazioni, <br/> elenco contatti, riunioni)** <br/> |**Log diagnostici** <br/> |
|**Android** <br/> |Le informazioni sulle credenziali vengono archiviate negli account Android. Le credenziali vengono crittografate anche prima di salvarle negli account. Per la crittografia viene utilizzato l'algoritmo **"AES/CBC/PKCS5Pa".** <br/> |Viene archiviata in un database SQL crittografato tramite una raccolta denominata [sqlcipher.](https://www.zetetic.net/sqlcipher/design/) In modalità CBC viene utilizzato l'algoritmo predefinito AES a 256 bit. I dati in archivio vengono sempre crittografati nel file di database ed è solo non crittografato in transito all'interno della memoria volatile e degli stack di chiamate dell'app. I file della segreteria telefonica vengono crittografati con lo stesso metodo utilizzato per la crittografia del nome utente e della password (non vengono archiviati nel database di proprietà). I messaggi vocali sono temporaneamente non crittografati su disco per consentire la riproduzione.  <br/> |Queste informazioni non sono crittografate.  <br/> |
|**iOS** <br/> |NON crittografare il nome utente o la password nel portachiavi. Il portachiavi è tuttavia crittografato da solo.  <br/> |È già in uso il contrassegno di protezione dati [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) per tutti i file nello spazio di archiviazione dell'app. Questo significa che i file nello spazio di archiviazione dell'app verranno crittografati finché l'utente non sblocca il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non sono crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone usa DPAPI (API di protezione dati) in Windows per proteggere le password. Lo schema di crittografia usato è AES. Windows non offre un'opzione per configurare le dimensioni della chiave (o lo schema), quindi è qualsiasi cosa offre DPAPI. Userà il TPM del dispositivo per proteggere le chiavi specifiche per l'utente e il dispositivo. Si noti che le chiavi DPAPI non sono specifiche dell'app.  <br/> |I dati dell'app WP sono protetti [con DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, come le creds. A seconda della quantità di dettagli desiderata, alcune informazioni dell'indice per i dati dell'app sono protette da crittografia AES (non DPAPI) per evitare la salting, quindi è possibile eseguire una ricerca senza decrittografare la chiave, che a sua volta è protetta con DPAPI. I dati memorizzati nella cache possono essere letti da qualsiasi processo dallo stesso telefono, presupponendo che raggiungano la cartella dei dati. La crittografia di Windows non protegge dalle violazioni sandbox, ma solo dai tentativi di accesso esterno.  <br/> |Queste informazioni non sono crittografate.  <br/> |
   
**Nota:** Fai riferimento a [questa documentazione pubblica per l'applicazione](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) del pin del dispositivo in ognuna delle piattaforme mobili precedenti
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
