---
title: Gestire l'esperienza di partecipazione Teams le visite virtuali nei browser per dispositivi mobili
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
description: Informazioni sull'esperienza di partecipazione Teams le visite virtuali nei browser per dispositivi mobili.
ms.openlocfilehash: 5c4b0f7ac9011d12d12e3076f900880292e72eb1
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288564"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>Gestire l'esperienza di partecipazione Teams le visite virtuali nei browser per dispositivi mobili

Microsoft Teams consente agli utenti di partecipare facilmente agli appuntamenti sui propri dispositivi mobili senza dover scaricare Teams. Per un'esperienza più fluida, i partecipanti possono partecipare a appuntamenti come visite sanitarie, consulenze finanziarie, orari di ufficio per docenti e così via, da un browser per dispositivi mobili. I partecipanti non devono installare l'app Teams per dispositivi mobili Android o iOS.

Con l'aggiunta del browser per dispositivi mobili, quando un partecipante partecipa a un appuntamento da un dispositivo mobile, non viene richiesto di scaricare Teams. Al contrario, Teams si apre in un browser per dispositivi mobili, in cui il partecipante può selezionare **Partecipa ora** per partecipare. Con questa funzionalità, tenere presente che se Teams è già installato nel dispositivo mobile di un partecipante, Teams verrà aperto in un browser per dispositivi mobili e non nell'app.

Attualmente, l'aggiunta al browser per dispositivi mobili è disponibile per gli appuntamenti pianificati nel modo seguente:

- [App Bookings](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- Microsoft Teams connettore Electronic Health Records (EHR)

  - Integrazione con [Cerner EHR](healthcare/ehr-admin-cerner.md)
  - Integrazione con [Epic EHR](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>Configurare l'accesso al browser per dispositivi mobili

### <a name="appointments-scheduled-through-the-bookings-app"></a>Appuntamenti pianificati tramite l'app Bookings

Gli utilità di pianificazione dell'organizzazione possono attivare questa caratteristica per tipi di appuntamenti specifici e per singoli appuntamenti nell'app Bookings.

Dopo aver attivato questa funzionalità, il messaggio di posta elettronica di conferma o il testo SMS inviato ai partecipanti conterrà un collegamento di partecipazione alla riunione che viene aperto Teams in un browser per dispositivi mobili. Nei dispositivi mobili Android, Teams si apre in Chrome. Nei dispositivi mobili iOS, Teams si apre in Safari.

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>Attivare l'accesso al browser per dispositivi mobili per un tipo di appuntamento

In Bookings **passare a** >  Impostazioni **artimentazione**, selezionare un tipo di [appuntamento e quindi](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) attivare Consenti ai partecipanti di partecipare **da un browser per dispositivi mobili**. In questo modo, il browser per dispositivi mobili può partecipare a tutti gli appuntamenti di questo tipo.

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Screenshot dell'impostazione Consenti ai partecipanti di partecipare da un browser per dispositivi mobili per i tipi di appuntamento nell'app Bookings":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>Attivare l'accesso al browser per dispositivi mobili per un singolo appuntamento

In Bookings selezionare **Nuova prenotazione** e quindi attivare Consenti ai **partecipanti di partecipare da un browser per dispositivi mobili**.

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Screenshot dell'impostazione Consenti ai partecipanti di partecipare da un browser per dispositivi mobili nel nuovo modulo di prenotazione nell'app Bookings":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Appuntamenti pianificati tramite il Teams EHR

Non è necessaria alcuna configurazione da parte dell'utente o del personale.

**Integrazione con Cerner EHR**: il connettore Teams EHR supporta i pazienti che a partecipare a visite virtuali tramite dispositivi mobili. Al momento dell'appuntamento, i pazienti possono partecipare a una visita virtuale toccando il collegamento nell'SMS. Il paziente sceglie il browser desiderato e quindi Teams si apre in tale browser.

**Integrazione con Epic EHR**: il connettore Teams EHR supporta i pazienti che a partecipare a visite virtuali tramite il Web MyChart e i dispositivi mobili. Al momento dell'appuntamento, i pazienti possono avviare una visita virtuale da MyChart usando il **pulsante Inizia visita** virtuale. Il paziente sceglie il browser desiderato e quindi Teams si apre in tale browser.

## <a name="supported-mobile-browsers"></a>Browser per dispositivi mobili supportati

Ecco i browser per dispositivi mobili attualmente supportati. Microsoft supporta l'ultima versione più due versioni precedenti, se non diversamente indicato.

|Piattaforma  |Chrome |Safari |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1; Le app iOS in Safari non possono selezionare i dispositivi del microfono e degli altoparlanti. Ad esempio, Bluetooth dispositivi. Si tratta di una limitazione del sistema operativo, che controlla la selezione predefinita del dispositivo.

&sup2; Safari 14+ e macOS 11+ sono necessari per il supporto video in uscita.

## <a name="things-to-consider"></a>Aspetti da considerare

Il membro del personale che conduce la visita virtuale può condividere lo schermo dal proprio client desktop, mobile o Web di Teams con un partecipante che partecipa da un browser per dispositivi mobili. Tuttavia, i partecipanti non possono condividere lo schermo da un browser per dispositivi mobili.

> [!NOTE]
> Stiamo aggiungendo altre funzionalità all'esperienza di partecipazione alla riunione nelle versioni future di Teams, quindi controlla di nuovo le informazioni più aggiornate. Per essere sempre al top delle funzionalità Teams, consulta la roadmap [Microsoft 365.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)

## <a name="related-articles"></a>Articoli correlati

- [Visite virtuali con Teams e l'app Bookings](bookings-virtual-visits.md)
- [Creare un tipo di appuntamento Bookings](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Partecipare a un appuntamento di Bookings come partecipante](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Visite virtuali con Teams - Integrazione in Cerner EHR](healthcare/ehr-admin-cerner.md)
- [Visite virtuali con Teams - Integrazione in Epic EHR](healthcare/ehr-admin.md)
