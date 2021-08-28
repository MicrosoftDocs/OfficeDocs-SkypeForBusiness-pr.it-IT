---
title: Assegnare un certificato di autenticazione da server a server a Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Riepilogo: assegnare un certificato di autenticazione da server a server per Skype for Business Server.'
ms.openlocfilehash: 67e9b618e882a257047a4569e790d96c73bf386b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621082"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Assegnare un certificato di autenticazione da server a server a Skype for Business Server
**Riepilogo:** Assegnare un certificato di autenticazione da server a server per Skype for Business Server.
  
Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Skype for Business Server, eseguire il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Se non vengono restituite informazioni sul certificato, è necessario assegnare un certificato dell'autorità emittente di token prima di poter utilizzare l'autenticazione da server a server. Come regola generale, qualsiasi Skype for Business Server può essere usato come certificato OAuthTokenIssuer; ad esempio, il Skype for Business Server predefinito può essere usato anche come certificato OAuthTokenIssuer. Il certificato OAUthTokenIssuer può anche essere qualsiasi certificato server Web che includa il nome del dominio SIP nel campo Subject. I due requisiti principali per il certificato utilizzato per l'autenticazione da server a server sono i seguenti: 1)lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer in tutti i Front End Server; e 2) il certificato deve essere di almeno 2048 bit.
  
Se non si dispone di un certificato da utilizzare per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importarlo e quindi utilizzarlo per l'autenticazione da server a server. Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei Front End Server e utilizzare un comando di Windows PowerShell simile al seguente per importare e assegnare il certificato:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Nel comando precedente il parametro Path rappresenta il percorso completo del file del certificato e il parametro Password rappresenta la password assegnata al certificato. Questa procedura deve essere eseguita una sola volta: il servizio di replica di Skype for Business Server creerà automaticamente un set di attività pianificate che decrittograferanno e distribuiranno il certificato in tutti i Front End Server.
  
In alternativa, è possibile utilizzare come certificato di autenticazione da server a server un certificato esistente. Come già specificato, è possibile utilizzare a tale scopo il certificato predefinito. La coppia seguente di comandi di Windows PowerShell recupera il valore della proprietà Thumbprint del certificato predefinito e quindi utilizza tale valore per impostare il certificato predefinito come certificato di autenticazione da server a server:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Nel comando precedente, il certificato recuperato è configurato per funzionare come certificato di autenticazione da server a server globale. ciò significa che il certificato verrà replicato e utilizzato da tutti i Front End Server. Anche in questo caso, questo comando deve essere eseguito una sola volta e solo in uno dei Front End Server. Anche se tutti i Front End Server devono utilizzare lo stesso certificato, non è consigliabile configurare il certificato OAuthTokenIssuer in ogni Front End Server. Configurare invece il certificato una sola volta, quindi lasciare che il server Skype for Business Server di replica si occupi della copia del certificato in ogni server.
  
Il cmdlet Set-CsCertificate utilizza il certificato in questione e configura immediatamente il certificato in modo che agirà come certificato OAuthTokenIssuer corrente. (Skype for Business Server conserva due copie di un tipo di certificato: il certificato corrente e il certificato precedente. Se è necessario che il nuovo certificato inizi immediatamente a fungere da certificato OAuthTokenIssuer, è necessario utilizzare il cmdlet Set-CsCertificate.
  
È inoltre possibile utilizzare il cmdlet Set-CsCertificate per "rollare" un nuovo certificato. "Rolling" un certificato significa semplicemente configurare un nuovo certificato in modo che diventi il certificato OAuthTokenIssuer corrente in un momento specificato. Ad esempio, questo comando recupera il certificato predefinito e quindi configura il certificato in modo che prenda il controllo come certificato OAuthTokenIssuer corrente a partire dal 1° luglio 2015:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Il 1° luglio 2015, il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato OAuthTokenIssuer "vecchio" verrà configurato come certificato precedente.
  
Se non si desidera utilizzare Windows PowerShell, è possibile utilizzare la console MMC Certificati per esportare un certificato da un Front End Server e quindi importarlo in tutti gli altri Front End Server. Se si sceglie questa soluzione, esportare la chiave privata insieme al certificato.
  
> [!CAUTION]
> In questo caso, la procedura deve essere eseguita in ogni Front End Server. Quando si esportano e si importano certificati in questo Skype for Business Server il certificato non verrà replicato in ogni Front End Server. 
  
Dopo l'importazione del certificato in tutti i Front End Server, è possibile assegnare tale certificato utilizzando la Distribuzione guidata di Skype for Business Server anziché Windows PowerShell. Per assegnare un certificato utilizzando la Distribuzione guidata, eseguire le operazioni seguenti in un computer in cui è stata installata la Distribuzione guidata:
  
1. Fare clic sul pulsante Start, scegliere Tutti i programmi, **Skype for Business Server** e quindi fare clic Skype for Business Server **distribuzione guidata.**
    
2. Nella Distribuzione guidata fare clic **su Installa o aggiorna Skype for Business Server sistema**.
    
3. Nella pagina Skype for Business Server, fare clic sul **pulsante Esegui** sotto l'intestazione **Passaggio 3: Richiesta, installazione o assegnazione di certificati**. Nota: se nel computer sono stati già installati certificati, anziché il pulsante **Esegui** sarà disponibile il pulsante **Riesegui**.
    
4. Nella Configurazione guidata certificati selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **Assegna certificato**.
    
5. Nella pagina **Assegnazione certificato** della procedura guidata Assegnazione certificato fare clic su **Avanti**.
    
6. Nella pagina **Archivio certificati** selezionare il certificato da utilizzare per l'autenticazione da server a server e quindi fare clic su **Avanti**.
    
7. Nella pagina Riepilogo assegnazione certificato fare clic su **Avanti**.
    
8. Nella pagina Esecuzione comandi in corso fare clic su **Fine**.
    
9. Chiudere la Creazione guidata certificati e la Distribuzione guidata.
    

