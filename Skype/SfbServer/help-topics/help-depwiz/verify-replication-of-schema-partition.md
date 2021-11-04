---
title: Verificare la replica della partizione dello schema
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: "Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta di Servizi di dominio Active Directory, eseguire le operazioni seguenti:"
ms.openlocfilehash: aa66f77c4a6282c3cbe2315bdd138e90bedc3495
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748272"
---
# <a name="verify-replication-of-schema-partition"></a>Verificare la replica della partizione dello schema
 
Per verificare che l'estensione dello schema sia stata replicata correttamente nella foresta di Servizi di dominio Active Directory, eseguire le operazioni seguenti:
  
1. Accedere a un controller di dominio (diverso dal controller di dominio che contiene il ruolo di master schema) nella foresta di Servizi di dominio Active Directory, in cui le estensioni dello schema sono state applicate come membri del gruppo Enterprise Admins.
    
2. Aprire ADSI Edit: fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **ADSI Edit**.
    
    > [!TIP]
    > In alternativa, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **adsiedit.msc** per avviare ADSI Edit.
  
3. Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su ADSI Edit.
    
4. Scegliere **Connetti a** dal menu **Azione**.
    
5. Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.
    
6. Nel contenitore Schema individuare la voce CN=ms-RTC-SIP-SchemaVersion. Se questo oggetto è presente e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non è presente o i valori degli attributi **rangeUpper** e **rangeLower** sono diversi da quelli specificati, lo schema non è stato modificato né replicato.
    
> [!NOTE]
> Se dalla verifica della replica dello schema ancora non risulta un esito positivo, attendere circa 15 minuti e quindi ripetere la verifica. La replica di Active Directory si basa su un modello di coerenza lento e può verificarsi una certa latenza di replica, in base a una serie di fattori nel server e nell'infrastruttura. 
  

