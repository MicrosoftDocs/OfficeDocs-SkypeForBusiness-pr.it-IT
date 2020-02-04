---
title: Preparare il dominio corrente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: "Per preparare un dominio per ospitare server che eseguono Skype for Business Server 2015 o Skype for Business Server gli utenti, è necessario completare il passaggio 5: preparare il dominio corrente, come descritto nell'argomento uso del programma di installazione per eseguire la preparazione del dominio. Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:"
ms.openlocfilehash: 58ff8ff515d171f7d0d1b0c2fb7d653e25c3ad31
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687409"
---
# <a name="prepare-current-domain"></a>Preparare il dominio corrente

Per preparare un dominio per ospitare server che eseguono Skype for Business Server 2015 o Skype for Business Server gli utenti, è necessario completare il **passaggio 5: preparare il dominio corrente**, come descritto nell'argomento [uso del programma di installazione per eseguire la preparazione del dominio](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx). Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:

1. Nella cartella di installazione o nel supporto di Skype for Business Server 2015 eseguire Setup. exe per avviare la distribuzione guidata di Skype for Business Server.

2. Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.

3. Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.

4. Nella pagina **Esecuzione comandi in corso** cercare il messaggio **Stato attività: Completata** e quindi fare clic su **Visualizza registro**.

5. Nella colonna **azione** espandere **domain prep**, cercare un ** \<\> ** risultato di esecuzione di successo alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il log e quindi fare clic su **fine**.

> [!TIP]
> Se è necessario rivedere i file di log creati dalla distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata nella directory degli utenti dell'utente dei servizi di dominio Active Directory che ha eseguito il passaggio. Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di log si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp.


