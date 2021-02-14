---
title: Dispositivo di test
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (nell'intero ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di test del Pannello di controllo di Skype for Business Server.
ms.openlocfilehash: fd32fafd3b334344fe90c28e130e016dfbcf5043
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819046"
---
# <a name="test-device"></a>Dispositivo di test

È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (nell'intero ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di **test** del Pannello di controllo di Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Dispositivo di test** è possibile eseguire le attività seguenti:

- Aggiungere un dispositivo di test a livello globale o per un sito specifico.

- Modificare le opzioni per un dispositivo di test esistente.

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Nuovo** È possibile aggiungere un nuovo dispositivo di test con l'ambito seguente:

  - Globale

  - Sito

- **Modifica** È possibile modificare le opzioni di un dispositivo di test nell'elenco. Usando questa voce, è possibile scegliere tra le opzioni seguenti:

  - **Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni per un dispositivo di test.

  - **Seleziona tutto** Questa opzione consente di selezionare tutti i dispositivi di test nell'elenco.

  - **Elimina** Questa opzione consente di eliminare tutti i dispositivi di test selezionati.

- **Aggiorna** È possibile aggiornare l'elenco dei dispositivi di test per verificare lo stato delle opzioni di tutti i dispositivi di test.

Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.
## <a name="see-also"></a>Vedere anche

[Dispositivo di test: crearne uno nuovo o modificarne uno esistente](test-device-create-new-or-edit-existing.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
