---
title: Numero di telefono non assegnato Crea nuovo o modifica esistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 51b66f7b3fffaf647970cb29b300b75460b0adce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703911"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numero di telefono non assegnato: crearne uno nuovo o modificarne uno esistente

> [!NOTE]
> La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for business 2019 con Exchange 2013 o Exchange 2016. A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene sottolineata a favore delle caratteristiche del cloud voicemail e dell'operatore automatico cloud.

I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.

> [!IMPORTANT]
> Dopo aver creato un nuovo intervallo di numeri non assegnati o averne modificato uno esistente, fare clic su **OK** per tornare alla pagina **numero non assegnati** che elenca tutti gli intervalli di numeri. Le modifiche apportate nella pagina **nuovo intervallo di numeri non assegnati** o nella pagina **modifica numero non assegnato non assegnati** non vengono salvate nel database finché non si fa clic su **commit tutto** nella pagina **numero non assegnati** .

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri non assegnati. Dopo aver salvato l'intervallo, non è possibile modificare questo nome.

- **Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri non assegnati. Nel secondo campo digitare il numero finale dell'intervallo.

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

  - Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.

  - Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?. Questo significa che il numero può iniziare con la stringa tel: (se non specifichi la stringa che verrà aggiunta automaticamente), un segno più (+) e una cifra da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.

- **Servizio annunci** Selezionare **annuncio** per gestire la chiamata in arrivo o la **messaggistica unificata** di Exchange per avere un operatore automatico di messaggistica unificata di Exchange per gestire la chiamata in arrivo.

- Se è stato selezionato l' **annuncio** per il **servizio annunci**:

  - **Nome di dominio completo del server di destinazione** Selezionare l'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati.

  - **Annuncio** Selezionare l'annuncio da riprodurre per l'intervallo di numeri non assegnati.

- Se è stata selezionata la **messaggistica unificata di Exchange** per il **servizio annunci**:

  - **Numero di telefono dell'operatore automatico** Selezionare il numero di telefono per l'operatore automatico di messaggistica unificata di Exchange.

Per informazioni dettagliate sulle caratteristiche e le funzionalità degli annunci, vedere [pianificare l'applicazione di annunci in Skype for business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.


