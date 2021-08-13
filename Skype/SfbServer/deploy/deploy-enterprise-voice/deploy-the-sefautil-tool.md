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
ms.openlocfilehash: 5683dab35a51a088b89f410c11bd0713a8256496f85d11c7190d44f82528a3c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331868"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Distribuire lo strumento SEFAUtil in Skype for Business
 
Distribuzione dello strumento SEFAUtil in Skype for Business Server.
  
Per distribuire e gestire la risposta alle chiamate di gruppo, è necessario utilizzare la Skype for Business Server dello strumento SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil. Scaricalo qui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344). Puoi anche scaricare UCMA 5 SDK, che include il runtime, qui: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).
  
È possibile eseguire lo strumento SEFAUtil in qualsiasi pool Front End della distribuzione. Per eseguire lo strumento SEFAUtil, è necessario eseguire i passaggi 1, 2 e 3 dalla Distribuzione guidata di Skype for Business nel computer dell'applicazione attendibile. SEFAUtil richiede che sia presente l'archivio di configurazione locale, nonché un certificato.
  
> [!NOTE]
> Per ulteriori informazioni sull'esecuzione di SEFAUtil, vedere l'articolo del blog "[How to get SEFAutil running?](/archive/blogs/jenstr/how-to-get-sefautil-running)". 
  
### <a name="to-deploy-sefautil"></a>Per distribuire SEFAUtil

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in **Delegate Setup Permissions**.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili. Se necessario, definire un pool di applicazioni attendibili per il pool Front End in cui si prevede di eseguire SEFAUtil. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN pool: FQDN del server o del pool che ospiterà l'applicazione SEFAUtil (in genere Skype for Business server Front End o pool).
    > FQDN di registrazione pool: FQDN del Skype for Business Front End Server o del pool associato a questo pool di applicazioni.
    > Sito pool: ID sito del sito in cui si trova il pool.

4. Definire lo strumento SEFAUtil come applicazione attendibile. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Se necessario, è possibile utilizzare una porta diversa. 
  
5. Abilitare la topologia con le modifiche. Nella riga di comando digitare il comando seguente:
    
   ```powershell
   Enable-CsTopology
   ```

6. Se non l'hai già fatto, scarica la versione Skype for Business Server [](https://www.microsoft.com/download/details.aspx?id=52631)dello strumento SEFAUtil da questo percorso e installala nel pool di applicazioni attendibili creato nel passaggio 3.
    
7. Verificare che lo strumento SEFAUtil sia in esecuzione correttamente, come indicato di seguito: 
    
    a. Eseguire lo strumento dal prompt dei Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.
    
    b. Visualizzare le impostazioni di inoltro di chiamata di un utente. Nella riga di comando digitare il comando seguente:
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.
