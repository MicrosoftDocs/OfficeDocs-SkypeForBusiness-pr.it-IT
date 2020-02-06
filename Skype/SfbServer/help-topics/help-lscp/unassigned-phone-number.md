---
title: Numero di telefono non assegnato
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 9247623bc0c9ebfe6f9556db15d93ea901cb28f5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821898"
---
# <a name="unassigned-phone-number"></a>Numero di telefono non assegnato

I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.

La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati ma viene chiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se ad esempio si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.

> [!IMPORTANT]
> Prima di configurare la tabella dei numeri non assegnati è necessario che sia definito almeno un annuncio o che sia impostato un Operatore automatico di messaggistica unificata di Exchange.

Nella pagina **Numero non assegnato** viene visualizzato un elenco degli intervalli di numeri non assegnati definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Numero non assegnato** è possibile eseguire le attività seguenti:

- Creare un nuovo intervallo di numeri non assegnati

- Modificare un intervallo di numeri non assegnati esistente

- Eliminare un intervallo di numeri non assegnato

- Modificare l'ordine degli intervalli di numeri non assegnati, per determinare quale azione applicare per prima a una chiamata in arrivo corrispondente a un numero non assegnato.

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i comandi presenti nella pagina.

- **Nuovo** Avvia un nuovo intervallo di numeri non assegnati.

- **Modifica** Apre l'intervallo di numeri non assegnati selezionato per la modifica, seleziona tutti gli intervalli di numeri non assegnati nell'elenco o Elimina l'intervallo di numeri non assegnati selezionato.

- **Spostati verso l'alto** Sposta l'intervallo di numeri non assegnati selezionato in alto nell'elenco in modo che Skype for Business Server la trovi prima e applichi l'azione specificata prima di applicare le azioni specificate per altri intervalli nell'elenco.

    > [!NOTE]
    > Skype for Business Server cerca nella tabella numeri non assegnati dall'alto verso il basso e usa il primo intervallo che corrisponde al numero non assegnato. Se, ad esempio, per un intervallo è specificata un'azione "ultimo tentativo", assicurarsi che tale intervallo si trovi alla fine dell'elenco.

- **Spostarsi verso il basso** Sposta l'intervallo di numeri non assegnati selezionato nell'elenco.

- **Commit all** Salva tutte le modifiche apportate agli intervalli di numeri non assegnati.

    > [!IMPORTANT]
    > Questo comando consente di salvare tutte le modifiche eseguite nelle pagine **Nuovo numero non assegnato** e **Modifica numero non assegnato**.

- **Aggiornare** Aggiorna l'elenco degli intervalli di numeri non assegnati.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Nome univoco che identifica l'intervallo di numeri non assegnati.

- **Stato** Mostra quali intervalli di numeri sono stati salvati nel database e quali no.

- **Intervallo di inizio** Numero iniziale dell'intervallo di numeri non assegnati.

- **Intervallo di fine** Numero finale dell'intervallo di numeri non assegnati.

- **Destinazione** ID servizio del servizio applicazione che ospita l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati.

- **Annuncio** L'annuncio che verrà riprodotto per questo intervallo di numeri non assegnati.

Per informazioni dettagliate sulle caratteristiche e le funzionalità degli annunci, vedere [pianificare l'applicazione di annunci in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.


