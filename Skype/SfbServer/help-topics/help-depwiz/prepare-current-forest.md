---
title: Preparare la foresta corrente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Per preparare la foresta di Servizi di dominio Active Directory, è necessario estendere correttamente lo schema, come descritto nell'argomento Running Schema Preparation, e verificare che lo schema sia stato replicato.
ms.openlocfilehash: 94d41a993b2fe976ef7ede885d277c00417ff7dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103462"
---
# <a name="prepare-current-forest"></a>Preparare la foresta corrente

Per preparare la foresta di Servizi di dominio Active Directory, è necessario estendere correttamente lo schema, come descritto nell'argomento [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)e verificare che lo schema sia stato replicato.

Dopo aver completato queste operazioni prerequisite, è possibile iniziare con il **Passaggio 3: Preparazione della foresta corrente**. Per preparare la foresta, eseguire l'accesso a un computer nella radice della foresta come membri del gruppo Domain Admins in tale radice o come membri del gruppo Enterprise Admins per la foresta che si sta preparando.

1. Dal **Passaggio 3: Preparazione della foresta corrente** della Distribuzione guidata, fare clic su **Esegui**.

2. Nella pagina **Prepara foresta** fare clic su **Avanti**.

    > [!NOTE]
    > La preparazione della foresta consente di scegliere dove posizionare i gruppi universali per Skype for Business Server 2015. Scegliere una posizione conforme ai requisiti dell'organizzazione.

3. Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**. Verificare che non vi siano errori. Esaminare gli avvisi per stabilire se siano previsti e normali per l'infrastruttura di cui si dispone.

4. Nella colonna **Azione** del registro espandere **Forest Prep,** cercare un risultato di esecuzione alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il registro e quindi fare clic **\<Success\>** su **Fine.**

5. Attendere il completamento della replica di Servizi di dominio Active Directory o forzare la replica in tutti i controller di dominio elencati nello snap-in Siti e servizi di **Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio. Forzare la replica tra i controller di dominio in tutti i siti di Active Directory perché la replica all'interno dei siti venga eseguita entro pochi minuti.

    > [!TIP]
    > Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp