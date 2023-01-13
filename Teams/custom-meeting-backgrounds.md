---
title: Sfondi delle riunioni personalizzate per le riunioni di Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: L'uso di risorse aziendali approvate come gli sfondi per creare sfondi personalizzati per le riunioni di Teams all'interno dell'organizzazione.
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800223"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Sfondi delle riunioni personalizzate per le riunioni di Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>Panoramica

La personalizzazione nelle riunioni di Teams consente alle organizzazioni di estendere le loro identità visive nell'intera esperienza di riunione. L'uso di sfondi personalizzati per le riunioni consente di favorire la creazione di una cultura aziendale interna e di aumentare la consapevolezza generale del marchio sia con i partecipanti alle riunioni interni che con i partecipanti esterni. Con l'aiuto dei team di gestione del marchio e di comunicazione aziendale di un'organizzazione, gli amministratori possono facilmente configurare e creare sfondi personalizzati per le riunioni per diverse business unit e reparti all'interno di un unico tenant.

Per impostazione predefinita, gli utenti con licenza Premium di Teams che sono amministratori o a cui è stato assegnato un criterio di personalizzazione delle riunioni possono creare riunioni con sfondi di riunioni personalizzati. Questi sfondi personalizzati saranno disponibili solo per gli utenti finali dell'organizzazione che hanno una licenza di Teams Premium da usare.

## <a name="prerequisites"></a>Prerequisiti

Prima di configurare sfondi di riunione personalizzati per le riunioni di Teams, verificare di avere gli elementi seguenti:

- Accesso allo SKU Teams Premium
- Sei un amministratore con accesso all'interfaccia di amministrazione di Teams o ti è stato assegnato un criterio di personalizzazione
- Hai abilitato i criteri [in background personalizzati](#enabling-the-custom-background-policy)
- Le immagini di sfondo soddisfano le [specifiche richieste](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>Configurazione di sfondi personalizzati per le riunioni

Gli amministratori possono caricare e gestire sfondi personalizzati per le riunioni di Teams nell'interfaccia di amministrazione di Teams.

### <a name="enabling-the-custom-background-policy"></a>Abilitazione dei criteri in background personalizzati

Per creare sfondi personalizzati, l'amministratore dovrà creare un nuovo criterio di personalizzazione delle riunioni o modificare il criterio predefinito globale dell'organizzazione.
Per abilitare i criteri in background personalizzati, gli amministratori eseguiranno la procedura seguente:

1. Aprire l'interfaccia di amministrazione di Teams
2. Selezionare **Riunioni** dal riquadro di spostamento
3. In Riunioni sono disponibili due modi per accedere ai criteri in background personalizzati. È possibile selezionare **Criteri di personalizzazione** per selezionare un criterio esistente o crearne uno nuovo. In alternativa, è possibile selezionare **Criteri riunione** e quindi il pulsante **Immagini riunione personalizzate** nell'angolo in alto a destra.
4. All'interno del criterio scelto, passare alla sezione **Sfondi riunione personalizzati**
5. Attivare l'impostazione **Sfondi personalizzati** per abilitare l'impostazione
6. Seleziona **Salva**

### <a name="adding-custom-background-images"></a>Aggiunta di immagini di sfondo personalizzate

Dopo aver abilitato i criteri di sfondo personalizzati, è possibile caricare le immagini di sfondo personalizzate. Queste immagini verranno visualizzate nelle interfacce degli utenti finali, ordinate in base all'ora di caricamento.

I caricamenti devono attenersi ai seguenti parametri. Gli amministratori possono caricare:

- Formati di immagine PNG e JPEG per le immagini
- Immagini con dimensioni minime di 360 px X 360 px
- Immagini con dimensioni minime di 3840 px X 2160 px
- Un massimo di 50 immagini di sfondo personalizzate

Per caricare le immagini, passare a **Criteri di personalizzazione** **delle riunioni** >  e selezionare il criterio nel passaggio precedente. Scorrere verso il basso fino alla sezione **Sfondi riunione personalizzati** e selezionare **+Aggiungi** sotto la tabella con l'interruttore dello sfondo personalizzato. Dopo aver selezionato +Aggiungi, verrà aperto un riquadro denominato **Gestione sfondi** , che consente di aggiungere le immagini.

> [!NOTE]
> Solo gli utenti finali con una licenza di Teams Premium vedranno queste immagini nel riquadro Impostazioni sfondo.

### <a name="saving-custom-background-images"></a>Salvataggio di immagini di sfondo personalizzate

Le anteprime delle immagini caricate sono disponibili in una nuova tabella nella sezione **Sfondi personalizzati delle riunioni** . Questa tabella visualizza anche il nome e la risoluzione delle immagini. Dopo aver confermato la scelta delle immagini caricate, selezionare il pulsante **Salva** sotto la tabella di anteprima. Dopo aver selezionato Salva, gli sfondi caricati sono visibili agli utenti finali con una licenza di Teams Premium.

## <a name="where-are-custom-backgrounds-visible"></a>Dove sono visibili gli sfondi personalizzati

L'elenco seguente mostra i client supportati in cui sono visibili gli sfondi personalizzati:

- Client Web
- Client desktop
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>Chi può selezionare e applicare sfondi personalizzati per le riunioni

Solo Teams Premium utenti con licenza possono usare gli sfondi della riunione nel riquadro Impostazioni sfondo.

> [!NOTE]
> Gli utenti esterni o anonimi non possono usare sfondi personalizzati per le riunioni.

### <a name="who-can-view-custom-meeting-backgrounds"></a>Chi può visualizzare sfondi personalizzati per le riunioni

Anche se solo gli utenti finali con licenza possono selezionare la scelta degli sfondi caricati, chiunque può visualizzare lo sfondo applicato a una riunione. Questi utenti includono:

- Utenti inclusi nel tenant Teams Premium con licenza
- Utenti nel tenant, senza licenza
- Utenti esterni
- Utenti anonimi
