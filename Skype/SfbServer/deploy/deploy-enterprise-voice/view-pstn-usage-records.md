---
title: Visualizzare i record di utilizzo PSTN in Skype for Business
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
description: 'Riepilogo: informazioni su come visualizzare i record di utilizzo PSTN utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.'
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109832"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Visualizzare i record di utilizzo PSTN in Skype for Business

**Riepilogo:** Informazioni su come visualizzare i record di utilizzo PSTN utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.

Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata (ad esempio interna, locale o interurbana) che può essere effettuata da vari utenti o gruppi di utenti in un'organizzazione. Per informazioni dettagliate, vedere [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) nella documentazione relativa alla pianificazione.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Per visualizzare un record di utilizzo PSTN tramite il Pannello di controllo di Skype for Business Server

1. Aprire il Pannello di controllo di Skype for Business Server.

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

[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business](voice-policy-and-pstn-usage-records.md)