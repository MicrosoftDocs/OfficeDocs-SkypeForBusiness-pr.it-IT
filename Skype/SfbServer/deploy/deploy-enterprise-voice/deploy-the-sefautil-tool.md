---
title: Distribuire lo strumento SEFAUtil in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Distribuzione dello strumento SEFAUtil in Skype for Business Server.
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245781"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>Distribuire lo strumento SEFAUtil in Skype for business
 
Distribuzione dello strumento SEFAUtil in Skype for Business Server.
  
Per distribuire e gestire il ritiro delle chiamate di gruppo, è necessario usare la versione di Skype for Business Server dello strumento SEFAUtil. 
  
> [!IMPORTANT]
> Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil. Scaricalo qui: [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344). È anche possibile scaricare il UCMA 5 SDK, che include il runtime, qui: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).
  
È possibile eseguire lo strumento SEFAUtil in qualsiasi pool Front-end della distribuzione. Per eseguire lo strumento SEFAUtil, è necessario eseguire i passaggi 1, 2 e 3 della distribuzione guidata di Skype for business nel computer dell'applicazione attendibile. SEFAUtil richiede che l'archivio di configurazione locale sia presente, oltre a un certificato.
  
> [!NOTE]
> Per altre informazioni sull'uso di SEFAUtil, vedere l'articolo su Blog "[come ottenere SEFAUtil in uso?](https://go.microsoft.com/fwlink/?LinkId=278940)". 
  
### <a name="to-deploy-sefautil"></a>Per distribuire SEFAUtil

1. Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile. Se necessario, definire un pool di applicazioni attendibili per il pool Front-end in cui si prevede di eseguire SEFAUtil. Nella riga di comando eseguire:
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > FQDN del pool: il nome di dominio completo del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un server front-end o un pool di Skype for business).
    > FQDN del registrar del pool: il nome di dominio completo del server front end o del pool di Skype for business associato al pool di applicazioni.
    > Sito del pool: ID sito del sito in cui è ospitato questo pool.

4. Definire lo strumento SEFAUtil come applicazione attendibile. Nella riga di comando eseguire:
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > Se necessario, è possibile usare una porta diversa. 
  
5. Abilitare la topologia con le modifiche apportate. Nella riga di comando eseguire:
    
   ```
   Enable-CsTopology
   ```

6. Se non è già stato fatto, scaricare la versione di Skype for Business Server dello strumento SEFAUtil da [questo percorso](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e installarlo nel pool di applicazioni attendibile creato nel passaggio 3.
    
7. Verificare che lo strumento SEFAUtil sia in uso correttamente, come indicato di seguito: 
    
    un. Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.
    
    b. Visualizzare le impostazioni di inoltro di chiamata di un utente. Nella riga di comando eseguire:
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.
    

