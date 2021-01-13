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
description: "Per preparare un dominio ai server host che eseguono Skype for Business Server o agli utenti di Skype for Business Server, è necessario completare il passaggio 5: preparare il dominio corrente, come descritto nell'argomento utilizzo del programma di installazione per eseguire la preparazione del dominio. Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:"
ms.openlocfilehash: d6e2efb774d7cad653c0a95e0e2863b97efe55ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824936"
---
# <a name="prepare-current-domain"></a>Preparare il dominio corrente

Per preparare un dominio ai server host che eseguono Skype for Business Server o agli utenti di Skype for Business Server, è necessario completare il **passaggio 5: preparare il dominio corrente**, come descritto nell'argomento [utilizzo del programma di installazione per eseguire la preparazione del dominio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:

1. Dalla cartella o dal supporto di installazione di Skype for Business Server, eseguire Setup.exe per avviare la distribuzione guidata di Skype for Business Server.

2. Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

3. Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.

4. Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.

5. Nella colonna **azione** espandere **preparazione dominio**, cercare il **\<Success\>** risultato dell'esecuzione alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic su **fine**.

> [!TIP]
> Se è necessario controllare i file di registro creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata nella directory degli utenti dell'utente di servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di registro sono disponibili in: C:\Users\Administrator.Contoso\AppData\Local\Temp.


