---
title: Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: 'Riepilogo: informazioni su come aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente e sui passaggi aggiuntivi necessari dopo aver patchato o aggiornato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server.'
ms.openlocfilehash: fe74cd804aff746a3d6c52163ed96d6b270703ce
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827509"
---
# <a name="manage-databases-with-an-alwayson-availability-group-in-skype-for-business-server"></a>Gestire i database con un gruppo di disponibilità AlwaysOn in Skype for Business Server

Utilizzare la procedura descritta in questo articolo per aggiungere altri database di Skype for Business Server a un gruppo di disponibilità AlwaysOn esistente in Skype for Business Server e per informazioni sui passaggi aggiuntivi necessari dopo aver patchato o aggiornato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn in Skype for Business Server.

## <a name="add-databases-to-an-alwayson-availability-group"></a>Aggiungere database a un gruppo di disponibilità AlwaysOn 

1. Aprire SQL Server Management Studio e passare al gruppo di disponibilità AlwaysOn. Eseguire il failover alla replica primaria.
    
2. In Generatore di topologie impostare l SQL Server FQDN del gruppo di disponibilità AlwaysOn sul nome di dominio completo del nodo primario del gruppo.
    
   - Aprire Generatore di topologie, selezionare **Scarica topologia dalla distribuzione esistente** e fare clic su **OK.**
    
   - Espandere Skype for Business Server, espandere la topologia ed espandere SQL Server **archivi**. Fare clic con il pulsante destro del SQL del nuovo gruppo di disponibilità AlwaysOn e scegliere **Modifica proprietà**.
    
   - Nella parte inferiore della pagina, nella casella **SQL Server FQDN,** digitare il nome di dominio completo del nodo primario del gruppo di disponibilità AlwaysOn.
    
3. Pubblicare la topologia. Scegliere **Topologia** dal menu Azione **e** quindi **Pubblica**. Nella pagina di conferma fare clic su **Avanti.**
    
4. Utilizzare SQL Server Management Studio per aggiungere il nuovo database al gruppo di disponibilità AlwaysOn.
    
## <a name="patch-or-update-a-sql-server-in-an-alwayson-availability-group"></a>Applicare patch o aggiornare un SQL Server in un gruppo di disponibilità AlwaysOn

Dopo aver patchato un server back-end che fa parte di un gruppo di disponibilità AlwaysOn, è necessario ripubblicare la topologia.

1. Installare l'aggiornamento nel server Skype for Business server.
    
2. Eseguire il comando di PowerShell seguente in Skype for Business Management Shell (connesso con un account autorizzato in modo appropriato per applicare le modifiche ai database AlwaysOn di SQL) come indicato di seguito:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn [sqlpool.contoso.com] -Verbose
    ```

    Dove [sqlpool.contoso.com] viene sostituito con il nome di dominio completo (FQDN) del gruppo di disponibilità AlwaysOn.
