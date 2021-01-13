---
title: Assegnazione di un certificato di autenticazione da server a server a Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Riepilogo: assegnazione di un certificato di autenticazione da server a server per Skype for Business Server.'
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828506"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Assegnazione di un certificato di autenticazione da server a server a Skype for Business Server
**Riepilogo:** Assegnare un certificato di autenticazione da server a server per Skype for Business Server.
  
Per determinare se un certificato di autenticazione da server a server è già stato assegnato a Skype for Business Server, eseguire il comando seguente da Skype for Business Server Management Shell:
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

Se non vengono restituite informazioni sui certificati, è necessario assegnare un certificato dell'autorità emittente di token prima di poter utilizzare l'autenticazione da server a server. Come regola generale, qualsiasi certificato di Skype for Business Server può essere utilizzato come certificato di OAuthTokenIssuer; ad esempio, il certificato predefinito di Skype for Business Server può essere utilizzato anche come certificato di OAuthTokenIssuer. Il certificato OAUthTokenIssuer può anche essere qualsiasi certificato del server Web che include il nome del dominio SIP nel campo Subject. I due requisiti principali per il certificato utilizzato per l'autenticazione da server a server sono i seguenti: 1) lo stesso certificato deve essere configurato come certificato OAuthTokenIssuer su tutti i Front End Server; 2) il certificato deve essere almeno pari a 2048 bit.
  
Se non si dispone di un certificato da utilizzare per l'autenticazione da server a server, è possibile ottenere un nuovo certificato, importarlo e quindi utilizzarlo per l'autenticazione da server a server. Dopo aver richiesto e ottenuto il nuovo certificato, è possibile accedere a uno dei Front End Server e utilizzare un comando di Windows PowerShell simile al seguente per importare e assegnare il certificato:
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

Nel comando precedente il parametro path rappresenta il percorso completo del file di certificato e il parametro password rappresenta la password assegnata al certificato. Questa procedura deve essere eseguita una sola volta: il servizio di replica di Skype for Business Server creerà automaticamente una serie di attività pianificate che decifrano e distribuiscono il certificato in tutti i Front End Server.
  
In alternativa, è possibile utilizzare come certificato di autenticazione da server a server un certificato esistente. Come già specificato, è possibile utilizzare a tale scopo il certificato predefinito. La coppia seguente di comandi di Windows PowerShell recupera il valore della proprietà Thumbprint del certificato predefinito e quindi utilizza tale valore per impostare il certificato predefinito come certificato di autenticazione da server a server:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

Nel comando precedente, il certificato recuperato è configurato per funzionare come certificato di autenticazione da server a server globale. Questo significa che il certificato verrà replicato e utilizzato da tutti i Front End Server. Di nuovo, questo comando deve essere eseguito solo una volta e solo in uno dei Front End Server. Anche se tutti i Front End Server devono utilizzare lo stesso certificato, non è necessario configurare il certificato OAuthTokenIssuer in ogni Front End Server. Invece, configurare il certificato una volta, quindi lasciare che il server di replica di Skype for Business Server si occupi di copiare il certificato in ogni server.
  
Il cmdlet Set-CsCertificate prende il certificato in questione e configura immediatamente il certificato in modo che funga da certificato OAuthTokenIssuer corrente. (Skype for Business Server conserva due copie di un tipo di certificato: il certificato corrente e il certificato precedente). Se è necessario che il nuovo certificato cominci subito a fungere da certificato OAuthTokenIssuer, è necessario utilizzare il cmdlet Set-CsCertificate.
  
È inoltre possibile utilizzare il cmdlet Set-CsCertificate per "eseguire il rollforward" di un nuovo certificato. "Rolling" un certificato significa semplicemente che è necessario configurare un nuovo certificato per diventare il certificato OAuthTokenIssuer corrente in un determinato momento. Ad esempio, questo comando consente di recuperare il certificato predefinito e quindi di configurare il certificato in modo che venga rilevato come certificato OAuthTokenIssuer corrente al 1 ° luglio 2015:
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Il 1 ° luglio 2015, il nuovo certificato verrà configurato come certificato OAuthTokenIssuer corrente e il certificato OAuthTokenIssuer "vecchio" verrà configurato come certificato precedente.
  
Se non si desidera utilizzare Windows PowerShell, è possibile utilizzare la console MMC Certificati per esportare un certificato da un Front End Server e quindi importarlo in tutti gli altri Front End Server. Se si sceglie questa soluzione, esportare la chiave privata insieme al certificato.
  
> [!CAUTION]
> In questo caso, la procedura deve essere eseguita in ogni Front End Server. Quando si esporta e si importano certificati in questo modo, Skype for Business Server non replica il certificato in ogni Front End Server. 
  
Dopo che il certificato è stato importato in tutti i Front End Server, tale certificato può essere assegnato tramite la distribuzione guidata di Skype for Business Server invece di Windows PowerShell. Per assegnare un certificato utilizzando la Distribuzione guidata, eseguire le operazioni seguenti in un computer in cui è stata installata la Distribuzione guidata:
  
1. Fare clic sul pulsante Start, scegliere tutti i programmi, fare clic su **Skype for Business Server** e quindi fare clic su **Skype for Business Server Deployment Wizard**.
    
2. Nella distribuzione guidata, fare clic su **Installa o aggiorna il sistema di Skype for Business Server**.
    
3. Nella pagina Skype for Business Server fare clic sul pulsante **Esegui** al di sotto del titolo **passaggio 3: richiesta, installazione o assegnazione dei certificati**. Nota: se nel computer sono stati già installati certificati, anziché il pulsante **Esegui** sarà disponibile il pulsante **Riesegui**.
    
4. Nella Configurazione guidata certificati selezionare il certificato **OAuthTokenIssuer** e quindi fare clic su **Assegna certificato**.
    
5. Nella pagina **Assegnazione certificato** della procedura guidata Assegnazione certificato fare clic su **Avanti**.
    
6. Nella pagina **Archivio certificati** selezionare il certificato da utilizzare per l'autenticazione da server a server e quindi fare clic su **Avanti**.
    
7. Nella pagina Riepilogo assegnazione certificato fare clic su **Avanti**.
    
8. Nella pagina Esecuzione comandi in corso fare clic su **Fine**.
    
9. Chiudere la Creazione guidata certificati e la Distribuzione guidata.
    

