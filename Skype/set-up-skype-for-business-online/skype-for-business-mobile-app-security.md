---
title: "Skype per la protezione Business per dispositivi mobili"
ms.author: kenwith
author: kenwith
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
description: ""
---

# Skype per la protezione Business per dispositivi mobili

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
## Sicurezza del client Skype for Business

Questo articolo riguarda le informazioni di crittografia dei dati nelle app per dispositivi mobili di Skype for Business.
  
|||||
|:-----|:-----|:-----|:-----|
||**Nome utente/password** <br/> |**Dati app (conversazioni, elenco contatti, riunioni)** <br/> |**Log diagnostici** <br/> |
|**Android** <br/> |Archiviamo informazioni relative alle credenziali negli account Android. Inoltre, crittografiamo le credenziali prima di salvarle negli account. Usiamo l'algoritmo " **AES/CBC/PKCS5Padding** " per la crittografia. <br/> |L'archiviazione avviene in un database SQL crittografato utilizzando una libreria chiamata [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Usiamo il loro algoritmo predefinito di AES a 256 bit in modalità CBC. I dati a riposo sono sempre crittografati nel file di database e sono in chiaro soltanto in transito all'interno della memoria volatile e nei call stack della app. Crittografiamo anche i file della segreteria telefonica utilizzando lo stesso metodo della crittografia di nome utente e password (che non vengono memorizzati nel DB). I messaggi vocali vengono temporaneamente non crittografati su disco per consentire la riproduzione.  <br/> |Queste informazioni non sono crittografate.  <br/> |
|**iOS** <br/> |NON crittografiamo nome utente/password nella keychain. La keychain, tuttavia, è crittografata per conto suo.  <br/> |Stiamo già utilizzando il flag di protezione dati [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) su tutti i file nello spazio di archiviazione della app. Ciò significa che nello spazio di archiviazione della app i file sono crittografati finché l'utente non sblocca il dispositivo per la prima volta dopo il riavvio del dispositivo. <br/> |Queste informazioni non sono crittografate.  <br/> |
|**Windows Phone** <br/> |Windows Phone usa la DPAPI (Data Protection API - interfaccia di programmazione applicazioni per la protezione dati) in Windows per proteggere le password. Credo che il sistema di crittografia utilizzato sia AES. Windows non ci dà la possibilità di configurare la dimensione della chiave (o schema), quindi dobbiamo attenerci alle impostazioni della DPAPI. Utilizzerà il TPM del dispositivo per proteggere chiavi specifiche per l'utente e il dispositivo. Le chiavi DPAPI non sono specifiche per l'applicazione.  <br/> |I dati dell'app WP sono protetti con [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, come le credenziali. A seconda del livello di dettagli che vogliamo, alcune delle informazioni di indice per i dati app sono protetti da crittografia AES (non DPAPI) per evitare il salting, in modo che possiamo effettuare ricerche senza decrittografare, e quella chiave è a sua volta protetta con DPAPI. I dati memorizzati nella cache possono essere letti da qualsiasi processo proveniente dallo stesso telefono, purché possa raggiungere la nostra cartella dei dati. La crittografia di Windows non protegge dalla violazione sandbox, solo dai tentativi di accesso esterni.  <br/> |Queste informazioni non sono crittografate.  <br/> |
   
Nota: fare riferimento a [questa documentazione pubblica](https://docs.microsoft.com/it-it/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) per l'obbligo di utilizzo del pin del dispositivo disponibile su ciascuna delle piattaforme mobili di cui sopra
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

