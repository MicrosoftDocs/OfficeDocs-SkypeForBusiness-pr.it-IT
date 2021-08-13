---
title: Criteri conferenza
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
description: Il criterio di conferenza definisce le caratteristiche e le funzionalità disponibili agli utenti durante una conferenza, detta anche riunione.
ms.openlocfilehash: a0acc18e27942c9a7b7c1198ee8372e47bd8fb79d34e3f94320cde441331e2bf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342281"
---
# <a name="conferencing-policy"></a>Criteri conferenza

Il criterio di conferenza definisce le caratteristiche e le funzionalità disponibili agli utenti durante una conferenza, detta anche riunione.

I criteri di conferenza includono il criterio globale e, facoltativamente, uno o più criteri per sito e utente:

- **Criteri globali:** Il criterio globale viene creato per impostazione predefinita. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.

- **Criteri sito (facoltativo):** È possibile creare uno o più criteri di conferenza del sito, ognuno dei quali si applica a un sito specifico. I criteri sito prevalgono sul criterio globale.

- **Criteri utente (facoltativo):** È possibile creare uno o più criteri di conferenza utente, ognuno dei quali si applica a un utente o a un gruppo di utenti specifico. I criteri utente hanno la priorità sul criterio globale e sui criteri sito.

La pagina **Criteri conferenza** mostra tutti i criteri di conferenza definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:

- Creare un nuovo criteri di conferenza sito o di conferenza utente

- Modificare il criterio globale o un criterio sito o utente esistente

- Eliminare un criterio sito o utente

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo criterio di conferenza del sito o criteri di conferenza utente.

- **Modifica** Apre il criterio di conferenza selezionato per modificarlo, seleziona tutti i criteri conferenza nell'elenco o elimina il criterio sito o il criterio utente selezionato.

    > [!NOTE]
    > Per il criterio globale, **Elimina** consente di riportare le impostazioni ai valori predefiniti.

- **Aggiorna** Aggiorna l'elenco dei criteri conferenza.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Identifica il criterio di conferenza.

- **Ambito** Identifica l'ambito dei criteri di conferenza: globale, sito o utente.

- **Collaborazione dati** Selezionato se il criterio di conferenza specifica che la collaborazione dati è consentita nelle conferenze.

- **Condivisione applicazioni** Selezionato se il criterio di conferenza specifica che la condivisione delle applicazioni è consentita nelle conferenze.

- **Audio** Selezionato se il criterio di conferenza specifica che l'audio è consentito nelle conferenze.

- **Video** Selezionato se il criterio di conferenza specifica che il video è consentito nelle conferenze.

- **PSTN** Selezionato se il criterio di conferenza specifica che le conferenze telefoniche con accesso esterno PSTN sono consentite.

- **Registrazione** Selezionato se il criterio di conferenza specifica che la registrazione è consentita nelle conferenze.

Per informazioni dettagliate sulle caratteristiche e sulle funzionalità di conferenza, vedere [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri di conferenza, vedere [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) nella documentazione relativa alle operazioni.