---
title: Verificare la replica della partizione dello schema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: "Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta dei servizi di dominio Active Directory, eseguire le operazioni seguenti:"
ms.openlocfilehash: 9b055120f33f4bc80b2fdbf163e9ab627927dd54
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191453"
---
# <a name="verify-replication-of-schema-partition"></a>Verificare la replica della partizione dello schema
 
Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta dei servizi di dominio Active Directory, eseguire le operazioni seguenti:
  
1. Accedere a un controller di dominio (ad eccezione del controller di dominio che contiene il ruolo di master schema) nella foresta di servizi di dominio Active Directory in cui sono state applicate le estensioni dello schema come membro del gruppo amministratori aziendali.
    
2. Aprire ADSI Edit: fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **Modifica ADSI**.
    
    > [!TIP]
    > In alternativa, fare clic sul pulsante **Start**e quindi su **Esegui**, digitare **ADSIEdit. msc** per avviare ADSI Edit.
  
3. Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su Modifica ADSI.
    
4. Nel menu **azione** fare clic su **Connetti a**.
    
5. Nella finestra di dialogo **impostazioni di connessione** in **selezionare un contesto di denominazione ben noto**Selezionare **schema**e quindi fare clic su **OK**.
    
6. In contenitore schema cercare CN = ms-RTC-SIP-SchemaVersion. Se l'oggetto esiste e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **RangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non esiste o se i valori degli attributi **rangeUpper** e **RangeLower** non sono specificati, lo schema non è stato modificato o non è stato replicato.
    
> [!NOTE]
> Se il controllo della replica dello schema non mostra ancora una replica corretta, attendere circa 15 minuti e quindi eseguire di nuovo il controllo. La replica di Active Directory si basa su un modello di coerenza allentato e si può verificare la latenza della replica, in base a diversi fattori nel server e nell'infrastruttura. 
  

