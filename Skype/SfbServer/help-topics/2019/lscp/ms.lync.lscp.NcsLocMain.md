---
title: Criteri percorso
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.
ms.openlocfilehash: bb7a63e63864b3d342d37fd62b26f806434644b7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824786"
---
# <a name="location-policy"></a>Criteri percorso

I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.

I criteri percorso includono un criterio globale e, facoltativamente, uno o più criteri sito e utente:

- **Criteri globali:** Il criterio globale viene creato per impostazione predefinita. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.

- **Criteri sito (facoltativi):** È possibile creare uno o più criteri percorso sito, ognuno dei quali si applica a un sito specifico. I criteri sito prevalgono sul criterio globale.

- **Criteri utente (facoltativi):** È possibile creare uno o più criteri percorso utente, ognuno dei quali si applica a un utente o a un gruppo di utenti specifico. I criteri utente prevalgono sul criteri globale e i criteri sito.

> [!NOTE]
> È inoltre possibile assegnare criteri percorso a siti di rete, ovvero gruppi di subnet. I criteri percorso assegnati a siti di rete hanno la precedenza su tutti gli altri criteri utente. Per informazioni dettagliate sull'assegnazione di criteri percorso a siti di rete tramite cmdlet, vedere [aggiungere un criterio percorso a un sito di rete in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Per informazioni dettagliate sull'utilizzo del pannello di controllo di Skype for Business Server per assegnare un criterio percorso a un sito di rete, vedere [Configuring Network sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

Nella pagina **Criteri percorso** viene visualizzato un elenco di tutti i criteri percorso definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:

- Creare un nuovo criterio percorso sito o utente

- Modificare il criterio globale o un criterio sito o utente esistente

- Eliminare un criterio sito o utente

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo criterio percorso sito o utente.

- **Modifica** Apre il criterio percorso selezionato per modificarlo, seleziona tutti i criteri percorso nell'elenco o Elimina il criterio sito o utente selezionato.

    > [!NOTE]
    > Per il criterio globale, **Elimina** consente di riportare le impostazioni ai valori predefiniti.

- **Aggiorna** Consente di aggiornare l'elenco dei criteri percorso.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Identifica il criterio percorso.

- **Ambito** Identifica l'ambito del criterio percorso: globale, sito o utente.

- **E9-1-1** Verificato se gli utenti assegnati a questo criterio percorso sono abilitati per il servizio E9-1-1.

- **Posizione** Specifica se agli utenti viene richiesto di immettere le informazioni sulla posizione quando il client esegue la registrazione con Skype for Business Server in una nuova posizione e se visualizzano una dichiarazione di non responsabilità se ignorano la richiesta senza immettere le informazioni sulla posizione.

- **Utilizzo PSTN** Specifica l'utilizzo della rete PSTN (Public Switched Telephone Network) utilizzato per determinare la route vocale utilizzata per instradare le chiamate di emergenza provenienti dai client che utilizzano questo profilo.

- **Numero E9-1-1** Specifica il numero che viene composto per raggiungere i servizi di emergenza.

- **Maschera E9-1-1** Specifica un numero composto da un utente che viene quindi convertito nel numero di composizione di emergenza.

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del servizio di emergenza VoIP aziendale, vedere [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.


