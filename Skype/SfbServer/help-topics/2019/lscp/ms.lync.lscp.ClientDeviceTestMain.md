---
title: Dispositivo di test
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: È possibile aggiungere un dispositivo di test nella pagina Dispositivo di test e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando aggiungi un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di test del Pannello Skype for Business Server controllo.
ms.openlocfilehash: 3b9fff9a94453cfd6ec8dd59e5979cf6c7d7a0c2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585482"
---
# <a name="test-device"></a>Dispositivo di test

È possibile aggiungere un dispositivo di test nella pagina **Dispositivo di test** e quindi utilizzarlo per verificare le funzionalità dei nuovi aggiornamenti prima di distribuirli nei dispositivi di produzione. Puoi testare un dispositivo a livello globale (in tutto l'ambiente) o all'interno di un singolo sito. Per identificare un dispositivo di test, utilizzare il relativo indirizzo MAC (Media Access Control) o il numero di serie. Quando aggiungi un dispositivo, questo viene visualizzato nell'elenco nella pagina Dispositivo di **test** del Pannello Skype for Business Server controllo.

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

  - **Elimina** Questa opzione elimina tutti i dispositivi di test selezionati.

- **Aggiorna** È possibile aggiornare l'elenco dei dispositivi di test per verificare lo stato delle opzioni di tutti i dispositivi di test.

Per informazioni dettagliate sui dispositivi di test, vedere [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) nella documentazione relativa alle operazioni.
## <a name="see-also"></a>Vedere anche

[Dispositivo di test: crearne uno nuovo o modificarne uno esistente](ms.lync.lscp.ClientDeviceTestEdit.md)

[New-CsTestDevice](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[Set-CsTestDevice](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[Visualizzare gli aggiornamenti software per i dispositivi nell'organizzazione](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)