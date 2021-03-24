---
title: Dispositivo di test Crea nuovo o Modifica esistente
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
description: La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando aggiungi un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di test del Pannello di controllo di Skype for Business Server.
ms.openlocfilehash: 959abca17e208a397cbdd9ad6a69ba241aad4362
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100632"
---
# <a name="test-device-create-new-or-edit-existing"></a>Dispositivo di test: crearne uno nuovo o modificarne uno esistente

La funzionalità Dispositivo di test opera in combinazione con la funzionalità Aggiornamento dispositivi. È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi usare il dispositivo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando aggiungi un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di **test** del Pannello di controllo di Skype for Business Server.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Nuovo dispositivo di test** o **Modifica dispositivo di test** è possibile eseguire le attività seguenti:

- Aggiungere un nuovo dispositivo di test.

- Modificare le proprietà di un dispositivo di test esistente.

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Negli elenchi seguenti sono descritti i menu, i comandi, i campi e le proprietà della pagina.

- **Ambito** Identifica l'ambito (Globale o Sito) del dispositivo di test.

- **Nome** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Nome dispositivo** È possibile aggiungere o modificare il nome del dispositivo di test.

- **Tipo di identificatore** Puoi selezionare il metodo da usare per identificare il dispositivo selezionando una delle opzioni seguenti:

  - **Indirizzo MAC**

  - **Numero di serie**

- **Identificatore univoco** Puoi digitare l'indirizzo MAC o il numero di serie del dispositivo.

Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) nella documentazione relativa alle operazioni.
## <a name="see-also"></a>Vedere anche

[Dispositivo di test](ms.lync.lscp.ClientDeviceTestMain.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)