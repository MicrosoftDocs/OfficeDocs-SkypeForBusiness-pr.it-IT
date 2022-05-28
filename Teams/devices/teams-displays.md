---
title: Microsoft Teams schermi
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
search.appverid: MET150
ms.localizationpriority: medium
description: Questo articolo fornisce una panoramica e le funzionalità supportate da Microsoft Teams schermi.
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760868"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams schermi

gli schermi Microsoft Teams sono una categoria di dispositivi Teams dedicati all-in-one dotati di touchscreen ambientale e un'esperienza vivavoce con tecnologia Cortana. Questo articolo offre una panoramica dei display Teams e consente di pianificare, distribuire e gestire Teams schermi nell'organizzazione.

Teams display riunisce le tue funzionalità&ndash;di Teams preferite in un unico dispositivo: chat, riunioni, chiamate, calendario e file&ndash;. Con gli schermi Teams, gli utenti possono usare un microfono, una fotocamera e gli altoparlanti (o Bluetooth auricolare) per un'esperienza di chiamata e riunione affidabile. I display Teams si integrano con i PC Windows degli utenti per offrire un'esperienza complementare che consente un'interazione tra dispositivi senza problemi.

Per altre informazioni, vedi [Attività iniziali con Teams schermi](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Funzionalità supportate dagli schermi Teams

Oltre alle [funzionalità supportate da Teams telefoni](phones-for-teams.md#features-supported-by-teams-phones), le funzionalità seguenti sono specifiche per Teams schermi:

- **Schermi dedicati per Teams** Gli utenti possono accedere a tutte le funzionalità di Teams principali, tra cui chat, riunioni, chiamate, team e canali, file e altro ancora.
- **Esperienza ambientale** Gli utenti possono facilmente rimanere aggiornati sul proprio lavoro con schermi sempre attivi e a colpo d'occhio per vedere le attività e le notifiche importanti senza passare al contesto sul dispositivo di lavoro principale. Gli utenti possono anche personalizzare Teams schermi personalizzando lo sfondo tramite le impostazioni.
- **Vivavoce con Cortana** Gli utenti possono interagire con Teams schermi usando la voce per partecipare e presentare facilmente durante le riunioni, dettare risposte a una Teams chat, controllare cosa c'è nel calendario e altro ancora.
- **Lasciare una nota nella schermata di blocco** Gli utenti guest possono scegliere di lasciare le note audio, video e di testo e gli utenti possono controllare le note lasciate dagli utenti guest e vedere chi è fermato.  

## <a name="required-licenses"></a>Licenze necessarie

Teams licenze possono essere acquistate come parte di [Microsoft 365 e Office 365 abbonamenti](/office365/servicedescriptions/teams-service-description). Per altre informazioni sulle licenze necessarie per usare Teams schermi, vedi [Chiamate vocali e videochiamate con Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Per altre informazioni su come ottenere Teams, vedere [Ricerca per categorie ottenere l'accesso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Distribuire schermi Teams usando Intune

Per altre informazioni su come distribuire schermi Teams con Intune, vedi [Distribuire telefoni e schermi Teams Teams.](phones-displays-deploy.md)

## <a name="manage-teams-displays-in-your-organization"></a>Gestire Teams schermi nell'organizzazione

Per gestire i dispositivi di visualizzazione Teams, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Teams schermi**. Da qui puoi modificare il profilo di configurazione del dispositivo, gestire gli aggiornamenti, riavviare i dispositivi, aggiungere e rimuovere tag del dispositivo e altro ancora. Per altre informazioni, vedere [Gestire i dispositivi in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurare l'hot desking su schermi Teams

L'hot desking consente agli utenti dell'organizzazione di prenotare in anticipo le aree di lavoro temporanee tramite Teams e Outlook o dal dispositivo stesso. Quando è abilitato l'hot desking, gli utenti accedono a Teams vengono visualizzati con le loro credenziali di Microsoft 365 per accedere a riunioni, chat e file. Quando si disconnettono, tutte le informazioni personali vengono rimosse dal dispositivo.

Per iniziare, è necessario acquisire licenze di Microsoft Teams Rooms Standard e creare account delle risorse per ogni Teams visualizzato. Per [creare account delle risorse, vedere Creare account di risorse per sale e dispositivi di Teams condivisi](../rooms/with-office-365.md).

Dopo aver creato gli account delle risorse, è possibile creare e assegnare un criterio per abilitare l'hot desking. Per ulteriori informazioni, vedi [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) .

> [!IMPORTANT]
> Poiché gli schermi Teams con hot desking vengono usati nelle aree di lavoro condivise da più persone, le regole di accesso condizionale e altre configurazioni di identità nell'ambiente, come l'autenticazione a più fattori, possono influire su questi dispositivi e causare problemi di accesso. Per indicazioni sulla protezione dei dispositivi condivisi, vedere [Procedure consigliate per l'autenticazione per i dispositivi Teams Android condivisi](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Aggiornare i telefoni Teams a schermi Teams

Teams display è l'evoluzione dei telefoni Teams. È possibile aggiornare Teams telefoni dell'organizzazione a Teams schermi usando l'interfaccia di amministrazione di Microsoft Teams. Questa opzione è disponibile solo per i telefoni che supportano l'aggiornamento a schermi Teams. Per altre informazioni, vedi [Aggiornare i telefoni Teams a schermi Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Vedere anche

[Introduzione agli schermi Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefoni per Teams](phones-for-teams.md)

[Telefoni IP certificati per Microsoft Teams](teams-ip-phones.md)

[Aggiornare i telefoni IP a schermi Teams](upgrade-phones-to-displays.md)

[Cortana assistenza vocale in Teams](../cortana-in-teams.md)