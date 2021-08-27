---
title: Numero di telefono non assegnato
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 1924b6502bac9d15aa328efd9a160701ca74f56e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625468"
---
# <a name="unassigned-phone-number"></a>Numero di telefono non assegnato

> [!NOTE]
> Exchange La messaggistica unificata rimane disponibile Skype for Business Server 2019 quando si integra Skype for Business 2019 con Exchange 2013 o Exchange 2016. A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione di messaggistica unificata di Exchange viene de-enfatizzata a favore delle funzionalità Cloud Voicemail e cloud Operatore automatico.

I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.

La modalità di configurazione della tabella dei numeri non assegnati dipende dal modo in cui si intende utilizzare tale tabella. È possibile configurare la tabella con tutti gli interni validi dell'organizzazione, solo con gli interni non assegnati o con una combinazione di numeri di entrambi i tipi. La tabella dei numeri non assegnati può includere sia numeri assegnati che numeri non assegnati, ma viene richiamata solo se un chiamante compone un numero non assegnato. Se nella tabella dei numeri non assegnati si inseriscono tutti gli interni validi, è possibile specificare l'azione da eseguire quando un utente lascia l'organizzazione, senza alcuna necessità di riconfigurare la tabella. Se nella tabella si inseriscono interni non assegnati, è possibile personalizzare l'azione da eseguire per numeri specifici. Se, ad esempio, si modifica l'interno del servizio di assistenza clienti, è possibile inserire il vecchio numero nella tabella e assegnarlo a un annuncio in cui viene indicato il nuovo numero.

> [!IMPORTANT]
> Prima di configurare la tabella dei numeri non assegnati è necessario che sia definito almeno un annuncio o che sia impostato un Operatore automatico di messaggistica unificata di Exchange.

Nella pagina **Numero non assegnato** viene visualizzato un elenco degli intervalli di numeri non assegnati definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Numero non assegnato** è possibile eseguire le attività seguenti:

- Creare un nuovo intervallo di numeri non assegnati

- Modificare un intervallo di numeri non assegnati esistente

- Eliminare un intervallo di numeri non assegnato

- Modificare l'ordine degli intervalli di numeri non assegnati, per determinare quale azione applicare per prima a una chiamata in arrivo corrispondente a un numero non assegnato.

## <a name="ui-reference"></a>Informazioni sull'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo intervallo di numeri non assegnati.

- **Modifica** Apre l'intervallo di numeri non assegnati selezionato per la modifica, seleziona tutti gli intervalli di numeri non assegnati nell'elenco oppure elimina l'intervallo di numeri non assegnati selezionato.

- **Spostarsi verso l'alto** Sposta l'intervallo di numeri non assegnati selezionato verso l'alto nell'elenco in modo che Skype for Business Server lo trovi prima e applii l'azione specificata prima di applicare le azioni specificate per gli altri intervalli dell'elenco.

    > [!NOTE]
    > Skype for Business Server ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo corrispondente al numero non assegnato. Se, ad esempio, per un intervallo è specificata un'azione "ultimo tentativo", assicurarsi che tale intervallo si trovi alla fine dell'elenco.

- **Sposta giù** Sposta l'intervallo di numeri non assegnati selezionato verso il basso nell'elenco.

- **Commit di tutti** Salva tutte le modifiche apportate agli intervalli di numeri non assegnati.

    > [!IMPORTANT]
    > Questo comando consente di salvare tutte le modifiche eseguite nelle pagine **Nuovo numero non assegnato** e **Modifica numero non assegnato**.

- **Aggiorna** Aggiorna l'elenco degli intervalli di numeri non assegnati.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Nome univoco che identifica l'intervallo di numeri non assegnati.

- **State** Mostra quali intervalli di numeri sono stati salvati nel database e quali no.

- **Intervallo iniziale** Numero iniziale dell'intervallo di numeri non assegnati.

- **Intervallo finale** Numero finale dell'intervallo di numeri non assegnati.

- **Destinazione** ID servizio del servizio applicazione che ospita l'applicazione Annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.

- **Annuncio** Annuncio che verrà riprodotto per questo intervallo di numeri non assegnati.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità degli annunci, vedere [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) nella documentazione relativa alle operazioni.