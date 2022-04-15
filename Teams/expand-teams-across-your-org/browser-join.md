---
title: Gestire l'esperienza di partecipazione per Teams appuntamenti virtuali nei browser
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: Informazioni sull'esperienza di partecipazione per Teams appuntamenti virtuali nei browser.
ms.openlocfilehash: 418186734befa66f145ca56f883605715d83aa30
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853307"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>Gestire l'esperienza di partecipazione per Teams appuntamenti virtuali nei browser

Microsoft Teams consente agli utenti di partecipare facilmente agli appuntamenti virtuali senza dover scaricare Teams. Per un'esperienza più fluida, i partecipanti possono partecipare a appuntamenti come visite mediche e consulenze finanziarie da un browser desktop o per dispositivi mobili. I partecipanti non devono installare l'app Teams nel proprio dispositivo.

Con l'accesso al browser, quando un partecipante partecipa a un appuntamento, non viene richiesto di scaricare Teams. Al contrario, Teams si apre in un browser, in cui il partecipante può selezionare **Partecipa ora** per partecipare. Con questa funzionalità, ricorda che se Teams è già installato nel dispositivo, Teams si aprirà in un browser e non nell'app.

Attualmente, la partecipazione al browser è disponibile per gli appuntamenti pianificati tramite:

- [App Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- connettore EHR (Electronic Health Record) Microsoft Teams

  - Integrazione con [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integrazione con [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-browser-join"></a>Configurare l'accesso al browser

### <a name="appointments-scheduled-through-the-bookings-app"></a>Appuntamenti pianificati tramite l'app Bookings

Gli utilità di pianificazione nell'organizzazione possono attivare questa caratteristica per tipi di appuntamenti specifici e per singoli appuntamenti nell'app Bookings.

Dopo aver attivato questa funzionalità, l'e-mail di conferma o l'SMS inviato ai partecipanti conterrà un collegamento per l'accesso alla riunione che si apre Teams in un browser desktop o per dispositivi mobili. Per un elenco dei browser supportati, vedere [Browser supportati](#supported-browsers).

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>Attivare l'accesso al browser per un tipo di appuntamento

In Bookings passare a **Impostazioni** >  **Tipi di** appuntamento, selezionare un [tipo di appuntamento](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) e quindi attivare **Consenti ai partecipanti di partecipare da un browser**. In questo modo è possibile partecipare al browser per tutti gli appuntamenti di questo tipo.

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Screenshot dell'impostazione Consenti ai partecipanti di partecipare da un browser per i tipi di appuntamento nell'app Bookings":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>Attivare l'accesso al browser per un singolo appuntamento

In Bookings selezionare **Nuova prenotazione** e quindi attivare **Consenti ai partecipanti di partecipare da un browser**.

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Screenshot dell'impostazione Consenti ai partecipanti di partecipare da un browser nel nuovo modulo di prenotazione nell'app Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Appuntamenti pianificati tramite il connettore Teams EHR

Non è necessaria alcuna configurazione da parte dell'utente o del personale.

**Integrazione con Cerner EHR**: il connettore Teams EHR supporta i pazienti che partecipano a appuntamenti virtuali tramite un collegamento nel messaggio di testo SMS. Al momento dell'appuntamento, i pazienti possono partecipare toccando il collegamento nell'SMS e Teams si apre in un browser.

**Integrazione con Epic EHR**: il connettore Teams EHR supporta i pazienti che partecipano a appuntamenti virtuali tramite il Web di MyChart e i dispositivi mobili. Al momento dell'appuntamento, i pazienti possono iniziare l'appuntamento da Grafico personale usando il pulsante **Inizia visita virtuale** e Teams si apre in un browser.

## <a name="supported-browsers"></a>Browser supportati

Ecco i browser attualmente supportati. Se non diversamente indicato, è supportare l'ultima versione più due versioni precedenti.

|Piattaforma  |Chrome |Safari |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1; &sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1; La condivisione dello schermo in uscita non è supportata in iOS o Android.

&sup2; Le app iOS in Safari non possono selezionare i dispositivi con microfono e altoparlanti. Ad esempio, Bluetooth dispositivi. Questa è una limitazione del sistema operativo, che controlla la selezione predefinita del dispositivo.

## <a name="things-to-consider"></a>Aspetti da considerare

Il membro del personale che svolge l'appuntamento può condividere lo schermo dal proprio desktop, dispositivo mobile o client Web Teams con un partecipante che partecipa da un browser desktop o per dispositivi mobili. Tuttavia, i partecipanti non possono condividere lo schermo da un browser desktop o per dispositivi mobili.

## <a name="related-articles"></a>Articoli correlati

- [Appuntamenti virtuali con Teams e l'app Bookings](bookings-virtual-visits.md)
- [Creare un tipo di appuntamento Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Partecipare a un appuntamento di Bookings come partecipante](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Appuntamenti virtuali con Teams - Integrazione in Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Appuntamenti virtuali con Teams - Integrazione in Epic EHR](healthcare/ehr-admin.md)
