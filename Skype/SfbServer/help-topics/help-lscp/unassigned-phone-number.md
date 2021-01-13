---
title: Numero di telefono non assegnato
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826886"
---
# <a name="unassigned-phone-number"></a>Numero di telefono non assegnato

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

- **Modifica** Consente di aprire l'intervallo di numeri non assegnati selezionato per la modifica, di selezionare tutti gli intervalli di numeri non assegnati nell'elenco o di eliminare l'intervallo di numeri non assegnati selezionato.

- **Spostamento verso l'alto** Sposta l'intervallo di numeri non assegnati selezionato in alto nell'elenco in modo che Skype for Business Server lo trovi prima e applichi l'azione specificata prima di applicare le azioni specificate per gli altri intervalli nell'elenco.

    > [!NOTE]
    > Skype for Business Server esegue la ricerca nella tabella dei numeri non assegnati dall'alto verso il basso e utilizza il primo intervallo che corrisponde al numero non assegnato. Se, ad esempio, per un intervallo è specificata un'azione "ultimo tentativo", assicurarsi che tale intervallo si trovi alla fine dell'elenco.

- **Spostamento verso il basso** Sposta l'intervallo di numeri non assegnati selezionato in basso nell'elenco.

- **Commit all** Consente di salvare tutte le modifiche apportate agli intervalli di numeri non assegnati.

    > [!IMPORTANT]
    > Questo comando consente di salvare tutte le modifiche eseguite nelle pagine **Nuovo numero non assegnato** e **Modifica numero non assegnato**.

- **Aggiorna** Consente di aggiornare l'elenco degli intervalli di numeri non assegnati.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Nome univoco che identifica l'intervallo di numeri non assegnati.

- **Stato** Visualizza quali intervalli di numeri sono stati salvati nel database e quali no.

- **Intervallo di avvio** Il numero iniziale dell'intervallo di numeri non assegnati.

- **Intervallo finale** Il numero finale dell'intervallo di numeri non assegnati.

- **Destinazione** ID del servizio dell'applicazione che ospita l'applicazione annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.

- **Annuncio** L'annuncio che verrà riprodotto per questo intervallo di numeri non assegnati.

Per informazioni dettagliate sulle caratteristiche e le funzionalità di annuncio, vedere [Plan for the annuncio Application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.


