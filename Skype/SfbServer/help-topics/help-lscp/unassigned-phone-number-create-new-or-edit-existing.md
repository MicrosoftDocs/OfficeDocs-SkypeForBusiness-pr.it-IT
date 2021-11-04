---
title: Numero di Telefono non assegnato Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: a8038c1b3fb9b09b3c8f45b51b412c45dc3731f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746372"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numero di telefono non assegnato: crearne uno nuovo o modificarne uno esistente

I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.

> [!IMPORTANT]
> Dopo aver creato un nuovo intervallo di numeri non assegnati o averne modificato uno esistente, fare clic su **OK** per tornare alla pagina **Numero non assegnato**, in cui sono elencati tutti gli intervalli di numeri. Le modifiche eseguite nella pagina **Nuovo intervallo di numeri non assegnati** o **Modifica intervallo di numeri non assegnati** non vengono salvate nel database fino a quando non si fa clic su **Salva tutto** nella pagina **Numero non assegnato**.

## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri non assegnati. Una volta salvato l'intervallo, questo nome non potrà essere modificato.

- **Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri non assegnati. Nel secondo campo digitare il numero finale dell'intervallo.

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

  - Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.

  - Il numero deve corrispondere all'espressione regolare `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` . Questo significa che il numero può iniziare con la stringa (se non si specifica tale stringa verrà aggiunta automaticamente), un segno più (+) e una cifra `tel:` da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.

- **Servizio annunci** Selezionare **Annuncio** per fare in modo  che l'applicazione Annuncio gestirà la chiamata Exchange messaggistica unificata per fare in modo che un Exchange di messaggistica unificata Operatore automatico gestire la chiamata in arrivo.

- Se è stato selezionato **Annuncio** per **Servizio Annuncio**:

  - **FQDN del server di destinazione** Selezionare l'ID del servizio applicazione che esegue l'applicazione Annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.

  - **Annuncio** Selezionare l'annuncio da riprodurre per questo intervallo di numeri non assegnati.

- Se è stata selezionata **Messaggistica unificata di Exchange** per **Servizio Annuncio**:

  - **Operatore automatico numero di telefono** Selezionare il numero di telefono per il Exchange di messaggistica unificata Operatore automatico.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità degli annunci, vedere [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) nella documentazione relativa alle operazioni.