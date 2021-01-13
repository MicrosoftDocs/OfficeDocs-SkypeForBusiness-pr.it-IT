---
title: Visualizzare i record di utilizzo PSTN in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Riepilogo: informazioni su come visualizzare i record di utilizzo PSTN utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.'
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830536"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Visualizzare i record di utilizzo PSTN in Skype for business

**Riepilogo:** Informazioni su come visualizzare i record di utilizzo PSTN utilizzando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.

Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere effettuata da vari utenti o gruppi di utenti di un'organizzazione. Per informazioni dettagliate, vedere [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) nella documentazione relativa alla pianificazione.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Utilizzo PSTN**.

3. Nella pagina **Utilizzo PSTN** evidenziare i record di utilizzo PSTN che si desidera visualizzare, fare clic su **Modifica** e quindi su **Mostra dettagli**.

    > [!NOTE]
    > In una pagina di sola lettura per il record di utilizzo PSTN selezionato vengono visualizzati le route e i criteri vocali associati.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Per visualizzare le informazioni sull'utilizzo PSTN tramite i cmdlet di Skype for Business Server Management Shell

- Per visualizzare informazioni su tutti gli utilizzi PSTN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:

  ```powershell
  Get-CsPstnUsage
  ```

    Il comando restituisce informazioni simili a quelle riportate di seguito:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Vedere anche

[Creare o modificare criteri vocali e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)

