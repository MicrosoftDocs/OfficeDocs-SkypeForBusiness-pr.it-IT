---
title: Gestione dell'integrità dei Teams dispositivi
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: snchatur
search.appverid: MET150
f1.keywords:
- NOCSH
description: Questo articolo ti guiderà nella gestione dell'integrità dei Teams, dei dispositivi in cui sono Microsoft Teams installati.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 40f03e6713cd68d2de61c6ee1368f3fd44b288ad
ms.sourcegitcommit: fd3d9118afa15d4750c0b1a98c2c85fcc76cfdc5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2021
ms.locfileid: "58684677"
---
# <a name="manage-the-health-of-teams-devices"></a>Gestire l'integrità dei Teams dispositivi

Gli amministratori possono monitorare l'integrità dei dispositivi installati Microsoft Teams usando lo stato di integrità, che indica la gravità dei problemi. Per verificare l'integrità di un dispositivo, è possibile  passare all'elenco dei dispositivi presente nella sezione Dispositivi dell'interfaccia Teams di amministrazione. La colonna Stato integrità in questo elenco indica lo stato di integrità corrente del dispositivo. Se si seleziona questo stato, viene **aperto il riquadro Stato integrità,** che fornisce informazioni più dettagliate sui problemi di integrità.

Molti tipi di problemi possono contribuire allo stato di integrità del dispositivo e il sistema dell'interfaccia di amministrazione di Teams valuta la gravità di questi problemi quando si verificano.

L'amministratore che gestisce i dispositivi Teams per l'organizzazione può decidere che la gravità dei problemi per loro non corrisponde alla configurazione predefinita Teams fornisce. Gli amministratori possono personalizzare la gravità e l'impatto sull'integrità dei dispositivi in modo che corrispondano alle priorità dell'organizzazione.

Teams Rooms dispositivi hanno periferiche collegate per offrire un'esperienza di riunione completa, come altoparlante, microfono, schermo, fotocamera. I dettagli su di essi sono disponibili nella pagina del dispositivo sotto le schede Periferiche e integrità. La connettività di queste periferiche influisce sull'integrità del dispositivo padre.

## <a name="feature-details"></a>Dettagli funzionalità

Quando si visualizzano i dettagli delle periferiche in una pagina del dispositivo, viene visualizzata **l'opzione Gestisci impatto sull'integrità.** Inoltre, gli amministratori possono anche visualizzare l'impatto di ogni periferica sull'integrità del dispositivo.

Per impostazione predefinita, tutte le periferiche hanno un **impatto critico** sull'integrità del dispositivo. Se una periferica è disconnessa, l'integrità del dispositivo padre diventerà **Critica** e il problema verrà visualizzato in **Problemi** critici nel riquadro stato integrità.

> [!NOTE]
> Le categorie periferiche **hdmi ingestire** e **calcolare** non sono disponibili per la personalizzazione in quanto sono cruciali per il funzionamento del dispositivo padre.

## <a name="how-does-this-work"></a>Come funziona?

1. Un amministratore può selezionare le periferiche per cui si vuole modificare l'impatto sull'integrità. Quindi possono selezionare Gestisci **impatto integrità**. In alternativa, possono anche trovare **l'opzione Gestisci** impatto sull'integrità nella **scheda** Periferiche di ogni scheda periferica.
1. Si **apre il** riquadro Impatto integrità e l'amministratore può selezionare il livello di impatto desiderato per le periferiche selezionate e salvarlo.

| Impostazioni Opzioni | Descrizione |
|------------------|-------------|
| **Non urgente** | Se è impostato per una categoria di periferiche, ad esempio uno schermo o un altoparlante, e la periferica è disconnessa, lo stato di integrità del dispositivo Teams Rooms diventerà **Non** urgente (invece di **Critico).** I nuovi problemi verranno categorizzati nella **sezione Non urgenti** del riquadro stato integrità.|
| **Nessun impatto** | Quando è impostato per una categoria di periferiche e la periferica è disconnessa, lo stato di integrità del dispositivo Teams Rooms rimarrà integro **(invece** di **Critico).** Questo problema di integrità non viene visualizzato nel riquadro dello stato di integrità.|
| **Critico** | Quando è impostato per una categoria di periferiche e la periferica è disconnessa, lo stato di integrità del dispositivo Teams Rooms diventa **Critico**. I nuovi problemi di questo tipo verranno categorizzati nella **sezione Critica** del riquadro stato di integrità.|
| **Ripristinare l'impostazione predefinita** | Se impostato per una categoria periferica, l'impatto sull'integrità della categoria verrà reimpostato su **Critico.** Una volta salvata questa scelta, le modifiche verranno applicate e l'impatto sull'integrità rifletterà le modifiche in futuro.|

## <a name="applicable-device-categories"></a>Categorie di dispositivi applicabili

Attualmente, questa funzionalità è disponibile per gestire l'impatto sull'integrità delle periferiche associate ai dispositivi Microsoft Teams Rooms (Windows).

## <a name="impact-on-other-workflows"></a>Impatto su altri flussi di lavoro

Se l'impatto sull'integrità delle periferiche è ridotto di gravità, gli amministratori potrebbero non notare problemi quando si verificano. È importante tenere presente che i dispositivi ad alta priorità devono essere monitorati con attenzione.

Ad esempio, se un avviso è configurato per essere attivato per ConfRoom1 se l'integrità diventa **Critica**. L'amministratore aveva ridotto l'impatto sull'integrità dello schermo e del relatore per la sala riunioni dall'impostazione predefinita, **Critico**, a **Non urgente**. Ora, se lo schermo è disconnesso, l'integrità di ConfRoom1 diventerà **Non urgente.** In questo caso, l'avviso non verrà attivato.
