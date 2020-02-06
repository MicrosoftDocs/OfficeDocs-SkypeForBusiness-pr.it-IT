---
title: Dispositivo di test Crea nuovo o modifica esistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Il dispositivo può essere testato a livello globale, ovvero in tutto l'ambiente, o in un singolo sito. Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del dispositivo di test del pannello di controllo di Skype for Business Server.
ms.openlocfilehash: 2101fb712d1084506de617ab234e3e8e0a03a961
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794545"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo di test: crearne uno nuovo o modificarne uno esistente

La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Il dispositivo può essere testato a livello globale, ovvero in tutto l'ambiente, o in un singolo sito. Per identificare un dispositivo di test, usare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando si aggiunge un dispositivo, questo viene visualizzato nell'elenco nella pagina del **dispositivo di test** del pannello di controllo di Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Nuovo dispositivo di test** o **Modifica dispositivo di test** è possibile eseguire le attività seguenti:

- Aggiungere un nuovo dispositivo di test.

- Modificare le proprietà di un dispositivo di test esistente.

## <a name="ui-reference"></a>Riferimenti UI

Gli elenchi seguenti descrivono i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (globale o sito) del dispositivo di test.

- **Nome** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Nome dispositivo** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Tipo di identificatore** È possibile selezionare il metodo da usare per identificare il dispositivo selezionando una delle opzioni seguenti:

  - **Indirizzo MAC**

  - **Numero di serie**

- **Identificatore univoco** È possibile digitare l'indirizzo MAC o il numero di serie del dispositivo.

Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](https://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) nella documentazione relativa alle operazioni.
## <a name="see-also"></a>Vedere anche

[Dispositivo di test](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Visualizzare gli aggiornamenti software per i dispositivi dell'organizzazione](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)
