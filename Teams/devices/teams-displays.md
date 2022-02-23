---
title: Microsoft Teams display
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: Questo articolo fornisce una panoramica delle funzionalità supportate da Microsoft Teams display.
ms.openlocfilehash: 8c8004edd12042ca27e77e545f23b8770f8d1899
ms.sourcegitcommit: e9b0a274fdfee3d5bc8211cb099155546b281fe0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2022
ms.locfileid: "62926329"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams display

Microsoft Teams display sono una categoria di dispositivi Teams dedicati all-in-one che presentano un touchscreen ambiente e un'esperienza senza mani basata su Cortana. Questo articolo offre una panoramica delle Teams e consente di pianificare, distribuire e gestire i Teams visualizzati nell'organizzazione.

Teams display riunisce le&ndash; funzionalità preferite Teams chat, riunioni, chiamate, calendario e file&ndash; in un singolo dispositivo. Con Teams, gli utenti possono usare un microfono, una fotocamera e gli altoparlanti (o Bluetooth auricolare) per un'esperienza di chiamata e riunione affidabile. Teams display si integra con i PC Windows degli utenti per creare un'esperienza complementare che consente un'interazione uniforme tra dispositivi.

Per altre informazioni, vedere [Introduzione ai Teams visualizzati](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Caratteristiche supportate da Teams display

Oltre alle funzionalità [supportate dai telefoni Teams](phones-for-teams.md#features-supported-by-teams-phones) telefoni, le caratteristiche seguenti sono uniche per Teams display:

- **Display dedicati per Teams** gli utenti possono accedere a tutte le funzionalità Teams di base, tra cui chat, riunioni, chiamate, team e canali, file e altro ancora.
- **Esperienza di ambiente** Gli utenti possono rimanere facilmente al corrente del proprio lavoro con schermi sempre attivi e a colpo d'occhio per visualizzare le attività e le notifiche importanti senza cambiare contesto nel dispositivo di lavoro principale. Gli utenti possono anche personalizzare Teams visualizzazione personalizzando lo sfondo tramite le impostazioni.
- **Hands-free con Cortana** Gli utenti possono interagire con gli schermi Teams usando la loro voce per partecipare e presentare senza fatica alle riunioni, dettare le risposte a una chat di Teams, controllare cosa c'è nel calendario e altro ancora.
- **Lasciare una nota nella schermata di blocco** Gli utenti guest possono scegliere di lasciare note audio, video e di testo e gli utenti possono controllare le note lasciate dagli utenti guest e vedere chi si è fermato.  

## <a name="required-licenses"></a>Licenze obbligatorie

Teams licenze possono essere acquistate come parte di Microsoft 365 [e Office 365 abbonamenti](/office365/servicedescriptions/teams-service-description). Per altre informazioni sulle licenze necessarie per l'uso Teams display, vedere Chiamate vocali e [videochiamate con](https://products.office.com/microsoft-teams/voice-calling) Microsoft Teams.

Per altre informazioni su come ottenere Teams, vedere Come si ottiene l'accesso a Microsoft Teams[?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Distribuire Teams display usando Intune

Per altre informazioni su come distribuire Teams display con Intune, vedere Distribuire Teams telefoni e Teams [schermi](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gestire Teams visualizzati nell'organizzazione

Per gestire i dispositivi Teams, nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione passare a Teams **display**. Da qui è possibile modificare il profilo di configurazione del dispositivo, gestire gli aggiornamenti, riavviare i dispositivi, aggiungere e rimuovere tag per i dispositivi e altro ancora. Per altre informazioni, vedere [Gestire i dispositivi in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurare l'hot desk su Teams display

L'hot desk consente agli utenti dell'organizzazione di prenotare in anticipo le aree di lavoro temporanee tramite Teams e Outlook o dal dispositivo stesso. Quando l'hot desk è abilitato, gli utenti accedono Teams vengono visualizzati con le credenziali Microsoft 365 per accedere alle riunioni, alle chat e ai file. Quando si disconnette, tutte le informazioni personali vengono rimosse dal dispositivo.

Per iniziare, è necessario acquisire licenze Microsoft Teams Rooms Standard e creare account delle risorse per ogni Teams visualizzazione. Vedere [Distribuire Microsoft Teams Rooms con Office 365](../rooms/with-office-365.md) per creare account delle risorse.

Dopo aver creato gli account delle risorse, è possibile creare e assegnare un criterio per abilitare l'hot desking. Per [altre informazioni, vedere New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Poiché gli schermi Teams con hot desk vengono usati in aree di lavoro condivise da più persone, le regole di accesso condizionale e altre configurazioni di identità nell'ambiente, come l'autenticazione a più fattori, possono influire su questi dispositivi e causare problemi di accesso. Per indicazioni sulla protezione dei dispositivi condivisi, vedere Procedure consigliate per l'autenticazione per [i dispositivi Teams Android](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aggiornare Teams telefoni a Teams display

Teams display è l'evoluzione Teams telefoni. È possibile aggiornare i Teams telefoni dell'organizzazione a Teams tramite l'interfaccia Microsoft Teams di amministrazione. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento a Teams display. Per altre informazioni, vedere [Aggiornare Teams telefoni a Teams display](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vedere anche

[Introduzione ai Microsoft Teams visualizzati](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Aggiornare i telefoni IP a Teams display](upgrade-phones-to-displays.md)

[Cortana'assistenza vocale in Teams](../cortana-in-teams.md)