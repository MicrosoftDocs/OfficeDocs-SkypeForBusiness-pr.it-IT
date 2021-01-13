---
title: Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server
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
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: "Riepilogo: informazioni su come aggiungere ulteriori database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente e informazioni sui passaggi aggiuntivi necessari dopo aver effettuato la patch o l'aggiornamento di un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server."
ms.openlocfilehash: 444194c9cda5f4c3f82e6f3f7698395dce1a5d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826366"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server

Utilizzare la procedura descritta in questo articolo per aggiungere ulteriori database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente in Skype for Business Server e scoprire i passaggi aggiuntivi necessari dopo aver effettuato la patch o l'aggiornamento di un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Aggiungere database a un gruppo di disponibilità AlwaysOn 

1. Aprire SQL Server Management Studio e passare al gruppo di disponibilità AlwaysOn. Eseguire il failover sulla replica primaria.
    
2. In Generatore di topologie impostare il nome di dominio completo di SQL Server del gruppo di disponibilità AlwaysOn sul nome di dominio completo del nodo principale del gruppo.
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK**.
    
   - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.
    
   - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo principale del gruppo di disponibilità AlwaysOn.
    
3. Pubblicare la topologia. Dal menu **azione** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
4. Utilizzare SQL Server Management Studio per aggiungere il nuovo database al gruppo di disponibilità AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patch o aggiornamento di un SQL Server in un gruppo di disponibilità AlwaysOn

Dopo aver eseguito l'applicazione di patch a un server back-end che fa parte di un gruppo di disponibilità AlwaysOn, è necessario ripubblicare la topologia.

1. Installare l'aggiornamento nel server o nei server Skype for business.
    
2. Eseguire il seguente comando di PowerShell in Skype for Business Management Shell (connesso con un account autorizzato per applicare le modifiche ai database di SQL AlwaysOn) come indicato di seguito:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Dove [sqlpool.contoso.com] viene sostituito con il nome di dominio completo (FQDN) del gruppo di disponibilità AlwaysOn.
