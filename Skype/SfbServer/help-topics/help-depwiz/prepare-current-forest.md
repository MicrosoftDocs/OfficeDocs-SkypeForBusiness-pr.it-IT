---
title: Preparare la foresta corrente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Per preparare la foresta di servizi di dominio Active Directory, è necessario estendere lo schema, come descritto nell'argomento eseguire la preparazione dello schema e verificare che lo schema sia stato replicato.
ms.openlocfilehash: 4286ff0bd9b3291f631e3466b0e790174807a8bf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687399"
---
# <a name="prepare-current-forest"></a>Preparare la foresta corrente

Per preparare la foresta di servizi di dominio Active Directory, è necessario estendere lo schema, come descritto nell'argomento [eseguire la preparazione dello schema](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)e verificare che lo schema sia stato replicato.

Dopo aver completato queste operazioni preliminari, è possibile iniziare con il **Passaggio 3: Preparazione della foresta corrente**. Per preparare la foresta, eseguire l'accesso a un computer nella radice della foresta come membri del gruppo Domain Admins in tale radice o come membri del gruppo Enterprise Admins per la foresta che si sta preparando.

1. Dal **Passaggio 3: Preparazione della foresta corrente** della Distribuzione guidata, fare clic su **Esegui**.

2. Nella pagina **Prepara foresta** fare clic su **Avanti**.

    > [!NOTE]
    > La preparazione della foresta consente di scegliere dove posizionare i gruppi universali per Skype for Business Server 2015. Scegliere una posizione conforme ai requisiti dell'organizzazione.

3. Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**. Verificare che non vi siano errori. Esaminare gli avvisi per stabilire se siano previsti e normali per l'infrastruttura di cui si dispone.

4. Nella colonna **azione** del log espandere **Forest Prep**, cercare un ** \<\> ** risultato di esecuzione di successo alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.

5. Attendere il completamento della replica di servizi di dominio Active Directory oppure forzare la replica a tutti i controller di dominio elencati nello snap-in **siti e servizi di Active** directory per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio. Forzare la replica tra i controller di dominio in tutti i siti di Active Directory per provocare la replica nei siti in pochi minuti.

    > [!TIP]
    > Se è necessario rivedere i file di log creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente dei servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp


