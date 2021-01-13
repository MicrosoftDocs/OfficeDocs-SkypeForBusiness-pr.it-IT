---
title: Verificare la replica della partizione dello schema
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: "Per verificare la corretta replica dell'estensione dello schema nella foresta di servizi di dominio Active Directory, eseguire le operazioni seguenti:"
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801566"
---
# <a name="verify-replication-of-schema-partition"></a>Verificare la replica della partizione dello schema
 
Per verificare la corretta replica dell'estensione dello schema nella foresta di servizi di dominio Active Directory, eseguire le operazioni seguenti:
  
1. Accedere a un controller di dominio (diverso dal controller di dominio che contiene il ruolo master schema) nella foresta di servizi di dominio Active Directory, in cui sono state applicate le estensioni dello schema come membri del gruppo Enterprise Admins.
    
2. Aprire ADSI Edit: fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione**, quindi **ADSI Edit**.
    
    > [!TIP]
    > In alternativa, fare clic sul pulsante **Start**, scegliere **Esegui** e quindi digitare **adsiedit.msc** per avviare ADSI Edit.
  
3. Nell'albero di Microsoft Management Console (MMC), se non è già selezionato, fare clic su ADSI Edit.
    
4. Scegliere **Connetti a** dal menu **Azione**.
    
5. Nella finestra di dialogo **Impostazioni connessione** selezionare **Schema** in **Selezionare un contesto dei nomi noto** e quindi fare clic su **OK**.
    
6. Nel contenitore Schema individuare la voce CN=ms-RTC-SIP-SchemaVersion. Se questo oggetto è presente e il valore dell'attributo **rangeUpper** è 1150 e il valore dell'attributo **rangeLower** è 3, lo schema è stato aggiornato e replicato correttamente. Se l'oggetto non è presente o i valori degli attributi **rangeUpper** e **rangeLower** sono diversi da quelli specificati, lo schema non è stato modificato né replicato.
    
> [!NOTE]
> Se dalla verifica della replica dello schema ancora non risulta un esito positivo, attendere circa 15 minuti e quindi ripetere la verifica. La replica di Active Directory si basa su un modello di coerenza sciolto e può verificarsi una latenza di replica, in base a un numero di fattori nel server e nell'infrastruttura. 
  

