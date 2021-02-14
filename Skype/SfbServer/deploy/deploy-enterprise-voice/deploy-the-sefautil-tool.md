---
title: Distribuire lo strumento SEFAUtil in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Distribuzione dello strumento SEFAUtil in Skype for Business Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812386"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Distribuire lo strumento SEFAUtil in Skype for Business
 
Distribuzione dello strumento SEFAUtil in Skype for Business Server.
  
Per distribuire e gestire la risposta alle chiamate di gruppo, è necessario usare la versione Skype for Business Server dello strumento SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil. Scaricalo qui: [Unified Communications Managed API 5.0 Runtime.](https://www.microsoft.com/download/details.aspx?id=47344) Puoi anche scaricare UCMA 5 SDK, che include il runtime, qui: [UCMA 5.0 SDK.](https://www.microsoft.com/download/details.aspx?id=47345)
  
È possibile eseguire lo strumento SEFAUtil in qualsiasi pool Front End della distribuzione. Per eseguire lo strumento SEFAUtil, è necessario eseguire i passaggi 1, 2 e 3 dalla Distribuzione guidata di Skype for Business nel computer dell'applicazione attendibile. SEFAUtil richiede che sia presente l'archivio di configurazione locale, nonché un certificato.
  
> [!NOTE]
> Per altri dettagli sull'esecuzione di SEFAUtil, vedi l'articolo del blog "[Come eseguire SEFAutil?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Per distribuire SEFAUtil

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**
    
3. Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. Se necessario, definire un pool di applicazioni attendibili per il pool Front End in cui si prevede di eseguire SEFAUtil. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN pool: FQDN del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un pool o un server Front End Skype for Business).
    > FQDN funzione di registrazione pool: FQDN del server Front End Skype for Business o del pool associato a questo pool di applicazioni.
    > Sito pool: ID sito del sito in cui si trova il pool.

4. Definire lo strumento SEFAUtil come applicazione attendibile. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Se necessario, è possibile utilizzare una porta diversa. 
  
5. Abilitare la topologia con le modifiche apportate. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   Enable-CsTopology
   ```

6. Se non lo hai già fatto, scarica la versione Skype [](https://www.microsoft.com/download/details.aspx?id=52631)for Business Server dello strumento SEFAUtil da questo percorso e installala nel pool di applicazioni attendibili creato nel passaggio 3.
    
7. Verificare che lo strumento SEFAUtil sia in esecuzione correttamente, come indicato di seguito: 
    
    a. Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.
    
    b. Visualizzare le impostazioni di inoltro di chiamata di un utente. Nella riga di comando digitare il comando seguente:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.
    

