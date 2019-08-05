---
title: Criteri percorso
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: I criteri percorso determinano se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.
ms.openlocfilehash: e86bf3c37350f0e7e571068eb276aa0b237dc86c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192131"
---
# <a name="location-policy"></a>Criteri percorso

I criteri percorso determinano se il servizio Enhanced 9-1-1 (E9-1-1) è abilitato e come viene usato, nonché come vengono usate le informazioni sulla posizione per utenti e contatti.

I criteri percorso includono un criterio globale e, facoltativamente, uno o più criteri sito e utente:

- **Criteri globali:** Il criterio globale viene creato per impostazione predefinita. È possibile modificare il criterio globale, ma non eliminarlo. Se si tenta di rimuoverlo, tutte le impostazioni verranno ripristinate ai valori predefiniti.

- **Criteri sito (facoltativo):** È possibile creare uno o più criteri per la posizione del sito, ognuno dei quali si applica a un sito specifico. I criteri sito prevalgono sul criterio globale.

- **Criteri utente (facoltativo):** È possibile creare uno o più criteri posizione utente, ognuno dei quali si applica a un utente o un gruppo di utenti specifico. I criteri utente prevalgono sui criteri globale e i criteri sito.

> [!NOTE]
> È inoltre possibile assegnare criteri percorso a siti di rete, ovvero gruppi di subnet. I criteri percorso assegnati a siti di rete hanno la precedenza su tutti gli altri criteri utente. Per informazioni dettagliate sull'assegnazione di criteri di posizione ai siti di rete tramite cmdlet, vedere [aggiungere un criterio di posizione a un sito di rete in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Per informazioni dettagliate sull'uso del pannello di controllo di Skype for Business Server per assegnare un criterio di posizione a un sito di rete, vedere [configurazione dei siti di rete](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).

Nella pagina **Criteri percorso** viene visualizzato un elenco di tutti i criteri percorso definiti per l'organizzazione.

## <a name="tasks-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina **Criteri percorso** è possibile eseguire le attività seguenti:

- Creare un nuovo criterio percorso sito o utente

- Modificare il criterio globale o un criterio sito o utente esistente

- Eliminare un criterio sito o utente

## <a name="ui-reference"></a>Riferimenti UI

L'elenco seguente descrive i comandi presenti nella pagina.

- **Nuovo** Avvia un nuovo criterio della posizione del sito o dei criteri di posizione degli utenti.

- **Modifica** Apre il criterio della posizione selezionata per modificarlo, seleziona tutti i criteri di posizione nell'elenco o Elimina i criteri del sito o i criteri utente selezionati.

    > [!NOTE]
    > Per il criterio globale, il comando **Elimina** ripristina le impostazioni ai valori predefiniti.

- **Aggiornare** Aggiorna l'elenco dei criteri di posizione.

L'elenco seguente descrive i campi presenti nella pagina.

- **Nome** Identifica il criterio di posizione.

- **Ambito** Identifica l'ambito dei criteri di posizione: globale, sito o utente.

- **E9-1-1** Verificare se gli utenti assegnati a questo criterio di posizione sono abilitati per E9-1-1.

- **Posizione** Specifica se viene chiesto o meno agli utenti di immettere le informazioni sulla posizione quando il loro client esegue la registrazione con Skype for Business Server in una nuova posizione e se viene respinto il messaggio senza immettere le informazioni sulla posizione.

- **Uso PSTN** Specifica l'utilizzo PSTN (Public Switched Telephone Network) usato per determinare la route vocale usata per instradare chiamate di emergenza da client che usano questo profilo.

- **Numero E9-1-1** Specifica il numero composto per raggiungere i servizi di emergenza.

- **Maschera E9-1-1** Specifica un numero che un utente compone e quindi tradotto nel numero di chiamata di emergenza.

Per informazioni dettagliate sulle funzionalità e le funzionalità del servizio di emergenza VoIP aziendale, vedere [Panoramica di E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) nella documentazione relativa alla pianificazione. Per informazioni dettagliate sull'uso dei criteri percorso, vedere [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) nella documentazione relativa alle operazioni.


