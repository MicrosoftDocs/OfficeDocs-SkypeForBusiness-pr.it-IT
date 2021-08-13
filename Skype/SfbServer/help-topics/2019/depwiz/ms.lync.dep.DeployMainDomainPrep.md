---
title: Preparare il dominio corrente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: "Per preparare un dominio per ospitare server che eseguono utenti di Skype for Business Server o Skype for Business Server, è necessario completare passaggio 5: Preparare il dominio corrente, come descritto nell'argomento Using Setup to Run Domain Preparation. Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:"
ms.openlocfilehash: e2741bb3c80f73e0a194f37633fa8d572ca8817d32b34bd2f138c1daca888ccd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325383"
---
# <a name="prepare-current-domain"></a>Preparare il dominio corrente

Per preparare un dominio per ospitare server che eseguono utenti di Skype for Business Server o Skype for Business Server, è necessario completare Passaggio **5: Preparare** il dominio corrente, come descritto nell'argomento [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation). Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:

1. Dalla cartella Skype for Business Server o dal supporto di installazione, eseguire Setup.exe per avviare la Skype for Business Server guidata.

2. Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

3. Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.

4. Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

5. Nella colonna **Azione** espandere **Domain Prep**, cercare un risultato di esecuzione alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic **\<Success\>** su **Fine**.

> [!TIP]
> Se è necessario esaminare i file di registro creati dalla Distribuzione guidata Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp.