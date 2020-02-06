---
title: Eseguire la migrazione dei numeri di accesso esterno
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet Move-CsApplicationEndpoint per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo simile ai numeri di accesso per la chiamata in ingresso creati nell'installazione legacy, come descritto in questo sezione.
ms.openlocfilehash: 5333cc7cb835fc6bf324de9ab12a868f95b72972
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813504"
---
# <a name="migrate-dial-in-access-numbers"></a>Eseguire la migrazione dei numeri di accesso esterno

La migrazione dei numeri di accesso esterno a Skype for Business Server 2019 richiede l'esecuzione del cmdlet **Move-CsApplicationEndpoint** per eseguire la migrazione degli oggetti contatto. Durante l'installazione legacy e il periodo di coesistenza di Skype for Business Server 2019, i numeri di accesso esterno creati in Skype for Business Server 2019 si comportano in modo simile ai numeri di accesso per la chiamata in ingresso creati nell'installazione legacy, come descritto in questo sezione. 

I numeri di accesso esterno creati nell'installazione legacy, ma spostati in Skype for Business Server 2019 o creati in Skype for Business Server 2019 prima, durante o dopo la migrazione, hanno le caratteristiche seguenti:

- Non vengono visualizzati negli inviti alle riunioni di Office Communications Server 2007 R2 e nella pagina numero di accesso esterno.

- Vengono visualizzati gli inviti alle riunioni di installazione legacy e la pagina numero di accesso esterno.

- Visualizzare gli inviti alle riunioni di Skype for Business Server 2019 e la pagina numero di accesso esterno.

- Non è possibile visualizzare o modificare lo strumento di amministrazione di Office Communications Server 2007 R2.

- Può essere visualizzato e modificato nel pannello di controllo installazione legacy e nell'installazione legacy di Management Shell.

- Può essere visualizzato e modificato nel pannello di controllo di Skype for Business Server 2019 e in Skype for Business Server 2019 Management Shell.

- Può essere risequenziata all'interno dell'area geografica usando il cmdlet Set-CsDialinConferencingAccessNumber con il parametro Priority.

È necessario completare la migrazione dei numeri di accesso esterno che puntano al pool di installazione legacy prima di rimuovere la Commissione dal pool di installazione legacy. Se non si completa la migrazione dei numeri di accesso per la chiamata in ingresso, come descritto nella procedura seguente, le chiamate in arrivo ai numeri di accesso avranno esito negativo.

> [!IMPORTANT]
> È necessario eseguire questa procedura prima della disattivazione del pool di installazione legacy. 

> [!NOTE]
> È consigliabile trasferire i numeri di accesso esterno quando l'utilizzo della rete è basso, in caso di un breve periodo di interruzione del servizio. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Per identificare e cambiare i numeri di accesso per la chiamata in ingresso

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server 2019**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Per trasferire ogni numero di accesso esterno a un pool ospitato in Skype for Business Server 2019, dalla riga di comando eseguire: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Aprire il pannello di controllo di Skype for Business Server.

4. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.

5. Fare clic sulla scheda **numero di accesso** esterno. 

6. Verificare che non rimangano numeri di accesso in ingresso per il pool di installazione legacy da cui si esegue la migrazione.

    > [!NOTE]
    > Quando tutti i numeri di accesso esterno puntano al pool di Skype for Business Server 2019, è possibile rimuovere il pool di installazione legacy. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Verificare la migrazione dei numeri di accesso esterno tramite il pannello di controllo di Skype for Business Server

1. Da un account utente assegnato al ruolo **CsUserAdministrator** o **CsAdministrator** , accedere a qualsiasi computer della distribuzione interna. 

2. Aprire il pannello di controllo di Skype for Business Server.

3. Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**.

4. Fare clic sulla scheda **numero di accesso** esterno. 

5. Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Skype for Business Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Verificare la migrazione dei numeri di accesso esterno con Skype for Business Server Management Shell

1. Aprire Skype for Business Server Management Shell.

2. Per restituire tutti i numeri di accesso per le conferenze telefoniche con chiamata in ingresso migrati, dalla riga di comando eseguire:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Verificare che tutti i numeri di accesso per la chiamata in ingresso vengano migrati nel pool ospitati in Skype for Business Server 2019.


