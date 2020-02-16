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

## <a name="skype-for-business-client-security"></a>Sicurezza dei client Skype for business

Questo articolo illustra le informazioni sulla crittografia dei dati nelle app per dispositivi mobili Skype for business.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/password** <br/> |**Dati dell'app (conversazioni<br/> , elenco contatti, riunioni)** <br/> |**Registri diagnostici** <br/> |
|**Android** <br/> |Memorizziamo le informazioni sulle credenziali in account Android. Si crittografano anche le credenziali prima di salvarle in account. Usiamo l'algoritmo " **AES/CBC/PKCS5Padding** " per la crittografia. <br/> |Memorizziamo in un database SQL crittografato usando una raccolta denominata [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Usiamo il loro algoritmo predefinito di 256 bit AES in modalità CBC. I dati in Rest vengono sempre crittografati nel file di database ed è solo non crittografati in transito all'interno della memoria volatile dell'app e delle chiamate. È anche possibile crittografare i file della segreteria telefonica usando lo stesso metodo usato per il nome e la crittografia della password dell'utente (non archiviati nel DB). I messaggi vocali sono temporaneamente decrittografati sul disco per consentire la riproduzione.  <br/> |Queste informazioni non sono crittografate.  <br/> |
|**iOS** <br/> |Il nome utente/password non viene crittografato nel portachiavi. Il portachiavi è comunque crittografato autonomamente.  <br/> |Stiamo già usando il contrassegno di protezione dei dati di [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) in tutti i file nell'archiviazione dell'app. Questo significa che i file nell'archiviazione dell'app verrebbero crittografati finché l'utente non sblocca il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non sono crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone usa la DPAPI (Data Protection API) in Windows per proteggere le password. Credo che lo schema di crittografia usato sia AES. Windows non consente di configurare la dimensione della chiave (o lo schema), quindi è tutto ciò che dà DPAPI. Userà il TPM del dispositivo per proteggere le chiavi specifiche per l'utente e il dispositivo. Tieni presente che i tasti DPAPI non sono specifici dell'app.  <br/> |I dati dell'app WP sono protetti con [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)i, come creds. A seconda della quantità di dettagli che vogliamo, alcune delle informazioni di indice per i dati dell'app sono protette dalla crittografia AES (non DPAPI) per evitare la salatura, quindi possiamo cercare senza decrittografare e la chiave è a sua volta protetta con DPAPI. I dati memorizzati nella cache possono essere letti da qualsiasi processo dello stesso telefono, presupponendo che possa raggiungere la cartella dati. La crittografia di Windows non protegge dalla violazione della sandbox, ma solo i tentativi di accesso esterno.  <br/> |Queste informazioni non sono crittografate.  <br/> |
   
**Nota:** Fare riferimento a [questa documentazione pubblica](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) per l'applicazione dei pin del dispositivo disponibile su ognuna delle piattaforme mobili sopra elencate
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
