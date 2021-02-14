---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet Move-CsApplicationEndpoint per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo analogo ai numeri di accesso esterno creati nell'installazione legacy, come descritto in questa sezione.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752698"
---
# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo analogo ai numeri di accesso esterno creati nell'installazione legacy, come descritto in questa sezione. 

I numeri di accesso esterno creati nell'installazione legacy ma spostati in Skype for Business Server 2019 o creati in Skype for Business Server 2019 prima, durante o dopo la migrazione hanno le caratteristiche seguenti:

- Non sono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina del numero di accesso esterno.

- Vengono visualizzati negli inviti alle riunioni per l'installazione legacy e nella pagina del numero di accesso remoto.

- Vengono visualizzati negli inviti alle riunioni di Skype for Business Server 2019 e nella pagina del numero di accesso remoto.

- Possono essere visualizzati e modificati nello strumento di amministrazione di Office Communications Server 2007 R2.

- Può essere visualizzato e modificato nel Pannello di controllo dell'installazione legacy e nell'installazione legacy di Management Shell.

- Può essere visualizzato e modificato nel Pannello di controllo di Skype for Business Server 2019 e in Skype for Business Server 2019 Management Shell.

- Possono essere risequenziati nell'area tramite il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.

È necessario completare la migrazione dei numeri di accesso esterno che puntano al pool di installazione legacy prima di rimuovere il pool di installazione legacy. Se non si completa la migrazione come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.

> [!IMPORTANT]
> È necessario eseguire questa procedura prima di rimuovere le autorizzazioni per il pool di installazione legacy. 

> [!NOTE]
> È consigliabile spostare i numeri di accesso esterno quando l'utilizzo della rete è ridotto, nel caso si verifichi una breve interruzione dei servizi. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Per identificare e spostare i numeri di accesso esterno

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Microsoft Skype for Business Server 2019** e quindi **Skype for Business Server Management Shell.**

2. Per spostare ogni numero di accesso remoto in un pool ospitato in Skype for Business Server 2019, dalla riga di comando eseguire: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Aprire il Pannello di controllo di Skype for Business Server.

4. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.

5. Fare clic sulla scheda **Numero di accesso esterno**. 

6. Verificare che non rimangano numeri di accesso esterno per il pool di installazione legacy da cui si esegue la migrazione.

    > [!NOTE]
    > Quando tutti i numeri di accesso esterno puntano al pool di Skype for Business Server 2019, è possibile rimuovere le autorizzazioni per il pool di installazione legacy. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verificare la migrazione del numero di accesso remoto tramite il Pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo **CsUserAdministrator** o al ruolo **CsAdministrator** accedere a qualsiasi computer nella distribuzione interna. 

2. Aprire il Pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su **Servizio di conferenza**.

4. Fare clic sulla scheda **Numero di accesso esterno**. 

5. Verificare che tutti i numeri di accesso esterno siano migrati nel pool ospitato in Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificare la migrazione del numero di accesso esterno tramite Skype for Business Server Management Shell

1. Aprire Skype for Business Server Management Shell.

2. Per ottenere un elenco di tutti i numeri di accesso a conferenze telefoniche con accesso esterno di cui è stata eseguita la migrazione, dalla riga di comando eseguire:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verificare che tutti i numeri di accesso esterno siano migrati nel pool ospitato in Skype for Business Server 2019.


