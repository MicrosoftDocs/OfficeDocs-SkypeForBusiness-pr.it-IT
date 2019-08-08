---
title: Visualizzare i record di utilizzo PSTN in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Riepilogo: informazioni su come visualizzare i record di utilizzo PSTN usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.'
ms.openlocfilehash: bbc9b7f174ff4b6710009af47dbdcd20e12334d4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240245"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Visualizzare i record di utilizzo PSTN in Skype for business

**Riepilogo:** Informazioni su come visualizzare i record di utilizzo PSTN usando il pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.

Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti di un'organizzazione. Per informazioni dettagliate, vedere [record sull'utilizzo PSTN](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) nella documentazione relativa alla pianificazione.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Skype for Business Server

1. Aprire il pannello di controllo di Skype for Business Server.

2. Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **utilizzo PSTN**.

3. Nella pagina **uso PSTN** evidenziare il record di utilizzo PSTN che si vuole visualizzare, fare clic su **modifica** e quindi su **Mostra dettagli**.

    > [!NOTE]
    > Una pagina di sola lettura del record di utilizzo PSTN selezionato Mostra le route associate e i criteri vocali associati.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Per visualizzare le informazioni sull'utilizzo PSTN usando i cmdlet di Skype for Business Server Management Shell

- Per visualizzare informazioni su tutti gli usi PSTN, digitare il comando seguente in Skype for Business Server Management Shell e quindi premere INVIO:

  ```
  Get-CsPstnUsage
  ```

    Questo comando restituisce informazioni simili a quelle seguenti:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Vedere anche

[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)

