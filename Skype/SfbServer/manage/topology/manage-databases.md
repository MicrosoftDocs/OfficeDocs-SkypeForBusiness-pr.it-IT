---
title: Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: "Riepilogo: informazioni su come aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente e informazioni sui passaggi aggiuntivi necessari dopo la patch o l'aggiornamento di un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server."
ms.openlocfilehash: 579b00047a9966e3ce991863506f5686d8a2d520
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817137"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server

Seguire i passaggi di questo articolo per aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente in Skype for Business Server e scoprire i passaggi aggiuntivi necessari dopo la patch o l'aggiornamento di un server back-end che fa parte di un AlwaysOn Gruppo di disponibilità in Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Aggiungere database a un gruppo di disponibilità AlwaysOn 

1. Aprire SQL Server Management Studio e passare al gruppo di disponibilità AlwaysOn. Non superarlo nella replica primaria.
    
2. In Generatore di topologie impostare il nome di dominio completo di SQL Server del gruppo di disponibilità AlwaysOn sul nome di dominio completo del nodo principale di tale gruppo.
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente**e fare clic su **OK**.
    
   - Espandi Skype for Business Server, Espandi la topologia ed Espandi gli **archivi di SQL Server**. Fare clic con il pulsante destro del mouse sull'archivio SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **modifica proprietà**.
    
   - Nella parte inferiore della pagina, nella casella **FQDN di SQL Server** , digitare il nome di dominio completo del nodo principale del gruppo di disponibilità AlwaysOn.
    
3. Pubblicare la topologia. Nel menu **azioni** fare clic su **topologia** e quindi su **pubblica**. Nella pagina di conferma fare clic su **Avanti**.
    
4. Usare SQL Server Management Studio per aggiungere il nuovo database al gruppo di disponibilità AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Patch o aggiornamento di un server SQL in un gruppo di disponibilità AlwaysOn

Dopo aver patchato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn, è necessario ripubblicare la topologia.

1. Installare l'aggiornamento in un server o server Skype for business.
    
2. Eseguire il comando di PowerShell seguente in Skype for Business Management Shell (effettuato l'accesso con un account autorizzato a applicare le modifiche apportate ai database SQL AlwaysOn) nel modo seguente:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Dove [sqlpool.contoso.com] viene sostituito con il nome di dominio completo (FQDN) del gruppo di disponibilità AlwaysOn.
