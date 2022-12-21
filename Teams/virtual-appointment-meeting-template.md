---
title: Modello di riunione appuntamento virtuale in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: Informazioni su come gestire il modello di riunione appuntamento virtuale per gli utenti di Teams nell'organizzazione.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 459845115d8a705673f21b5e8a57dadac59841f6
ms.sourcegitcommit: f8da8f613fc3902d2607e322ad9dfbdeb8838c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2022
ms.locfileid: "69624918"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Modello di riunione appuntamento virtuale in Microsoft Teams

## <a name="overview"></a>Panoramica

Il modello Appuntamento virtuale è un modello predefinito di riunione in Microsoft Teams che gli utenti possono usare per pianificare appuntamenti virtuali con clienti, clienti e altre persone esterne all'organizzazione. Ad esempio, usalo per pianificare e condurre colloqui, sessioni di mentoring, consulenze finanziarie, esperienze di shopping virtuale e altro ancora.

Il modello consente di specificare i valori per le impostazioni della riunione che gli organizzatori della riunione controllano in genere. Offre la flessibilità necessaria per applicare le impostazioni predefinite e applicare le impostazioni. È possibile scegliere di bloccare le impostazioni in modo che gli organizzatori della riunione non possano modificarle quando usano il modello.

Con questo modello, è possibile abilitare un'esperienza coerente in tutta l'organizzazione per gli appuntamenti virtuali pianificati all'interno di Teams e contribuire ad applicare i requisiti di conformità.

Questo articolo offre una panoramica su come visualizzare e gestire il modello di riunione appuntamento virtuale nell'interfaccia di amministrazione di Teams.

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>Visualizzare o modificare le impostazioni del modello di riunione per un appuntamento virtuale

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, passare a **Modelli di riunione** > **.**
1. Scegliere **Appuntamento virtuale** e quindi selezionare **Modifica**.
1. Per apportare modifiche, selezionare un'opzione e quindi configurare le impostazioni desiderate. Per ogni opzione, è possibile definire le impostazioni seguenti:
    - **Valore predefinito**: valore applicato all'appuntamento virtuale quando si usa il modello.
    - **Visibilità**: scegliere **Nascondi** o **Mostra** per specificare se l'opzione è visibile agli organizzatori delle riunioni nelle opzioni delle riunioni di Teams.
    - **Stato** blocco: per impedire agli organizzatori della riunione di modificare il valore impostato, scegliere **Blocca**. Per consentire agli organizzatori della riunione di modificare il valore impostato, scegliere **Sblocca**.
1. Rivedere le modifiche e quindi scegliere **Salva**.

## <a name="manage-the-virtual-appointment-meeting-template"></a>Gestire il modello di riunione appuntamento virtuale

È possibile usare i criteri dei modelli di riunione nell'interfaccia di amministrazione di Teams per controllare i modelli di riunione disponibili per gli utenti dell'organizzazione. Per impostazione predefinita, il criterio Globale consente agli utenti di visualizzare e usare tutti i modelli di riunione, incluso il modello Appuntamento virtuale e tutti i modelli personalizzati creati.

Se si vuole rendere disponibile il modello Appuntamento virtuale a utenti o gruppi di utenti specifici dell'organizzazione, è possibile creare un criterio modello di riunione personalizzato e quindi assegnarlo a tali utenti o gruppi.

Per altre informazioni, vedere [Gestire i modelli di riunione in Teams](manage-meeting-templates.md).

## <a name="user-experience"></a>Esperienza utente

Quando gli utenti dell'organizzazione usano il modello di riunione per pianificare un appuntamento virtuale, le persone esterne all'organizzazione (guest esterni) ricevono un invito a una riunione personalizzato che include un **pulsante Partecipa come guest** e altri dettagli sull'appuntamento. Possono usare questo pulsante per partecipare facilmente da qualsiasi dispositivo senza dover scaricare e installare Teams.

Tenere presente che alcune opzioni di riunione di Teams potrebbero non essere applicabili ai guest esterni o a qualsiasi persona che partecipa usando il pulsante **Partecipa all'appuntamento come guest** . Per l'accesso guest sono supportate le seguenti opzioni di riunione:

- **Utenti autorizzati a ignorare la sala di attesa: l'impostazione** **Tutti** consente agli utenti guest esterni di ignorare la sala di attesa.
- **Scegliere co-organizzatori**
- **Registra automaticamente**
- **Consentire la chat della riunione**: è impostato su **Disabilitato** se si vuole impedire la chat prima, durante e dopo la riunione.

Persone all'interno dell'organizzazione ricevono un invito a una riunione e l'appuntamento viene visualizzato nel calendario di Teams e Outlook, dove possono partecipare facilmente come in qualsiasi altra riunione di Teams. Tutte le opzioni per le riunioni di Teams si applicano ai partecipanti che partecipano usando il collegamento alla riunione di Teams nell'invito alla riunione o dal calendario di Teams o Outlook.

Per altre informazioni su come usare il modello di riunione appuntamento virtuale e l'esperienza utente, vedere [Usare un modello di riunione di Teams per creare un appuntamento virtuale](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).

## <a name="related-articles"></a>Articoli correlati

- [Panoramica dei modelli di riunione personalizzati in Teams](custom-meeting-templates-overview.md)
