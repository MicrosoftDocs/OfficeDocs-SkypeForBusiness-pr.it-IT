---
title: Dispositivo di test crearne uno nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
ROBOTS: NOINDEX, NOFOLLOW
description: La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (nell'intero ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di test del Pannello di controllo di Skype for Business Server.
ms.openlocfilehash: e1a8c570714b1096d14ac49260922c1a6dc3fecc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830326"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo di test: crearne uno nuovo o modificarne uno esistente

La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (nell'intero ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di **test** del Pannello di controllo di Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuovo dispositivo di test** o **Modifica dispositivo di test** è possibile eseguire le attività seguenti:

- Aggiungere un nuovo dispositivo di test.

- Modificare le proprietà di un dispositivo di test esistente.

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (globale o sito) del dispositivo di test.

- **Name** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Nome dispositivo** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Tipo di identificatore** Puoi selezionare il metodo da usare per identificare il dispositivo selezionando una delle opzioni seguenti:

  - **Indirizzo MAC**

  - **Numero di serie**

- **Identificatore univoco** Puoi digitare l'indirizzo MAC o il numero di serie del dispositivo.

Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.
## <a name="see-also"></a>Vedere anche

[Dispositivo di test](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
