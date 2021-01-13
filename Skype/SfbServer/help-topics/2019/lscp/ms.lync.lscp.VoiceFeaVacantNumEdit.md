---
title: Numero di telefono non assegnato crearne uno nuovo o modificarne uno esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: a584812b32d99796259bde56838f0193c54b8fac
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812096"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>Numero di telefono non assegnato: crearne uno nuovo o modificarne uno esistente

> [!NOTE]
> La messaggistica unificata di Exchange resta disponibile in Skype for Business Server 2019 quando si integra Skype for business 2019 con Exchange 2013 o Exchange 2016. A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene sottolineata a favore delle funzionalità di segreteria telefonica cloud e operatore automatico cloud.

I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.

> [!IMPORTANT]
> Dopo aver creato un nuovo intervallo di numeri non assegnati o averne modificato uno esistente, fare clic su **OK** per tornare alla pagina **Numero non assegnato**, in cui sono elencati tutti gli intervalli di numeri. Le modifiche eseguite nella pagina **Nuovo intervallo di numeri non assegnati** o **Modifica intervallo di numeri non assegnati** non vengono salvate nel database fino a quando non si fa clic su **Salva tutto** nella pagina **Numero non assegnato**.

## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri non assegnati. Una volta salvato l'intervallo, questo nome non potrà essere modificato.

- **Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri non assegnati. Nel secondo campo digitare il numero finale dell'intervallo.

  - Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.

  - Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.

  - Il numero deve corrispondere all'espressione regolare (Tel:)? ( \+ )? [1-9] \d {0,17} (; EXT = [1-9] \d {0,9} )?. Questo significa che il numero può iniziare con la stringa tel: (se non si specifica la stringa che verrà aggiunta automaticamente), un segno più (+) e una cifra da 1 a 9. Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.

- **Servizio annunci** Fare clic su **annuncio** affinché l'applicazione annuncio gestisca la chiamata in arrivo o la **messaggistica unificata di Exchange** per gestire la chiamata in arrivo di un operatore automatico di messaggistica unificata di Exchange.

- Se è stato selezionato **Annuncio** per **Servizio Annuncio**:

  - **FQDN del server di destinazione** Selezionare l'ID servizio del servizio applicazione che esegue l'applicazione annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.

  - **Annuncio** Selezionare l'annuncio da riprodurre per questo intervallo di numeri non assegnati.

- Se è stata selezionata **Messaggistica unificata di Exchange** per **Servizio Annuncio**:

  - **Numero di telefono dell'operatore automatico** Selezionare il numero di telefono per l'operatore automatico di messaggistica unificata di Exchange.

Per informazioni dettagliate sulle caratteristiche e le funzionalità di annuncio, vedere [Plan for the annuncio Application in Skype for business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.


