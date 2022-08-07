---
title: Schermi di Microsoft Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Questo articolo fornisce una panoramica delle funzionalità supportate dagli schermi di Microsoft Teams.
ms.openlocfilehash: 18b8219a3eef391170c7321ae994d79f1b73f016
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268771"
---
# <a name="microsoft-teams-displays"></a>Schermi di Microsoft Teams

I display di Microsoft Teams sono una categoria di dispositivi Teams dedicati all-in-one che dispongono di un touchscreen ambientale e di un'esperienza vivavoce con tecnologia Cortana. Questo articolo fornisce una panoramica degli schermi di Teams e può aiutarti a pianificare, distribuire e gestire gli schermi di Teams nella tua organizzazione.

I display di Teams uniscono le funzionalità&ndash;preferite di Teams in un unico dispositivo: chat, riunioni, chiamate, calendario e file&ndash;. Con gli schermi di Teams, gli utenti possono usare un microfono, una fotocamera e gli altoparlanti (o cuffie Bluetooth) per un'esperienza di chiamata e riunione affidabile. I display di Teams si integrano con i PC Windows degli utenti per offrire un'esperienza complementare che consente un'interazione tra dispositivi senza interruzioni.

Per altre informazioni, vedere [Introduzione agli schermi di Teams](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Funzionalità supportate dagli schermi di Teams

Oltre alle [funzionalità supportate dai telefoni di Teams](phones-for-teams.md#features-supported-by-teams-phones), le funzionalità seguenti sono univoche per gli schermi di Teams:

- **Schermi dedicati per Teams** Gli utenti possono accedere a tutte le funzionalità principali di Teams, tra cui chat, riunioni, chiamate, team e canali, file e altro ancora.
- **Esperienza ambientale** Gli utenti possono facilmente rimanere aggiornati sul proprio lavoro con schermi sempre attivi e a colpo d'occhio per vedere le attività e le notifiche importanti senza passare al contesto sul dispositivo di lavoro principale. Gli utenti possono anche personalizzare gli schermi di Teams personalizzando lo sfondo tramite le impostazioni.
- **Vivavoce con Cortana** Gli utenti possono interagire con gli schermi di Teams usando la propria voce per partecipare e presentare facilmente alle riunioni, dettare risposte a una chat di Teams, controllare cosa c'è nel calendario e altro ancora.
- **Lasciare una nota nella schermata di blocco** Gli utenti guest possono scegliere di lasciare le note audio, video e di testo e gli utenti possono controllare le note lasciate dagli utenti guest e vedere chi è fermato.  

## <a name="required-licenses"></a>Licenze necessarie

Le licenze di Teams possono essere acquistate come parte di [Microsoft 365 e Office 365 abbonamenti](/office365/servicedescriptions/teams-service-description). Per altre informazioni sulle licenze necessarie per usare gli schermi di Teams, vedere [Chiamate vocali e videochiamate con Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Per altre informazioni su come ottenere Teams, vedere [Ricerca per categorie ottenere l'accesso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Distribuire gli schermi di Teams usando Intune

Per altre informazioni su come distribuire gli schermi di Teams usando Intune, vedere [Distribuire i telefoni e gli schermi di Teams](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gestire gli schermi di Teams nell'organizzazione

Per gestire i dispositivi di visualizzazione di Teams, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Schermi di Teams**. Da qui puoi modificare il profilo di configurazione del dispositivo, gestire gli aggiornamenti, riavviare i dispositivi, aggiungere e rimuovere tag del dispositivo e altro ancora. Per altre informazioni, vedere [Gestire i dispositivi in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurare l'hot desking sugli schermi di Teams

L'hot desking consente agli utenti dell'organizzazione di prenotare in anticipo le aree di lavoro temporanee tramite Teams e Outlook o dal dispositivo stesso. Quando è abilitato l'hot desking, gli utenti accedono a Teams visualizzando le loro credenziali di Microsoft 365 per accedere a riunioni, chat e file. Quando si disconnettono, tutte le informazioni personali vengono rimosse dal dispositivo.

Per iniziare, è necessario acquisire licenze di Microsoft Teams Rooms Standard e creare account di risorse per ogni visualizzazione di Teams. Vedere [Creare account di risorse per sale e dispositivi di Teams condivisi](../rooms/with-office-365.md) per creare account delle risorse.

Dopo aver creato gli account delle risorse, è possibile creare e assegnare un criterio per abilitare l'hot desking. Per ulteriori informazioni, vedi [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Poiché gli schermi di Teams con hot desking vengono usati nelle aree di lavoro condivise da più persone, le regole di accesso condizionale e altre configurazioni di identità nell'ambiente, come l'autenticazione a più fattori, possono influire su questi dispositivi e causare problemi di accesso. Per indicazioni sulla protezione dei dispositivi condivisi, vedere [Procedure consigliate per l'autenticazione per i dispositivi Teams Android condivisi](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aggiornare i telefoni di Teams agli schermi di Teams

Teams visualizza è l'evoluzione dei telefoni di Teams. È possibile aggiornare i telefoni di Teams dell'organizzazione a schermi Teams usando l'interfaccia di amministrazione di Microsoft Teams. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento agli schermi di Teams. Per altre informazioni, vedere [Aggiornare i telefoni di Teams agli schermi di Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vedere anche

[Introduzione agli schermi di Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Aggiornare i telefoni IP agli schermi di Teams](upgrade-phones-to-displays.md)

[Assistenza vocale di Cortana in Teams](../cortana-in-teams.md)