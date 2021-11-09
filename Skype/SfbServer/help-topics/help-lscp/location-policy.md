---
title: Criteri percorso
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.
ms.openlocfilehash: cfdff82c16aa4a9430bf8923cddd28bf26dad85a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840298"
---
# <a name="location-policy"></a>Criteri percorso

I criteri percorso determinano se i servizi di emergenza avanzati sono abilitati e come vengono utilizzati, oltre a definire come vengono utilizzate le informazioni percorso per utenti e contatti.

I criteri percorso includono un criterio globale e, facoltativamente, uno o più criteri sito e utente:

- **Criteri globali:** Il criterio globale viene creato per impostazione predefinita. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.

- **Criteri sito (facoltativo):** È possibile creare uno o più criteri percorso sito, ognuno dei quali si applica a un sito specifico. I criteri sito prevalgono sul criterio globale.

- **Criteri utente (facoltativo):** È possibile creare uno o più criteri percorso utente, ognuno dei quali si applica a un utente o a un gruppo di utenti specifico. I criteri utente prevalgono sul criteri globale e i criteri sito.

> [!NOTE]
> È inoltre possibile assegnare criteri percorso a siti di rete, ovvero gruppi di subnet. I criteri percorso assegnati a siti di rete hanno la precedenza su tutti gli altri criteri utente. Per informazioni dettagliate sull'assegnazione di criteri percorso ai siti di rete tramite cmdlet, vedere [Add a location policy to a network site in Skype for Business Server 2015.](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md) Per informazioni dettagliate sull'Skype for Business Server di controllo per assegnare un criterio percorso a un sito di rete, vedere [Configuring Network Sites.](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)

Nella pagina **Criteri percorso** viene visualizzato un elenco di tutti i criteri percorso definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività eseguibili

Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:

- Creare un nuovo criterio percorso sito o utente

- Modificare il criterio globale o un criterio sito o utente esistente

- Eliminare un criterio sito o utente

## <a name="ui-reference"></a>Riferimento all'interfaccia utente

Nell'elenco seguente sono descritti i comandi della pagina.

- **Nuovo** Avvia un nuovo criterio percorso sito o criteri percorso utente.

- **Modifica** Apre il criterio percorso selezionato per modificarlo, seleziona tutti i criteri percorso nell'elenco o elimina il criterio sito o il criterio utente selezionato.

    > [!NOTE]
    > Per il criterio globale, **Elimina** consente di riportare le impostazioni ai valori predefiniti.

- **Aggiorna** Aggiorna l'elenco dei criteri percorso.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Identifica il criterio percorso.

- **Ambito** Identifica l'ambito dei criteri percorso: globale, sito o utente.

- **E9-1-1** Selezionato se gli utenti assegnati a questo criterio percorso sono abilitati per E9-1-1.

- **Posizione** Specifica se agli utenti viene richiesto di immettere o meno le informazioni sulla posizione quando il client esegue la registrazione con Skype for Business Server in una nuova posizione e se visualizzano una dichiarazione di non responsabilità se ignorano il prompt senza immettere le informazioni sulla posizione.

- **Utilizzo PSTN** Specifica l'utilizzo pstN (Public Switched Telephone Network) utilizzato per determinare la route vocale utilizzata per instradare le chiamate di emergenza dai client che utilizzano questo profilo.

- **Numero E9-1-1** Specifica il numero composto per raggiungere i servizi di emergenza.

- **Maschera E9-1-1** Specifica un numero composto da un utente che viene quindi convertito nel numero di chiamata di emergenza.

Per informazioni dettagliate VoIP aziendale funzionalità e funzionalità del servizio di emergenza, vedere [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'utilizzo di criteri percorso, vedere [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) nella documentazione relativa alle operazioni.