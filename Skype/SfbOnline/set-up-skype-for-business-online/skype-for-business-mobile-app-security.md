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
ms.openlocfilehash: 1adfc8e44880b89ab9f4b24be532ae4a327744cf69d0ef63ecea3f65ae684fc8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295113"
---
# <a name="skype-for-business-mobile-app-security"></a>Sicurezza dell’app per dispositivi mobili di Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Skype for Business Client Security

Questo articolo illustra le informazioni sulla crittografia dei dati Skype for Business app per dispositivi mobili.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/password** <br/> |**Dati dell'app (Conversazioni, <br/> Elenco contatti, Riunioni)** <br/> |**Log di diagnostica** <br/> |
|**Android** <br/> |Le informazioni sulle credenziali vengono archiviate in Account Android. Le credenziali vengono crittografate anche prima di salvarle in Account. Per la crittografia viene utilizzato l'algoritmo " **AES/CBC/PKCS5Padding** ". <br/> |Archiviamo in un database SQL crittografato usando una raccolta denominata [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Viene utilizzato l'algoritmo predefinito AES a 256 bit in modalità CBC. I dati in pausa sono sempre crittografati nel file di database ed è solo non crittografato in transito all'interno della memoria volatile e degli stack di chiamate dell'app. I file della segreteria telefonica vengono crittografati anche con lo stesso metodo utilizzato per la crittografia del nome e della password dell'utente (non vengono archiviati nel database). I messaggi vocali sono temporaneamente non crittografati su disco per consentire la riproduzione.  <br/> |Queste informazioni non sono crittografate.  <br/> |
|**iOS** <br/> |NON crittografiamo il nome utente/password nel portachiavi. Il portachiavi, tuttavia, è crittografato da solo.  <br/> |Il flag di protezione dei dati [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) è già in uso in tutti i file nello spazio di archiviazione dell'app. Questo significa che i file nello spazio di archiviazione dell'app verranno crittografati finché l'utente non sblocca il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non sono crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone usa DPAPI (Data Protection API) in Windows per proteggere le password. Credo che lo schema di crittografia usato sia AES. Windows non offre un'opzione per configurare le dimensioni della chiave (o dello schema), quindi è tutto ciò che fornisce DPAPI. Userà il TPM del dispositivo per proteggere le chiavi specifiche per l'utente e il dispositivo. Tenere presente che i tasti DPAPI non sono specifici dell'app.  <br/> |I dati delle app WP sono protetti [con DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, come le creds. A seconda del livello di dettaglio desiderato, alcune delle informazioni di indice per i dati dell'app sono protette dalla crittografia AES (non DPAPI) per evitare il salting, quindi è possibile cercare senza decrittografare e la chiave è a sua volta protetta con DPAPI. I dati memorizzati nella cache possono essere letti da qualsiasi processo dallo stesso telefono, presupponendo che possa raggiungere la cartella dati. Windows crittografia non protegge dalla violazione della sandbox, ma solo dai tentativi di accesso esterno.  <br/> |Queste informazioni non sono crittografate.  <br/> |
   
**Nota:** Fare riferimento a [questa documentazione pubblica per l'applicazione](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) del pin del dispositivo disponibile in ognuna delle piattaforme mobili precedenti
  
## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)

  
